# ``Swift/String/LocalizationValue``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

A reference to a localizable string, with optional string interpolation.

Use this type when the localization key is the localized string value in the development language.  This type also supports creating localized strings that depend on a value you provide at runtime. For example, if your app's strings catalog contains a localizable entry for `"Hello, \(userName)."`, you create a localized string like the following:

```` swift
    let greeting = String(localized: "Hello, \(userName).")
````

If you want to use an arbitary string as your localization key, use ``Swift/String`` initializers that take a ``Swift/StaticString`` and a `defaultValue` parameter, like ``Swift/String/init(localized:defaultValue:table:bundle:locale:comment:)``
 and ``Swift/String/init(localized:defaultValue:options:table:bundle:locale:comment:)``.

If you need to provide localized strings to another process that might be using a different locale, initialize with a `LocalizedStringResource`, using ``Swift/String/init(localized:)``
 or ``Swift/String/init(localized:options:)``.

## Topics ##

### Creating a string localization value instance

- ``Swift/String/LocalizationValue/init(_:)``
- ``Swift/String/LocalizationValue/init(stringInterpolation:)``
- ``Swift/String/LocalizationValue/StringInterpolation``
- ``Swift/String/LocalizationValue/init(stringLiteral:)``

### Comparing string localization values

- ``Swift/String/LocalizationValue/==(_:_:)``

### Supporting types

- ``Swift/String/LocalizationValue/Placeholder``
- ``Swift/String/LocalizationValue/ExtendedGraphemeClusterLiteralType``
- ``Swift/String/LocalizationValue/StringLiteralType``
- ``Swift/String/LocalizationValue/UnicodeScalarLiteralType``

