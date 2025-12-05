# ``Swift/assertionFailure(_:file:line:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Indicates that an internal consistency check failed.

This function's effect varies depending on the build flag used:

* In playgrounds and `-Onone` builds (the default for Xcode's Debug
  configuration), stop program execution in a debuggable state after
  printing `message`.

* In `-O` builds, has no effect.

* In `-Ounchecked` builds, the optimizer may assume that this function is
  never called. Failure to satisfy that assumption is a serious
  programming error.

- Parameters:
  - message: A string to print in a playground or `-Onone` build. The
    default is an empty string.
  - file: The file name to print with `message`. The default is the file
    where `assertionFailure(_:file:line:)` is called.
  - line: The line number to print along with `message`. The default is the
    line number where `assertionFailure(_:file:line:)` is called.
