# react-native-version

`react-native-version` extend the behaviour of [npm version](https://docs.npmjs.com/cli/version). react-native-version [docs](https://github.com/stovmascript/react-native-version)

The fork adds:

`--never-increment-prerelease` detect prerelease version and use `--never-increment-build`

`--version-build` to set version to build number

## npm-scripts hook (automatic method)

### Setup

```bash
npm i github:denis-kungurov/react-native-version#<commit-hash> --save-dev
```

Hook into the "version" or "postversion" npm script in your app's package.json:

```diff
{
  "name": "AwesomeProject",
  "scripts": {
+   "postversion": "react-native-version --never-increment-prerelease -t android && react-native-version --version-build -t ios"
  }
}
```

### Usage

Just run `npm version <newversion>`.

react-native-version will then update your `android/` and `ios/` code. Depending on the script and options you choose, it can also automatically amend the version bump commit and update the Git tag created by `npm version`. This method should be useful in most cases. If you need more control, take a look at the CLI and options below.
