# ``Swift/Duration/UnitsFormatStyle/FractionalPartDisplayStrategy/encode(to:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Encodes this value into the given encoder.

If the value fails to encode anything, `encoder` encodes an empty keyed container in its place.
This function throws an error if any values are invalid for the given encoder’s format.

- Parameter encoder: The encoder to write data to.
