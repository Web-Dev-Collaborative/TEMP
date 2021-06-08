/

Joshua's Docs - React / JSX - Cheatsheet

Theme:

Light

<a href="#other-resources" class="anchor before"></a>

Other resources

My other pages:

-   [React Hooks](/cheatsheets/react/react-hooks/)
-   [React Performance and Optimizations](/cheatsheets/react/react-performance-optimization/)

External resources:

<table><thead><tr class="header"><th>What &amp; Link</th><th>Type</th><th></th></tr></thead><tbody><tr class="odd"><td>"The React Handbook" by Flavio Copes - <a href="https://www.freecodecamp.org/news/the-react-handbook-b71c27b0a795/">Online version</a> <a href="https://flaviocopes.com/page/react-handbook/">PDF signup</a><br />
   ---&gt; Amazing resource!</td><td>Guide</td><td></td></tr><tr class="even"><td><a href="https://sebastiandedeyne.com/react-for-vue-developers/">"React for Vue Developers"</a> by Sebastian De Deyne</td><td>Guide / Cheatsheet</td><td></td></tr><tr class="odd"><td><a href="http://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/">React Lifecycles Method Diagram</a></td><td>Cheatsheet</td><td></td></tr><tr class="even"><td><a href="https://github.com/typescript-cheatsheets/react-typescript-cheatsheet">React+TypeScript Cheatsheets</a><br />
    - <a href="https://react-typescript-cheatsheet.netlify.app/">Live Website</a></td><td>Cheatsheet</td><td></td></tr><tr class="odd"><td><a href="https://github.com/piotrwitek/react-redux-typescript-guide">React Redux TypeScript Guide</a></td><td>Cheatsheet</td><td></td></tr><tr class="even"><td>PluralSight: <a href="https://www.pluralsight.com/guides/composing-react-components-with-typescript">Composing React Components with TypeScript</a></td><td>Guide</td><td></td></tr><tr class="odd"><td>Post: <a href="https://reactjs.org/blog/2018/06/07/you-probably-dont-need-derived-state.html">"You Probably Don't Need Derived State"</a></td><td>Guide</td><td></td></tr><tr class="even"><td>Collection: <a href="https://github.com/enaqx/awesome-react">enaqx/awesome-react</a></td><td>Collection</td><td></td></tr><tr class="odd"><td>Kent C. Dodds - <a href="https://kentcdodds.com/blog/super-simple-start-to-react">"Super Simple Start to React"</a></td><td>Guide</td><td></td></tr><tr class="even"><td>Steven Jin: <a href="https://medium.com/@stevenjinyi/study-sheet-for-react-interview-questions-2020-2fe25b8fa316">Cheat Sheet for React Interview, 2020</a></td><td>Refresher / Cheatsheet</td><td></td></tr><tr class="odd"><td><a href="https://github.com/learning-zone/react-interview-questions">learning-zone/react-interview-questions</a></td><td>Refresher / Cheatsheet</td><td></td></tr></tbody></table>

<a href="#binding-template-literal" class="anchor before"></a>

Binding template literal

Binding template literal to property expecting string: You have to use double brackets to "break out" of JSX and into regular JS. Instead of:

    <SEO title="`${props.pageContext.slug}`" />

You need:

    <SEO title={`${props.pageContext.slug}`} />

<a href="#creating-unique-keys" class="anchor before"></a>

Creating unique keys

You want a unique identifier, which is actually harder than one might expect to create. Using the `index` provided within a loop is not recommended, and even combining with something like `(new Date()).getTime()` is not guaranteed to be unique.

There are tons of packages out there that you can drop in to create unique Ids. Or just make a composite key out of enough unique parameters to ensure non-duplicates.

<a href="#misc--how-do-i" class="anchor before"></a>

Misc / How Do I...

-   You can now use empty elements, known as *fragments*, to wrap siblings:

    -   `<><div></div><div></div></>`

-   Issues returning JSX?

    -   More than one line? Make sure wrapped in parenthesis `return (<div></div>)`
    -   Make sure there is \*only **one\*** root level element

-   Pass a bunch of options to a component as props (basically convert JS Obj to props)

    -   Just use spread operator - `{...props}`
    -   You can use this re-use the same props across multiple components!
    -   Be careful about directly spreading vs capturing via rest parameters and then spreading - you might not want to pass *all* props to child component

        -   This is why you often see `const {myVarA, myVarB, ...restProps} =                               props;` inside components -&gt; `restProps` would be a subset of `props` that does not contain `myVarA` or `myVarB`

-   Simulate a change event on a `<input>` element

    -   Use a combination of an exposed setter with a manual event dispatch
    -   See <https://stackoverflow.com/a/46012210/11447682>

-   How to add an external stylesheet (not for bundling)

    -   Instead of using `import` within a JS file (like *App.js*), add the stylesheet directly as a link tag element in the **HTML** file (e.g. `<link rel="stylesheet"                           href="https://.../style.css" />`)

-   How do I access an element directly (similar to native browser APIs like `document.getElementById`) in React? How do I get the DOM node?

    -   That is a great use case for React `refs`! - [Docs](https://reactjs.org/docs/refs-and-the-dom.html)
    -   Options:

        -   Newest and recommended: [`useRef` hook](https://reactjs.org/docs/hooks-reference.html#useref)

            -   `myRef = useRef(null)`

        -   Older:- `this.myRef = React.createRef()` in class constructor

    -   You can access DOM node through `myRef.current`, after attaching via `<MyElement ref={myRef}/>`

-   How do I expose and call a function from a child component in a parent component (aka passing methods up through the component tree)?

    -   This is considered a bit of an *anti-pattern* with React, and is generally avoided entirely (things are always passed down, not up).
    -   However, there are still ways to do so - the main way is to use refs ([S/O](https://stackoverflow.com/a/37950970/11447682), [Docs](https://reactjs.org/docs/refs-and-the-dom.html))

-   What's with the `{}` curly braces? Is this Mustache or Handlebars templating?

    -   No, the curly braces simply tell the JSX compiler that you are about to give it something that should be evaluated as a ***JavaScript Expression***, rather than a string or component.

<a href="#tips" class="anchor before"></a>

Tips

-   You can assign JSX to variables! Makes it very easy to reuse!
-   Make use of object destructuring assignments to avoid repetitive props syntax

    -   `const {hidden, dataArr, isAdmin, isAuthed} =                           this.props`
    -   -&gt; Or, destructure right in function argument, `const myComponent = ({hidden, dataArr, isAdmin,                           isAuthed}) => {}`

-   You can use class members and/or regular vars to hold changing values, as opposed to putting in state/props, if you want to avoid unnecessary renders when those values are not part of UI

<a href="#asset-management-and-usage" class="anchor before"></a>

Asset management and usage

You have two main options when it comes to asset management:

-   [Public Folder](https://create-react-app.dev/docs/using-the-public-folder): Place in `/public`

    -   Pull into HTML with `%PUBLIC_URL%`
    -   Pull into JS with `process.env.PUBLIC_URL`

-   [Bundling](https://create-react-app.dev/docs/adding-images-fonts-and-files): Place asset files *alongside* JS, in `/src`

    -   Pull into JS by using `import` at top of file with relatively path
    -   Pull into css (e.g. for background image) with relative path

The second option [is *always* preferred](https://create-react-app.dev/docs/adding-images-fonts-and-files), since it uses webpack to bundle assets and will help keep the size of your app down by only bundling assets that are actually used (as well as some other tricks).

<a href="#importing-assets-in-js-or-css" class="anchor before"></a>

Importing assets in JS or CSS

Examples:

JS:

    import background from './assets/background.jpg';
    // ...
    render() {
        return (
            <img src={background} />
        )
    }

CSS:

    #main {
        background-image: url(./assets/background.jpg);
    }

<a href="#getting-around-method-binding-of-this" class="anchor before"></a>

Getting around method binding of `this`

A common issue with React is preserving the value of `this`, especially when it comes to event handlers, like `onClick`.

If the callback you are assigning uses `this` within its body, you will have issues if the value of `this` changes (most often in a `Cannot read property '___' of undefined` error).

Here are some ways to ensure the value of `this` stays the way you want it to:

<a href="#explicit-with-bind-on-the-attribute" class="anchor before"></a>

Explicit, with `.bind()` on the attribute

The older method was commonly to use `.bind()` to explicitly bind the value of this at the point of attaching the handler. That might look something like this:

    <CustomComponent onClick={this.handleEvent.bind(this)}>

<a href="#es6-class-binding" class="anchor before"></a>

ES6 Class binding

If you are using the new ES6 class syntax, you have all the other options, plus a few more. Let's say this is our base code:

    class MyComponent extends React.Component {
        constructor(props) {
            super(props);
            this.state = {counter: 0};
        }

        handleClick(evt) {
            const updatedCount = this.state.counter + 1;
            this.setState({
                counter: updatedCount
            });
            console.log(this.state.counter);
        }

        render() {
            return (
                <button onClick={this.handleClick}> Counter + </button>
            );
        }
    }

One option is to use `.bind()`, in the constructor:

    constructor(props) {
        super(props);
        this.state = {counter: 0};
        // ADDED:
        this.handleClick = this.handleClick.bind(this);
    }

Another option is to turn the `handleClick` method, into a *member*, that is the value of an arrow function, thus automatically binding `this` to the class:

    // Rest of class definition
    // Or: public handleClick = (evt) => {}
    handleClick = (evt) => {
        const updatedCount = this.state.counter + 1;
        this.setState({
            counter: updatedCount
        });
        console.log(this.state.counter);
    }
    // ...

> Technically, this is actually an ES6 *public field*, which is, as of 2019, in an experimental stage, so while it is well supported with transpiled JS/TS, it has limited native browser support.

<a href="#inline-arrow-functions" class="anchor before"></a>

Inline arrow functions

One of the benefits (or drawbacks) of arrow functions is that they lexically bind `this` - **automatically**. So, if you do:

    <CustomComponent onClick={(evt) => {
        this.handleEvent(evt);
    }}>

It doesn't matter if `CustomComponent` has a different `this` scope, because the arrow function binds the callback where you defined it!

<a href="#use-createreactclass" class="anchor before"></a>

Use `createReactClass`

If you use `createReactClass`, you generally don't have to worry about this issue, as [createReactClass uses autobinding](https://reactjs.org/docs/react-without-es6.html#autobinding), which basically does `.bind()` for you.

<a href="#more-reading" class="anchor before"></a>

More reading

-   <http://egorsmirnov.me/2015/08/16/react-and-es6-part3.html>
-   <https://www.sitepoint.com/bind-javascripts-this-keyword-react/>

------------------------------------------------------------------------

<a href="#computed-properties" class="anchor before"></a>

Computed properties

Unlike Vue, which has a specific syntax for computed properties, React doesn't really care how you try to formulate values based on computed state properties.

<a href="#es6-class---getter" class="anchor before"></a>

ES6 Class - Getter

With the new ES6 class based approach, a very clean solution is to use *getters*, with something like:

    class MyComponent extends React.Component {
        // ... class stuff
        get isAdult() {
            return typeof(this.state.age) === 'number' && this.state.age > 18;
        }
    }

<a href="#within-the-render-function-itself" class="anchor before"></a>

Within the render function itself

There is nothing preventing you from computing a value within the `render` function itself. For example:

    class MyComponent extends React.Component {
        // ... class stuff
        render() {
            const isAdult = typeof(this.state.age) === 'number' && this.state.age > 18;
            return (
                <div>
                    Is adult = {isAdult.toString()}
                </div>
            );
        }
    }

<a href="#as-a-function" class="anchor before"></a>

As a function

Another vanilla solution here is to simply use a function to return the computed value, rather than anything else. How you declare this is up to you:

-   Explicitly, with `function myFunction(){}`
-   As a ES6 class member

    -   `public isAdult() {}`

-   With an arrow function to bind `this`

    -   `const isAdult = () => {};`

-   Etc.

To use within your `render` method, simply make sure you actually execute it by following it with the parenthesis and arguments if applicable.

<a href="#state-management-system" class="anchor before"></a>

State management system

If you are using a dedicated state management system, there is a chance that what you are using might already have something in place to not only provide explicit computed properties, but also optimize them, to prevent redundant expensive re-calculations.

For example, if you use MobX, make sure to check out [this page](https://mobx.js.org/refguide/computed-decorator.html) on *computed values*.

<a href="#further-reading" class="anchor before"></a>

Further reading:

-   <https://daveceddia.com/computed-properties-in-react/>

------------------------------------------------------------------------

<a href="#handlebars--mustache-type-logic-loops-conditional-etc" class="anchor before"></a>

Handlebars / Mustache type logic (loops, conditional, etc)

<a href="#conditional-rendering" class="anchor before"></a>

Conditional rendering

Tons of options - see ["7 ways to implement conditional rendering"](https://scotch.io/tutorials/7-ways-to-implement-conditional-rendering-in-react-applications).

Some tricky ones to remember, but can be very helpful are:

-   AND (`&&`) operator to show or hide

    -   You can use `{shouldShowBool && <div>I'll only show                           up if shouldShowBool is true!</div>}`
    -   This works because in JS, `A && B` returns B if A is true, ***without*** coercing B to a boolean

-   Ternary Operator (`_?_:_`) to swap between things

    -   You can use `{isLeaving ? <p>Goodbye!</p> :                           <p>Hello!</p>}`

<a href="#loop--array-render" class="anchor before"></a>

Loop / array render

The main way to render an array of something in React is to simply pass an array of JSX, within a *JavaScript Expression* block (e.g. `{myJsxArr}`). However, there are many ways to write this code:

You could:

-   Create an array of JSX template code assigned to a variable, and use it within `render()`, with something like: `items.push(<div                       key={UNIQUE_KEY}>{CONTENT}</div>);`
-   Iterate over the items directly in `render()`, and return the template there:

        const render = function() {
            const items = ['bread', 'milk', 'cookies'];
            return (
                <ul>
                    {items.map((value, index) => {
                        return <li key={index}>{value}</li>
                    })}
                </ul>
            );
        }

-   Use an IIFE to construct and return the array, all inline within the JSX:

        <div>
            <h1>One through Ten:</h1>
            {(function () {
                const jsxArr = [];
                for (let x = 1; x <= 10; x++) {
                    jsxArr.push(<p key={x}>Number {x}</p>);
                }
                return jsxArr;
            })()}
        </div>

    -   This is kind of an anti-pattern, so I would avoid and instead construct the array further up in the component before starting to return JSX / HTML.

<a href="#react-hooks" class="anchor before"></a>

React Hooks

See [my separate cheat sheet](/cheatsheets/react/react-hooks/).

<a href="#react---typescript-and-tsx" class="anchor before"></a>

React - TypeScript and TSX

> 👉I also have [a general cheat sheet on TypeScript](/cheatsheets/typescript/) you might find helpful!

<a href="#react---typescript-and-tsx---resources" class="anchor before"></a>

React - TypeScript and TSX - Resources

-   [My General TS Cheat Sheet](/cheatsheets/typescript/)
-   [typescript-cheatsheets/react](https://github.com/typescript-cheatsheets/react)
-   [TypeScript Handbook - JSX](https://www.typescriptlang.org/docs/handbook/jsx.html)
-   @ddprrt: [TypeScript and React: Components](https://fettblog.eu/typescript-react/components/)

<a href="#react---common-ts-issues" class="anchor before"></a>

React - Common TS Issues

-   Error using component: `'__' cannot be used as a JSX component. Its return type                         '___' is not a valid JSX element.` + `ts(2786)`

    -   Read the full error message to be sure, but this could be because you indeed have something unsafe or incorrectly typed
    -   In some cases, this can be caused by type definition files [getting "out of sync"](https://stackoverflow.com/a/53859712/11447682). Especially if the specific error is that the return type might be `null`, but you know it shouldn't be

        -   Try completely deleting `node_modules`, all lock files, and then re-installing

    -   Does adding `@types/react` as a devDependency fix it?
    -   Are you using `Preact`? You might want to take a look at [scurker/preact-and-typescript guide](https://github.com/scurker/preact-and-typescript), or see if [this specific issue (around preact/compat) applies](https://joshuatz.com/posts/2020/fixing-jsx-types-between-preact-and-react-libraries/).

-   `Cannot find name '___'`

    -   Did you accidentally name your file with `.ts` instead of `.tsx`?
    -   Make sure you have configured the `jsx` and `jsxFactory` in `compilerOptions` in the TSConfig

<a href="#react---common-ts-syntax-stuff" class="anchor before"></a>

React - Common TS Syntax Stuff

-   Declaring prop types

    // All of the below are acceptable

    // We can define the shape of props separately
    interface BirthdayProps {
        age: number;
        name: string;
    }
    export const BirthdayGreeting = (props: BirthdayProps) => (
        <span>{`Congrats ${props.name} on turning ${props.age}`}</span>
    );


    // ...or, we can inline it
    export const BirthdayGreeting = (props: { age: number; name: string }) => (
        <span>{`Congrats ${props.name} on turning ${props.age}`}</span>
    );

    // And we can also use destructuring for easier nested prop access:
    export const BirthdayGreeting = ({ age, name }: { age: number; name: string }) => (
        <span>{`Congrats ${name} on turning ${age}`}</span>
    );

-   Reusing Prop Types / Extracting Prop Types

    -   You can use `ComponentProps<typeof MyComponent>` (or `ComponentPropsWithoutRef`)

        -   For standard elements, you can use with string constant `ComponentProps<'div'>`

    -   Optimally, if using a library that separately exports Prop types, import & use that directly (e.g. `import {BoxProps} from '@chakra-ui/core'`)
    -   Another alternative is `JSX.IntrinsicElements["div"]`, but this is not recommended.
    -   See [this S/O answer](https://stackoverflow.com/a/59137835/11447682)
    -   TS React Cheatsheet: ["Wrapping/Mirroring a HTML element](https://github.com/typescript-cheatsheets/react/blob/main/docs/advanced/patterns_by_usecase.md#wrappingmirroring-a-html-element)

-   Taking generic props / extending another component props

    -   It kind of depends on how specific you want to be, and what exact ecosystem you are using (`react`, `preact`, etc.)
    -   It is usually best to combine your custom props with either:

        -   A props interface exported from your framework (e.g. `BoxProps` from Chakra UI)

            -   Or...

        -   `React.ComponentProps<T>` utility

            -   See reusing prop types section above for details

    -   Example: Custom component that allows parent to pass all standard `<div>` props 👇

            interface Props {
                name: string;
            }

            const MyComponent = (props: Props & ComponentProps<'div'>) => {
                return (
                    <div {...props} className={['myComponent', props.className].join(' ')}>
                        <span>Hello {props.name}</span>
                    </div>
                )
            };

-   Accepting components through props / passing children

    -   The type signature of children is kind of tricky in React. In general, practically anything can be a child, so the type is pretty wide.
    -   In standard React:

        -   the type for props that accept children looks like this: `P & { children?: ReactNode };` ([src](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/6a1c6a5567fa177396fa802b2367ec34e1028eea/types/react/index.d.ts#L825))
        -   And `ReactNode` can practically be anything:

            -   `type ReactNode = ReactChild | ReactFragment |                                   ReactPortal | boolean | null |                                   undefined;` ([src](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/6a1c6a5567fa177396fa802b2367ec34e1028eea/types/react/index.d.ts#L239))
            -   This gets expanded even further...

    -   In `preact`:

        -   Type for props with children looks like: `P & { children: ComponentChildren }` ([src](https://github.com/preactjs/preact/blob/c7a7253da8fa8b447af0269217ef14a3ae02680e/src/index.d.ts#L15))
        -   Just like in React, this gets expanded until it represents practically anything ([src](https://github.com/preactjs/preact/blob/c7a7253da8fa8b447af0269217ef14a3ae02680e/src/index.d.ts#L46-L54))

-   Typing DOM events and change handlers

    -   There are multiple ways to do this
    -   If you are trying to type the `evt` for an event handler, you can...

        -   Use a type that accepts a generic slot for the event-generating element:

            -   `evt: MouseEvent<{ElementType}>`
            -   `evt: TargetedEvent<{ElementType},                                   Event>`
            -   `evt: TargetedEvent<{ElementType},                                   {EventSubType}>`
            -   Example: `TargetedEvent<HTMLButtonElement,                                   MouseEvent>`

        -   Merge a generic event type with an explicit type for `evt.target`:

            -   `evt: MouseEvent<HTMLButtonElement>                                   & {target: HTMLButtonElement}`
            -   `evt:                                   h.JSX.TargetedEvent<HTMLSelectElement,                                   Event> & {target:                                   HTMLSelectElement}`
            -   `evt: InputEvent & {target:                                   HTMLSelectElement`

        -   Use the direct type, if you have it:

            -   `onClick={(evt: MouseEvent) => {}}`

    -   If you are trying to type the element of `evt.target`, you can just type assert for that section:

        -   `evt.target as HTMLInputElement`

    -   Some of this also depends on React vs Preact, framework libs, etc.

<a href="#material-ui-notes" class="anchor before"></a>

Material-UI Notes

<a href="#material-ui-media-queries" class="anchor before"></a>

Material-UI: Media Queries

In general, the [docs on breakpoints](https://material-ui.com/customization/breakpoints/) are a good place to start. Here are a few options:

-   You can use them directly in `makeStyles`:

        const useStyles = makeStyles(theme => ({
            myStyle: {
                width: '100px',
                '@media (min-width: 1000px)': {
                    width: '400px',
                },
                // Or, with theme settings
                // https://material-ui.com/customization/breakpoints/#css-media-queries
                [theme.breakpoints.up('sm')]: {
                    width: '200px',
                },
            }
        }));

-   You can use the provided [`useMediaQuery` hooks](https://material-ui.com/customization/breakpoints/#usemediaquery-hook)

Markdown Source Last Updated:

Fri Jan 01 2021 10:42:57 GMT+0000 (Coordinated Universal Time)

Markdown Source Created:

Wed Aug 21 2019 20:31:01 GMT+0000 (Coordinated Universal Time)

© 2021 Joshua Tzucker, Built with [Gatsby](https://www.gatsbyjs.org)

<span class="MuiButton-label">About This Site</span>

[Feedback](https://docs.google.com/forms/d/e/1FAIpQLScDGobzD52IsjgXRdxjUU9qu3qvvmRTMfBSzIzNEbC44iVzLw/viewform?usp=pp_url&entry.913929489=)
