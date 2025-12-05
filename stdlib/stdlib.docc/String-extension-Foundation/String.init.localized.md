# ``Swift/String/init(localized:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Creates a localized string from a localized string resource.

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

If you don't need the deferred-loading behavior of `LocalizedStringResource`, use ``Swift/String/init(localized:table:bundle:locale:comment:)`` instead. If you prefer to use an arbitrary localization key rather than the localized string in the development language, use ``Swift/String/init(localized:defaultValue:table:bundle:locale:comment:)``.

- Parameters:
  - resource: A `LocalizedStringResource` that provides the localization key, table, bundle, and locale.
