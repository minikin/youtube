# Youtube macOS

Youtube macOS is Flutter cross-platform application for macOS, iOS and Android.

## Meta

**State:** development

**Point People:** [Sasha Prokhorenko](mailto:djminikin@gmail.com)

**CI:** _ci status_

---

- [Youtube macOS](#Youtube-macOS)
  - [Meta](#Meta)
  - [Requirements](#Requirements)
  - [Dependencies](#Dependencies)
  - [Installation](#Installation)
  - [Running the project](#Running-the-project)
  - [Development](#Development)
    - [Project Structure](#Project-Structure)
    - [Serialization](#Serialization)
  - [Running Tests](#Running-Tests)
  - [Deployment](#Deployment)
  - [FAQ](#FAQ)

## Requirements

- Flutter 1.9.6+ (_the latest version on master channel_)
- Dart 2.4.0
- Xcode 10.0+
- Androind Studio 3.5.0+
- iOS 11.0+ / macOS 10.13+ / Android SDK 16+
- Ruby 2.4+
- Fastlane 2.115.0+
- CocoaPods 1.7.0+
- Flutter & Dart plugins:
  - [Visual Studio Code](https://flutter.dev/docs/get-started/editor?tab=androidstudio)
  - [Android Studio / IntelliJ](https://flutter.dev/docs/get-started/editor?tab=vscode)

## Dependencies

To manage dependencies we use [Pub](https://pub.dartlang.org/).

You can add new dependencies to file [pubspec.yaml](https://github.com/minikin/youtube/blob/develop/pubspec.yaml)

## Installation

```bash
git clone https://github.com/minikin/youtube.git && cd youtube && flutter packages get
```

## Running the project

To run the app open the directory `youtube` in Visual Studio Code or Android Studio / IntelliJ, start simulator and run the project. If you want to run the app on a real iOS device instead of the simulator, you will need the Provisioning Profile.

## Development

### Project Structure

In the project folder, there are a few important files and directories :

- `lib`: This is the main directory with source files.
- `pubspec.yaml`: This file contains all the third party dependencies. Read more about [pub](https://pub.dartlang.org).
- `analysis_options.yaml`: Configuration file for [dartfm](https://github.com/dart-lang/dart_style#readme) that has rules on code linting and style. Read [Effective Dart](https://www.dartlang.org/guides/language/effective-dart).
- `macOS` folder: Contains Xcode project to build macOS app
- `ios` folder: Contains Xcode project to build iOS app.
- `android` folder: Contains Android Studio project.
- `assets` folder: Contains assets used in the app i.e. images, fonts, html etc.
- `test` folder: Contains the app test files and mocks.
- `coverage` folder: Contains test coverage results.
- `scripts` folder: Contains a few simple scripts that are used to automate things during the build process.

### Serialization

To reduce amount of boilerplate code we use `built_value` and `built_collection` with `build_runner` and `built_value_generator`.

If you need to add a new model or update existing one **do not forget** to run:

```bash
flutter packages pub run build_runner build
```

OR

```bash
flutter packages pub run build_runner watch
```

Read more about `built_value` and `built_collection`:

[Dart’s built_value for Immutable Object Models](https://medium.com/dartlang/darts-built-value-for-immutable-object-models-83e2497922d4)

[Dart’s built_collection for Immutable Collections](https://medium.com/dartlang/darts-built-collection-for-immutable-collections-db662f705eff)

[Moving Fast with Dart Immutable Values](https://medium.com/dartlang/moving-fast-with-dart-immutable-values-1e717925fafb)

[Dart’s built_value for Serialization](https://medium.com/dartlang/darts-built-value-for-serialization-f5db9d0f4159)

[Building a Chat App in Dart](https://medium.com/dartlang/building-a-chat-app-in-dart-815fcd0e5a31)

## Running Tests

To run test:

```sh
flutter test
```

To run and collect test coverage:

```sh
flutter test --coverage && genhtml coverage/lcov.info -o coverage/output/
```

## Deployment

## FAQ
