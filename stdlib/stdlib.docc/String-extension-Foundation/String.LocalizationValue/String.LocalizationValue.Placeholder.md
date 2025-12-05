# ``Swift/String/LocalizationValue/Placeholder``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

An enumeration of types that can appear as a placeholder in a string interpolation.

Foundation uses this type when you create a string with the `\(placeholder: type)` syntax and supply an array of replacement values in a `String.LocalizationOptions`. Placeholders work with ``Swift/String`` initializers that take an `options:` parameter:

* ``Swift/String/init(localized:options:table:bundle:locale:comment:)``
* ``Swift/String/init(localized:options:)``
* ``Swift/String/init(localized:defaultValue:options:table:bundle:locale:comment:)``

You only use this type directly when specifying one of its enumeration cases in the placeholder syntax, like `\(placeholder: .int)`.

## Topics

### Placeholder types

- ``Swift/String/LocalizationValue/Placeholder/int``
- ``Swift/String/LocalizationValue/Placeholder/uint``
- ``Swift/String/LocalizationValue/Placeholder/float``
- ``Swift/String/LocalizationValue/Placeholder/double``
- ``Swift/String/LocalizationValue/Placeholder/object``

### Encoding and decoding

- ``Swift/String/LocalizationValue/Placeholder/init(from:)``
- ``Swift/String/LocalizationValue/Placeholder/encode(to:)``

### Hashing

- ``Swift/String/LocalizationValue/Placeholder/hash(into:)``
- ``Swift/String/LocalizationValue/Placeholder/hashValue``

### Comparing placeholder instances

- ``Swift/String/LocalizationValue/Placeholder/==(_:_:)``
