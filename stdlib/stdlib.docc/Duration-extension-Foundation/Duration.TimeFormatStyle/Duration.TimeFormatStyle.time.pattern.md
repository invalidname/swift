# ``Swift/Duration/TimeFormatStyle/time(pattern:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Creates a time format style using the provided pattern, from a type method.

Use this convenience factory function in situations that expect a ``Swift/Duration/TimeFormatStyle``, such as ``Swift/Duration/formatted(_:)``, as an alternative to using the full initializer.

- Parameters:
  - pattern: A `Pattern` that specifies the units to include in the displayed string and the behavior of the units.
