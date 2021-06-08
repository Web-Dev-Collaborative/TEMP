;

Operators
---------

### Accessors

    SELECT * FROM users WHERE data->>'name' = 'John';
    SELECT data->>'name' AS name FROM users;

{: .-setup}

<table><thead><tr class="header"><th>Operator</th><th>Description</th><th>Example</th><th>Returns</th></tr></thead><tbody><tr class="odd"><td><code>-&gt;</code> <em>int</em></td><td>Get array element <code>2</code></td><td><code>data-&gt;2</code></td><td>JSON</td></tr><tr class="even"><td><code>-&gt;</code> <em>text</em></td><td>Get object key <code>name</code></td><td><code>data-&gt;'name'</code></td><td>JSON</td></tr><tr class="odd"><td><code>#&gt;</code> <em>text[]</em></td><td>Get keypath <code>a,b</code> (eg, <code>data.a.b</code>)</td><td><code>data#&gt;'{a,b}'</code></td><td>JSON</td></tr><tr class="even"><td>-</td><td></td><td></td><td></td></tr><tr class="odd"><td><code>-&gt;&gt;</code> <em>int</em></td><td>Get array element <code>2</code></td><td><code>data-&gt;&gt;2</code></td><td>Text</td></tr><tr class="even"><td><code>-&gt;&gt;</code> <em>text</em></td><td>Get object key <code>name</code></td><td><code>data-&gt;&gt;'name'</code></td><td>Text</td></tr><tr class="odd"><td><code>#&gt;&gt;</code> <em>text[]</em></td><td>Get keypath <code>a,b</code> (eg, <code>data.a.b</code>)</td><td><code>data#&gt;&gt;'{a,b}'</code></td><td>Text</td></tr></tbody></table>

{: .-headers.-shortcuts}

`>` returns JSON, `>>` returns text.

### Boolean operators

    SELECT * FROM users WHERE data->tags ? 'admin';
    SELECT data->tags ? 'admin' AS is_admin FROM users;

{: .-setup}

<table><thead><tr class="header"><th>Operator</th><th>Description</th><th>Example</th></tr></thead><tbody><tr class="odd"><td><code>?</code> <em>str</em></td><td>Does <code>data</code> have key <code>name</code>?</td><td><code>data ? 'name'</code></td></tr><tr class="even"><td><code>?|</code> <em>text[]</em></td><td>Does <code>data</code> have <code>a</code> or <code>b</code>?</td><td><code>data ?| array['a','b']</code></td></tr><tr class="odd"><td><code>?&amp;</code> <em>text[]</em></td><td>Does <code>data</code> have <code>a</code> and <code>b</code>?</td><td><code>data ?&amp; array['a','b']</code></td></tr><tr class="even"><td><code>@&gt;</code> <em>jsonb</em></td><td>Does <code>left</code> include <code>right</code>?</td><td><code>data @&gt; '{"b":2}'::jsonb</code></td></tr><tr class="odd"><td><code>&lt;@</code> <em>jsonb</em></td><td>Does <code>right</code> include <code>left</code>?</td><td><code>data &lt;@ '{"a":1,"b":2}'::jsonb</code></td></tr></tbody></table>

{: .-headers.-shortcuts.-left-align}

When `?`/`?|`/`?&` works on objects, it checks keys; when it works on arrays, it checks for elements.

Updating
--------

### Arrays and objects

    UPDATE users SET tags = tags || array['admin'];

{: .-setup}

<table><thead><tr class="header"><th>Operator</th><th>Example</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>||</code> <em>json</em></td><td><code>data || array['a','b']</code></td><td>Concatenate</td></tr><tr class="even"><td><code>-</code> <em>str</em></td><td><code>data - 'a'</code></td><td>Delete a key</td></tr><tr class="odd"><td><code>-</code> <em>int</em></td><td><code>data - 1</code></td><td>Delete an array item</td></tr><tr class="even"><td><code>#-</code> <em>text[]</em></td><td><code>data #- '{us,name}'</code></td><td>Delete a path</td></tr></tbody></table>

{: .-headers.-shortcuts}

Only available in PostgreSQL 9.5+.

### jsonb\_set

    UPDATE users SET data = jsonb_set(data, '{name}', '"John"');

Only available in PostgreSQL 9.5+.

Functions
---------

#### fn(json) → json

    jsonb_set(data, '{path}', value)
    jsonb_strip_nulls(data)

#### fn(···) → json

    to_json("Hello"::text)
    array_to_json('{1,2}'::int[])

#### Iteration

    SELECT * from json_each('{"a":1, "b":2}')
    SELECT * from json_each_text('{"a":1, "b":2}')
    -- key | value

This is an incomplete list, there’s way too many!

See: [JSON functions](https://www.postgresql.org/docs/9.5/static/functions-json.html)

More examples
-------------

-   `'{"a":1}'::jsonb ? 'a'`
-   `'["a"]'::jsonb ? 'a'`

References
----------

-   <a href="https://www.postgresql.org/docs/9.5/static/functions-json.html" class="uri">https://www.postgresql.org/docs/9.5/static/functions-json.html</a>
-   <a href="https://www.postgresql.org/docs/9.5/static/datatype-json.html" class="uri">https://www.postgresql.org/docs/9.5/static/datatype-json.html</a>
