# ``Swift/String/init(localized:options:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Creates a localized string from a localized string resource, applying the specified options.

Call this initializer to look up the localization that `resource` indicates from a string catalog or `strings` file in your app bundle. Alter the resource’s `locale` prior to calling this method if you want to localize this string in a different locale than the process that creates the `LocalizedStringResource`.

``` swift
// Assume the string catalog contains "Hello, world!" for English
// and "Bonjour, le monde!" for French.
var localizable = LocalizedStringResource("Hello, world!")
// Potentially using localizable in another process…
localizable.locale = Locale(identifier: "en")
let enLocalized = String(localized: localizable)
localizable.locale = Locale(identifier: "fr")
let frLocalized = String(localized: localizable)
// enLocalized == "Hello, world!"
// frLocalized == "Bonjour, le monde!"
```

Use the `options` parameter to include any replacement values to insert into the localized formatted string. The formatted string uses the syntax `\(placeholder: TYPE)` to strongly type replacement values. The following example shows how to insert strongly typed replacement values into a string:

``` swift
// Assume the strings file or catalog contains "Position in queue: %lld."
// for English and "Position dans la file d’attente: %lld." for French.
var localizable = LocalizedStringResource("Position in queue: \(placeholder: .int).")
// Potentially using localizable in another process…
var options = String.LocalizationOptions()
options.replacements = [12]
localizable.locale = Locale(identifier: "en")
let enLocalized = String (localized: localizable, options: options)
localizable.locale = Locale(identifier: "fr")
let frLocalized = String (localized: localizable, options: options)
// enLocalized == "Position in queue: 12."
// frLocalized == "Position dans la file d’attente: 12."
```

If you don't need the deferred-loading behavior of `LocalizedStringResource`, use ``Swift/String/init(localized:options:table:bundle:locale:comment:)`` instead. If you prefer to use an arbitrary localization key rather than the localized string in the development language, use ``Swift/String/init(localized:defaultValue:options:table:bundle:locale:comment:)``.

- Parameters:
  - resource: A `LocalizedStringResource` that provides the localization key, table, bundle, and locale.
  - options: A localization options instance that specifies localization options to apply, such as replacement values for formatted strings.
