# Disallow unsupported Node.js built-in APIs on the specified version (`n/no-unsupported-features/node-builtins`)

💼 This rule is enabled in the ✅ `recommended` [config](https://github.com/eslint-community/eslint-plugin-n#-configs).

<!-- end auto-generated rule header -->

Node.js community is improving built-in APIs continuously.
You can check [Node.js Documentation](https://nodejs.org/api/) to know which Node.js version supports each Node.js API.

This rule reports unsupported Node.js built-in APIs on the configured Node.js version as lint errors.
Editor integrations of ESLint would be useful to know it in real-time.

## 📖 Rule Details

This rule reports APIs of Node.js built-in APIs on the basis of [Node.js v13.2.0 Documentation](https://nodejs.org/docs/v13.2.0/api/).

### Configured Node.js version range

This rule gets the supported Node.js version range from the following, falling back to the next if unspecified:

1. Rule configuration `version`
2. ESLint [shared setting](http://eslint.org/docs/user-guide/configuring.html#adding-shared-settings) `node.version`
3. `package.json` [`engines`] field
4. `>=8.0.0`

The default version is `8.0.0` because it's the minimum version the community is maintaining (see also [Node.js Release Working Group](https://github.com/nodejs/Release#readme)).

For Node.js packages, using the [`engines`] field is recommended because it's the official way to indicate support:

```json
{
    "name": "your-module",
    "version": "1.0.0",
    "engines": {
        "node": ">=8.0.0"
    }
}
```

For [Shareable Configs](https://eslint.org/docs/latest/developer-guide/shareable-configs) or packages with a different development environment (e.g. pre-compiled, web package, etc.), you can configure ESLint with `settings.node.version` to specify support.

### Options

```json
{
    "n/no-unsupported-features/node-builtins": ["error", {
        "version": ">=8.0.0",
        "ignores": []
    }]
}
```

#### version

As mentioned above, this rule reads the [`engines`] field of `package.json`.
But, you can overwrite the version by `version` option.

The `version` option accepts [the valid version range of `node-semver`](https://github.com/npm/node-semver#range-grammar).

#### ignores

If you are using transpilers, maybe you want to ignore the warnings about some features.
You can use this `ignores` option to ignore the given features.

The `"ignores"` option accepts an array of the following strings.

<details>

**Globals:**

- `"Buffer.alloc"`
- `"Buffer.allocUnsafe"`
- `"Buffer.allocUnsafeSlow"`
- `"Buffer.from"`
- `"TextDecoder"`
- `"TextEncoder"`
- `"URL"`
- `"URLSearchParams"`
- `"console.clear"`
- `"console.count"`
- `"console.countReset"`
- `"console.debug"`
- `"console.dirxml"`
- `"console.group"`
- `"console.groupCollapsed"`
- `"console.groupEnd"`
- `"console.table"`
- `"console.markTimeline"`
- `"console.profile"`
- `"console.profileEnd"`
- `"console.timeLog"`
- `"console.timeStamp"`
- `"console.timeline"`
- `"console.timelineEnd"`
- `"process.allowedNodeEnvironmentFlags"`
- `"process.argv0"`
- `"process.channel"`
- `"process.cpuUsage"`
- `"process.emitWarning"`
- `"process.getegid"`
- `"process.geteuid"`
- `"process.hasUncaughtExceptionCaptureCallback"`
- `"process.hrtime.bigint"`
- `"process.ppid"`
- `"process.release"`
- `"process.report"`
- `"process.setegid"`
- `"process.seteuid"`
- `"process.setUncaughtExceptionCaptureCallback"`
- `"process.stdout.getColorDepth"`
- `"process.stdout.hasColor"`
- `"process.stderr.getColorDepth"`
- `"process.stderr.hasColor"`
- `"queueMicrotask"`
- `"require.resolve.paths"`

**`assert` module:**

- `"assert.deepStrictEqual"`
- `"assert.doesNotReject"`
- `"assert.notDeepStrictEqual"`
- `"assert.rejects"`
- `"assert.strict"`
- `"assert.strict.doesNotReject"`
- `"assert.strict.rejects"`

**`async_hooks` module:**

- `"async_hooks"`
- `"async_hooks.createHook"`

**`buffer` module:**

- `"buffer.Buffer.alloc"`
- `"buffer.Buffer.allocUnsafe"`
- `"buffer.Buffer.allocUnsafeSlow"`
- `"buffer.Buffer.from"`
- `"buffer.constants"`
- `"buffer.kMaxLength"`
- `"buffer.transcode"`

**`child_process` module:**

- `"child_process.ChildProcess"`

**`console` module:**

- `"console.clear"`
- `"console.count"`
- `"console.countReset"`
- `"console.debug"`
- `"console.dirxml"`
- `"console.group"`
- `"console.groupCollapsed"`
- `"console.groupEnd"`
- `"console.table"`
- `"console.markTimeline"`
- `"console.profile"`
- `"console.profileEnd"`
- `"console.timeLog"`
- `"console.timeStamp"`
- `"console.timeline"`
- `"console.timelineEnd"`

**`crypto` module:**

- `"crypto.Certificate.exportChallenge"`
- `"crypto.Certificate.exportPublicKey"`
- `"crypto.Certificate.verifySpkac"`
- `"crypto.KeyObject"`
- `"crypto.createPrivateKey"`
- `"crypto.createPublicKey"`
- `"crypto.createSecretKey"`
- `"crypto.constants"`
- `"crypto.fips"`
- `"crypto.generateKeyPair"`
- `"crypto.generateKeyPairSync"`
- `"crypto.getCurves"`
- `"crypto.getFips"`
- `"crypto.privateEncrypt"`
- `"crypto.publicDecrypt"`
- `"crypto.randomFillSync"`
- `"crypto.randomFill"`
- `"crypto.scrypt"`
- `"crypto.scryptSync"`
- `"crypto.setFips"`
- `"crypto.sign"`
- `"crypto.timingSafeEqual"`
- `"crypto.verify"`

**`dns` module:**

- `"dns.Resolver"`
- `"dns.resolvePtr"`
- `"dns.promises"`

**`events` module:**

- `"events.EventEmitter.once"`
- `"events.once"`

**`fs` module:**

- `"fs.Dirent"`
- `"fs.copyFile"`
- `"fs.copyFileSync"`
- `"fs.mkdtemp"`
- `"fs.mkdtempSync"`
- `"fs.realpath.native"`
- `"fs.realpathSync.native"`
- `"fs.promises"`
- `"fs.writev"`
- `"fs.writevSync"`

**`http2` module:**

- `"http2"`

**`inspector` module:**

- `"inspector"`

**`module` module:**

- `"module.Module.builtinModules"`
- `"module.Module.createRequireFromPath"`
- `"module.Module.createRequire"`
- `"module.Module.syncBuiltinESMExports"`
- `"module.builtinModules"`
- `"module.createRequireFromPath"`
- `"module.createRequire"`
- `"module.syncBuiltinESMExports"`

**`os` module:**

- `"os.constants"`
- `"os.constants.priority"`
- `"os.getPriority"`
- `"os.homedir"`
- `"os.setPriority"`
- `"os.userInfo"`

**`path` module:**

- `"path.toNamespacedPath"`

**`perf_hooks` module:**

- `"perf_hooks"`
- `"perf_hooks.monitorEventLoopDelay"`

**`process` module:**

- `"process.allowedNodeEnvironmentFlags"`
- `"process.argv0"`
- `"process.channel"`
- `"process.cpuUsage"`
- `"process.emitWarning"`
- `"process.getegid"`
- `"process.geteuid"`
- `"process.hasUncaughtExceptionCaptureCallback"`
- `"process.hrtime.bigint"`
- `"process.ppid"`
- `"process.release"`
- `"process.report"`
- `"process.resourceUsage"`
- `"process.setegid"`
- `"process.seteuid"`
- `"process.setUncaughtExceptionCaptureCallback"`
- `"process.stdout.getColorDepth"`
- `"process.stdout.hasColor"`
- `"process.stderr.getColorDepth"`
- `"process.stderr.hasColor"`

**`stream` module:**

- `"stream.Readable.from"`
- `"stream.finished"`
- `"stream.pipeline"`

**`trace_events` module:**

- `"trace_events"`

**`url` module:**

- `"url.URL"`
- `"url.URLSearchParams"`
- `"url.domainToASCII"`
- `"url.domainToUnicode"`

**`util` module:**

- `"util.callbackify"`
- `"util.formatWithOptions"`
- `"util.getSystemErrorName"`
- `"util.inspect.custom"`
- `"util.inspect.defaultOptions"`
- `"util.inspect.replDefaults"`
- `"util.isDeepStrictEqual"`
- `"util.promisify"`
- `"util.TextDecoder"`
- `"util.TextEncoder"`
- `"util.types"`
- `"util.types.isBoxedPrimitive"`

**`v8` module:**

- `"v8"`
- `"v8.DefaultDeserializer"`
- `"v8.DefaultSerializer"`
- `"v8.Deserializer"`
- `"v8.Serializer"`
- `"v8.cachedDataVersionTag"`
- `"v8.deserialize"`
- `"v8.getHeapCodeStatistics"`
- `"v8.getHeapSnapshot"`
- `"v8.getHeapSpaceStatistics"`
- `"v8.serialize"`
- `"v8.writeHeapSnapshot"`

**`vm` module:**

- `"vm.Module"`
- `"vm.compileFunction"`

**`worker_threads` module:**

- `"worker_threads"`

</details>

### Shared Settings

The following options can be set by [shared settings](http://eslint.org/docs/user-guide/configuring.html#adding-shared-settings).
Several rules have the same option, but we can set this option at once.

- `version`

For Example:

```json
{
    "settings": {
        "node": {
            "version": ">=8.0.0",
        }
    },
    "rules": {
        "n/no-unsupported-features/node-builtins": ["error", {
            "ignores": []
        }]
    }
}
```

### Known limitations

This rule cannot find non-static things.
For example:

- New properties and methods of instances.
- New parameters of functions.
- New `options` properties of function parameters.
- New events.

[`engines`]: https://docs.npmjs.com/files/package.json#engines

## 🔎 Implementation

- [Rule source](../../../lib/rules/no-unsupported-features/node-builtins.js)
- [Test source](../../../tests/lib/rules/no-unsupported-features/node-builtins.js)
