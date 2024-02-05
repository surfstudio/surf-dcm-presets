# Surf DCM Presets

[![Build Status](https://shields.io/github/actions/workflow/status/surfstudio/flutter-surf-logger/main.yml?logo=github&logoColor=white)](https://github.com/surfstudio/surf-dcm-presets)
[![Coverage Status](https://img.shields.io/codecov/c/github/surfstudio/surf-dcm-presets?logo=codecov&logoColor=white)](https://app.codecov.io/gh/surfstudio/surf-dcm-presets)
[![Pub Version](https://img.shields.io/pub/v/surf_dcm_presets?logo=dart&logoColor=white)](https://pub.dev/packages/surf_dcm_presets)
[![Pub Likes](https://badgen.net/pub/likes/surf_dcm_presets)](https://pub.dev/packages/surf_dcm_presets)
[![Pub popularity](https://badgen.net/pub/popularity/surf_dcm_presets)](https://pub.dev/packages/surf_dcm_presets/score)
![Flutter Platform](https://badgen.net/pub/flutter-platform/surf_dcm_presets)

## Description

This repository contains a list of pre-set presets for DCM that are used on Surf projects:

- **All:** contains all available lint rules for Dart and Flutter.
- **Dart:** contains all lint rules applicable to any Dart app.
- **Flutter:** contains all lint rules applicable to any Flutter app.
- **Recommended:** contains recommended Dart and Flutter rules.
- **Provider:** contains all lint rules for the Provider package.
- **Intl:** contains all lint rules for the Intl package.
- **Pub:** contains all lint rules for linting the `pubspec.yaml` files.

## How to use a preset

Take these steps to enable a preset:

1. Install this package as a dev dependency:

   ```terminal
   dart pub add --dev surf_dcm_presets
   ```

   or:

   ```terminal
   flutter pub add --dev surf_dcm_presets
   ```

2. For DCM configuration add the `extents` entry:

   ```yaml
   dart_code_metrics:
     extends:
       - package:surf_dcm_presets/all.yaml
   ```

## Disabling or reconfiguring a rule from the preset

To disable a rule, simply set its value to false:

```yaml
dart_code_metrics:
  extends:
    - package:surf_dcm_presets/all.yaml
  rules:
    - avoid-banned-imports: false
```

To reconfigure a rule, that is included into a preset:

```yaml
dart_code_metrics:
  extends:
    - package:surf_dcm_presets/all.yaml
  rules:
    - arguments-ordering:
        child-last: true
```

## Defining a custom preset

Any other preset can be passed to the `extends` entry. To create a custom preset create a `yaml` file with the same structure as for regular [DCM configuration](https://dcm.dev/docs/configuration/).