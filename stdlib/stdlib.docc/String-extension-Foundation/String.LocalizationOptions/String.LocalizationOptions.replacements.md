# ``Swift/String/LocalizationOptions/replacements``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

An array of replacement options.

Use this proprty when providing replacement values to localizable strings that use the `\(placeholder: )` syntax. You can then initialize localized strings with the following `String` initializers:

* With a ``Swift/String/LocalizationValue``: ``Swift/String/init(localized:options:table:bundle:locale:comment:)``
* With a Foundation `LocalizedStringResource`: ``Swift/String/init(localized:options:)``
* With a ``Swift/StaticString`` that serves as an arbitary localization key: ``Swift/String/init(localized:defaultValue:options:table:bundle:locale:comment:)``

The string interpolation that inserts the placeholder value takes an argument that represents the type of the replacement value. The following example inserts an ``Int`` value into the placeholder position.

``` swift
// Assume the strings file or catalog contains "Position in queue: %lld."
// for English and "Position dans la file d’attente: %lld." for French.
var options = String.LocalizationOptions()
options.replacements = [12]
let queueMessage = String (localized: "Position in queue: \(placeholder: .int).",
                           options: options)
// queueMessage == "Position in queue: 12." in en locale, "Position dans la file d’attente: 12." in fr locale.
```

Foundation looks up the localized string from the app's strings file or string catalog. For multiple replacements, provide the replacement values in the order of their placeholders in the development language. Localizers can change the word order as needed for the desired language. The following example shows this syntax with a ``String/LocalizationValue``.

``` swift
// Assuming strings file or catalog contains the following entries for "%@’s %@":
// English: "%1$@’s %2$@"
// French: "%2$@ de %1$@"
let replaceable = String.LocalizationValue(
    "\(placeholder: .object)’s \(placeholder: .object)")
var options = String.LocalizationOptions()
options.replacements = ["Anne", "iPad"]
let localized =  String(localized: replaceable,
                        options: options)
// In English locale: localized == "Anne’s iPad"
// In French locale: localized ==  "iPad de Anne"
```

Use this same `\(placeholder:)` syntax for reordered replacements when your localization string is a `LocalizedStringResource` or a ``Swift/StaticString`` that represents an arbitary localization key.

Populate this array with the same number of values that the format string requires, matching the type of each replacement. If this array contains too few replacements or if the types of the replacements do not match the placeholders, Foundation substitutes reasonable default values. These replacements include `0` for integers and `"(null)"` for objects.
