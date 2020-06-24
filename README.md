# await.ops proposal

The [rendered spec text](https://jack-works.github.io/proposal-await.ops/). [Playground](https://www.typescriptlang.org/play/index.html?ts=4.0.0-pr-39224-4&ssl=1&ssc=1&pln=5&pc=2#code/IYZwngdgxgBAZgV2gFwJYHsIwLbFRACgEoYBvAKBipmAHc9kA6YAGxZgAZLqpMRkYAbQAeAXRgBeGvVRNWLQQAUATumyoQAU0bLNIdCwBumggCYAzOaKjuVYY2ToAosIAOmTRDSti5AL5AA).

Introduce await.all / await.race / await.allSettled / await.any to simplify the usage of Promises

-   Stage: 0

-   Champions: [Jack Works](https://github.com/Jack-Works), [Jordan Harband](https://github.com/ljharb)

## Motivation

To simplify the usage of Promises. (Previous discussions: https://es.discourse.group/t/allow-awaiting-on-arrays/178/19)

Usage:

```js
// before
await Promise.all(users.map(async x => fetchProfile(x.id)))

// after
await.all users.map(async x => fetchProfile(x.id))
```

Syntax:

```js
await.all expr
// eq: await Promise.all(expr)

await.race expr
// eq: await Promise.race(expr)

await.allSettled expr
// eq: await Promise.allSettled(expr)

await.any expr
// eq: await Promise.any(expr)
```
