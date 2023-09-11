# Kinde React Native 0.7x generator

The generator for the [Kinde React Native 0.7x SDK](https://github.com/kinde-oss/kinde-react-native-sdk-0-7x).

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](https://makeapullrequest.com) [![Kinde Docs](https://img.shields.io/badge/Kinde-Docs-eee?style=flat-square)](https://kinde.com/docs/developer-tools) [![Kinde Community](https://img.shields.io/badge/Kinde-Community-eee?style=flat-square)](https://thekindecommunity.slack.com)

## Overview

This generator creates an SDK in React Native 0.7x that can authenticate to Kinde using the Authorization Code grant or the Authorization Code with PKCE grant via the [OAuth 2.0 protocol](https://oauth.net/2/) 

Also, see the SDKs section in Kinde’s [contributing guidelines](https://github.com/kinde-oss/.github/blob/main/.github/CONTRIBUTING.md).

## Usage

### Requirements

- Java [Link to download](https://www.java.com/en/)

### Initial set up

1. Clone the repository to your machine:

   ```bash
   git clone https://github.com/kinde-oss/kinde-react-native-generator-0-7x
   ```

2. Go into the project:

   ```bash
   cd kinde-react-native-generator-0-7x
   ```

### SDK generation

Run the following command to generate the SDK:

```bash
make clean
make build-react-native
```

The SDK gets outputted to: `./out/kinde-react-native-sdk`, which you can enter via:

```bash
cd out/kinde-react-native-sdk
```

## SDK documentation

[React Native 0.7x SDK](https://kinde.com/docs/developer-tools/react-native-sdk/)

## Development
#### Add the SDK to your existing project
- To add the SDK in an already existing project, you must first compile the SDK package:
  ```bash
  git init && npm install
  npm run build
  ```
- Next, go to the project's root directory:
  ```bash
  npm pack <path-to-generator-folder>/out/kinde-react-native-sdk
  ```
- Update the `package.json` file
  ```json
  {
    ...
    "dependencies": {
      "@kinde-oss/react-native-sdk-0-7x": "file:kinde-oss-react-native-sdk-0-7x-<version>.tgz",
      ...
    }
    ...
  }
  ```
#### Regenerate the SDK
When you modify the SDK, it is essential to update the template files to regenerate the SDK:
- Mustache files: `/generators/react-native/src/main/resources/react-native`
- Generator file: `generators/react-native/src/main/java/com/kinde/codegen/KindeReactNativeGenerator.java`

## Contributing

Please refer to Kinde’s [contributing guidelines](https://github.com/kinde-oss/.github/blob/489e2ca9c3307c2b2e098a885e22f2239116394a/CONTRIBUTING.md).

## License

By contributing to Kinde, you agree that your contributions will be licensed under its MIT License.