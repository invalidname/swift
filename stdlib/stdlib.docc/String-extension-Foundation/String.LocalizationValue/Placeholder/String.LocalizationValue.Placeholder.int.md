# ``Swift/String/LocalizationValue/Placeholder/int``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

The signed integer type, as used for replacement values with the localized string placeholder syntax.

To insert a signed integer into a placeholder, use the syntax `\(placeholder: .int)`.

The various `String(localized:)` initializers apply a locale-appropriate `FormatStyle` to the numeric value, based on the `locale:` parameter or the `LocalizedStringResource`.
