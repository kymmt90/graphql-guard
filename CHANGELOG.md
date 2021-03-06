# Changelog

The following are lists of the notable changes included with each release.
This is intended to help keep people informed about notable changes between
versions, as well as provide a rough history. Each item is prefixed with
one of the following labels: `Added`, `Changed`, `Deprecated`,
`Removed`, `Fixed`, `Security`. We also use [Semantic Versioning](http://semver.org)
to manage the versions of this gem so
that you can set version constraints properly.

#### [Unreleased](https://github.com/exAspArk/graphql-guard/compare/v1.1.0...HEAD)

* WIP

#### [v1.1.0](https://github.com/exAspArk/graphql-guard/compare/v1.0.0...v1.1.0) – 2018-05-09

* `Added`: support to `mask` fields depending on the context.

#### [v1.0.0](https://github.com/exAspArk/graphql-guard/compare/v0.4.0...v1.0.0) – 2017-07-31

* `Changed`: guards for every `*` field also accepts arguments: `->(object, arguments, context) { ... }`:

Before:

<pre>
GraphQL::ObjectType.define do
  name "Post"
  guard ->(obj, ctx) { ... }
  ...
end
</pre>

After:

<pre>
GraphQL::ObjectType.define do
  name "Post"
  guard ->(obj, <b>args</b>, ctx) { ... }
  ...
end
</pre>

* `Changed`: `.field_with_guard` from `graphql/guard/testing` module accepts policy object as a second argument:

Before:

<pre>
<b>guard_object</b> = GraphQL::Guard.new(policy_object: GraphqlPolicy)
posts_field = QueryType.field_with_guard('posts', <b>guard_object</b>)
</pre>

After:

<pre>
posts_field = QueryType.field_with_guard('posts', <b>GraphqlPolicy</b>)
</pre>

#### [v0.4.0](https://github.com/exAspArk/graphql-guard/compare/v0.3.0...v0.4.0) – 2017-07-25

* `Added`: ability to test `guard` lambdas via field.

#### [v0.3.0](https://github.com/exAspArk/graphql-guard/compare/v0.2.0...v0.3.0) – 2017-07-19

* `Added`: ability to use custom error handlers.

#### [v0.2.0](https://github.com/exAspArk/graphql-guard/compare/v0.1.0...v0.2.0) – 2017-07-19

* `Added`: support for object policies.

#### [v0.1.0](https://github.com/exAspArk/graphql-guard/compare/e6d7d0f...v0.1.0) – 2017-07-19

* `Added`: initial functional version with inline policies.
