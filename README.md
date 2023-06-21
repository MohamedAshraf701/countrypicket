# Country Picker Flutter Package

[![pub package](https://img.shields.io/pub/v/country_picker.svg)](https://pub.dev/packages/country_picker)

The Country Picker Flutter package provides a simple and convenient way to select a country from a list of countries within a Flutter application.

![Country Picker Screenshot](https://raw.githubusercontent.com/Daniel-Ioannou/flutter_country_picker/master/assets/ReadMe_20Screenshot.png)

## Getting Started

To use the Country Picker package, follow these steps:

1. Add the package to your `pubspec.yaml` file:
```yaml
countrypicker: ^0.0.1
```

2. Import the package in your Dart file:
```dart
import 'package:countrypicker/countrypicker.dart';
```

3. Display the country picker using the `showCountryPicker` method:
```dart
showCountryPicker(
  context: context,
  showPhoneCode: true, // Optional: Shows the phone code before the country name.
  onSelect: (Country country) {
    print('Selected country: ${country.displayName}');
  },
);
```

### Localization Support

To enable localization support, add `CountryLocalizations.delegate` to the list of your app delegates in the `MaterialApp`:
```dart
MaterialApp(
  supportedLocales: [
    const Locale('en'),
    const Locale('el'),
    const Locale.fromSubtags(languageCode: 'zh', scriptCode: 'Hans'), // Generic Simplified Chinese 'zh_Hans'
    const Locale.fromSubtags(languageCode: 'zh', scriptCode: 'Hant'), // Generic traditional Chinese 'zh_Hant'
  ],
  localizationsDelegates: [
    CountryLocalizations.delegate,
    GlobalMaterialLocalizations.delegate,
    GlobalWidgetsLocalizations.delegate,
    GlobalCupertinoLocalizations.delegate,
  ],
  home: HomePage(),
);
```

### Parameters

The `showCountryPicker` method accepts several optional parameters to customize the behavior and appearance of the country picker:

- `onSelect`: A required callback function that is called when a country is selected. The selected country is passed as an argument to the callback.
- `onClosed`: An optional callback function that is called when the Country Picker is dismissed, whether a country is selected or not.
- `showPhoneCode`: An optional parameter that can be used to show the phone code before the country name.
- `searchAutofocus`: An optional parameter that can be used to initially focus on the search field.
- `showSearch`: An optional parameter that can be used to show or hide the search bar.
- `showWorldWide`: An optional parameter for showing a "World Wide" option at the beginning of the country list.
- `favorite`: An optional parameter that can be used to show favorite countries at the top of the country list.
- `countryListTheme`: An optional parameter that allows customization of the country list's bottom sheet and its widgets. It accepts `CountryListThemeData` object with various styling options.
- `exclude`: An optional parameter that can be used to exclude one or more countries from the country list. It takes a list of country codes (ISO2).
- `countryFilter`: An optional parameter that can be used to filter the country list. It takes a list of country codes (ISO2). Note that you cannot provide both `exclude` and `countryFilter`.

## Contributions

Contributions of any kind are more than welcome! Feel free to fork the Country Picker package, make improvements, submit pull requests, or open issues.

We appreciate your support in making the Country Picker package even better!