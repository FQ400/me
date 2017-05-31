### The Situation

I have an infernojs app that is built using webpack. As a dependency for the UI I use bootstrap v4.alpha.6. with the webpack-bootstrap-loader.

After trying node8 with npm5 I run in the following issue:

```
ERROR in ./~/bootstrap-loader/lib/bootstrap.loader.js!./~/bootstrap-loader/no-op.js
Module build failed: TypeError: Invalid Version: https://registry.npmjs.org/bootstrap/-/bootstrap-4.0.0-alpha.6.tgz
    at new SemVer (/Users/xxx/workspace/inferno-project/node_modules/semver/semver.js:293:11)
    at Function.major (/Users/xxx/workspace/inferno-project/node_modules/semver/semver.js:551:10)
    at exports.default (/Users/xxx/workspace/inferno-project/node_modules/bootstrap-loader/lib/utils/checkBootstrapVersion.js:18:31)
    at Object.module.exports.pitch (/Users/xxx/workspace/inferno-project/node_modules/bootstrap-loader/lib/bootstrap.loader.js:159:65)
 @ ./~/bootstrap-loader/loader.js 2:17-61
 @ ./src/index.jsx
```

**What happens is** the bootstrap-loader checks the version of bootstrap using the `version` field in the `package.json` of the installed package in `node_modules` ([see this file](https://github.com/shakacode/bootstrap-loader/blob/master/src/utils/checkBootstrapVersion.js#L18)). The check itself is done by the package `semver`. `semver`'s major function is used to determine the major version number ([Semver Code](https://github.com/npm/node-semver)).

With npm `4.2.0` the version field of installed packages into `node_modules` contains in my case something like `4.0.0-alpha.6`.

With npm `5.0.0` the version field of installed packages into `node_modules` contains something like `https://registry.npmjs.org/bootstrap/-/bootstrap-4.0.0-alpha.6.tgz`. I guess this comes with the `package-lock.json`.

### What now?
Which lib should be responsible for dealing with that issue? Should the dev-team of the bootstrap-loader parse the value before putting it into `semver`?

Or should `semver` handle URLs?

Or is it an npm issue?
