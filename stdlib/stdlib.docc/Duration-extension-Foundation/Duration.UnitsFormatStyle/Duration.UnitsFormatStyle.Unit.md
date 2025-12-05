# ``Swift/Duration/UnitsFormatStyle/Unit``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

A unit to use in formatting a duration.

Supported units range from hours to nanoseconds. Use these with the `allowed` parameter of the ``Duration/UnitsFormatStyle/`` initializers to specify which units to use in a formatted string.

## Topics

### Duration units

- ``Swift/Duration/UnitsFormatStyle/Unit/hours``
- ``Swift/Duration/UnitsFormatStyle/Unit/minutes``
- ``Swift/Duration/UnitsFormatStyle/Unit/seconds``
- ``Swift/Duration/UnitsFormatStyle/Unit/milliseconds``
- ``Swift/Duration/UnitsFormatStyle/Unit/microseconds``
- ``Swift/Duration/UnitsFormatStyle/Unit/nanoseconds``

### Encoding and decoding

- ``Swift/Duration/UnitsFormatStyle/Unit/init(from:)``
- ``Swift/Duration/UnitsFormatStyle/Unit/encode(to:)``

### Hashing

- ``Swift/Duration/UnitsFormatStyle/Unit/hashValue``
- ``Swift/Duration/UnitsFormatStyle/Unit/hash(into:)``

### Comparing units

- ``Swift/Duration/UnitsFormatStyle/Unit/==(_:_:)``
