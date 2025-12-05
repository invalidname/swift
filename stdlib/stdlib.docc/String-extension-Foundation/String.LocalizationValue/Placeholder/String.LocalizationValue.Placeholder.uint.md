# ``Swift/String/LocalizationValue/Placeholder/uint``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

The unsigned integer type, as used for replacement values with the localized string placeholder syntax.

To insert an unsigned integer into a placeholder, use the syntax `\(placeholder: .uint)`.

The various `String(localized:)` initializers apply a locale-appropriate `FormatStyle` to the numeric value, based on the `locale:` parameter or the `LocalizedStringResource`.
