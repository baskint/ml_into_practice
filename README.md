# BookSearch

mix phx.new book_search
Now, run the following command to change to the root directory of your project
and list its contents:
cd book_search && ls
The output of this command will look like this:

assets _build config deps lib mix.exs mix.lock priv README.md test

Next, you’ll need to install pgvector. Start by adding pgvector as a dependency
in your mix.exs:
{:pgvector, "~> 0.2.0"}
Then run mix deps.get. Next, create a new file lib/postgrex_types.ex and add the
following code:
```
Postgrex.Types.define(BookSearch.PostgrexTypes,
[Pgvector.Extensions.Vector] ++ Ecto.Adapters.Postgres.extensions(),
[]
)
```
Next, add the following to config/config.exs:
config :book_search, BookSearch.Repo, types: BookSearch.PostgrexTypes
Then, create a migration with mix ecto.gen.migration create_vector_extension and add
the following:

brew install postgis

https://github.com/pgvector/pgvector

Now you can visit [`localhost:4000`](http://localhost:4000) from your browser.

Ready to run in production? Please [check our deployment guides](https://hexdocs.pm/phoenix/deployment.html).

## Learn more

  * Official website: https://www.phoenixframework.org/
  * Guides: https://hexdocs.pm/phoenix/overview.html
  * Docs: https://hexdocs.pm/phoenix
  * Forum: https://elixirforum.com/c/phoenix-forum
  * Source: https://github.com/phoenixframework/phoenix
