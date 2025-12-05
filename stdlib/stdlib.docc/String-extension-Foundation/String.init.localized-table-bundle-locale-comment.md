# ``Swift/String/init(localized:table:bundle:locale:comment:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Creates a localized string from an interpolated string.

Use this initializer when the development-language string serves as your localization key. You can use a fixed string for the key or a string that the system interpolates from values you provide at runtime. For example, if your app's strings catalog contains a localizable entry for ` “Hello, %@.”`, you create a localized string like the following:

```` swift
// Assume the strings file or catalog contains "Hello, %@." for English
// and "Bonjour, %@." for French.
let userName = "Juan"
let greeting = String(localized: "Hello, \(userName).")
// greeting == "Hello, Juan." in en locale, "Bonjour, Juan." in fr locale.
````

If you prefer to use an arbitrary localization key rather than the localized string in the development language, use ``Swift/String/init(localized:defaultValue:table:bundle:locale:comment:)``. If you need to provide localized strings to another process that might be using a different locale, use ``Swift/String/init(localized:)``.

- Parameters:
  - keyAndValue: A ``Swift/String/LocalizationValue`` that provides the localization key to look up. This parameter also serves as the default value if the system can't find a localized string.
  - table: The bundle’s string table to search. If `table` is `nil` or is an empty string, the method attempts to use the table named `Localizable`. The default is `nil`.
  - bundle: The bundle to use for looking up strings. If `nil`, an app searches its main bundle. The default is `nil`.
  - locale: The locale to use when localizing interpolated values, such as numbers. This doesn't change which locale the system uses to look up the localized string. If `nil`, this initializer uses the current locale. The default is `nil`.
  - comment: The comment to place above the key-value pair in the strings file. This parameter provides the translator with some context about the localized string’s presentation to the user.
