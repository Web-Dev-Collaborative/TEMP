Introduction
------------

### Concepts

-   `Schema` - The root. Defines what queries you can do, and what types they return.
-   `Resolver` - Functions that return data.
-   `Type` - A type definition describing the shape of the data you’ll return.

### Plug

#### web/router.ex

    defmodule Blog.Web.Router do
      use Phoenix.Router

      forward "/", Absinthe.Plug,
        schema: Blog.Schema
    end

{: data-line=“4,5”}

Absinthe is a Plug, and you pass it one **Schema**.

See: [Our first query](http://absinthe-graphql.org/tutorial/our-first-query/)

Main concepts
-------------

{: .-three-column}

### Schema

#### web/schema.ex

    defmodule Blog.Schema do
      use Absinthe.Schema
      import_types Blog.Schema.Types

      query do
        @desc "Get a list of blog posts"
        field :posts, list_of(:post) do
          resolve &Blog.PostResolver.all/2
        end
      end
    end

{: data-line=“5,6,7,8,9,10”}

This schema will account for `{ posts { ··· } }`. It returns a **Type** of `:post`, and delegates to a **Resolver**.

### Resolver

#### web/resolvers/post\_resolver.ex

    defmodule Blog.PostResolver do
      def all(_args, _info) do
        {:ok, Blog.Repo.all(Blog.Post)}
      end
    end

{: data-line=“3”}

This is the function that the schema delegated the `posts` query to.

### Type

#### web/schema/types.ex

    defmodule Blog.Schema.Types do
      use Absinthe.Schema.Notation

      @desc "A blog post"
      object :post do
        field :id, :id
        field :title, :string
        field :body, :string
      end
    end

{: data-line=“4,5,6,7,8,9”}

This defines a type `:post`, which is used by the resolver.

Schema
------

### Query arguments

#### GraphQL query

    { user(id: "1") { ··· } }

#### web/schema.ex

    query do
      field :user, type: :user do
        arg :id, non_null(:id)
        resolve &Blog.UserResolver.find/2
      end
    end

{: data-line=“3”}

#### Resolver

    def find(%{id: id} = args, _info) do
      ···
    end

{: data-line=“1”}

See: [Query arguments](http://absinthe-graphql.org/tutorial/query-arguments/)

### Mutations

#### GraphQL query

    {
      mutation CreatePost {
        post(title: "Hello") { id }
      }
    }

#### web/schema.ex

    mutation do
      @desc "Create a post"
      field :post, type: :post do
        arg :title, non_null(:string)
        resolve &Blog.PostResolver.create/2
      end
    end

{: data-line=“1”}

See: [Mutations](http://absinthe-graphql.org/tutorial/mutations/)

References
----------

-   [Absinthe website](http://absinthe-graphql.org/) *(absinthe-graphql.org)*
-   [GraphQL cheatsheet](./graphql) *(devhints.io)*
