# ``Swift/RegexComponent/iso8601Date(timeZone:dateSeparator:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Creates a regex component that matches an ISO 8601-formatted date string, capturing it as a Foundation date in the specified time zone.

This method matches an ISO 8601 date string using the provided date separator. This method only matches a date substring. If the source string also contains a time, this method doesn't match it. To match both date and time in an ISO 8601-formatted string, use ``Swift/RegexComponent/iso8601(timeZone:includingFractionalSeconds:dateSeparator:dateTimeSeparator:timeSeparator:)``.

The returned date's time is midnight in the provided time zone.

The following example creates a ``Swift/Regex`` that matches a date formatted with the base ISO 8601 format and dashes for date separators. It then matches this regex against a source string containing a date with this format, some whitespace, a substring, more whitespace, and a currency value.

    let iso860Source = "2022-07-14   Lemon-lime slushie      $1.99"
    let matcher = Regex {
        Capture {
            One(.iso8601Date(timeZone: TimeZone(identifier: "PST")!,
                             dateSeparator: .dash))
        }
        OneOrMore(.horizontalWhitespace)
        OneOrMore(.any)
        OneOrMore(.horizontalWhitespace)
        One(.localizedCurrency(code:Locale.Currency("USD"),
                               locale:Locale(identifier: "en_US")))
    }
    let match = iso860Source.firstMatch(of: matcher)
    let date = match?.1 // date == Jul 14, 2022 at 12:00 AM PST

- Parameters:
  - timeZone: The time zone to use when returning a captured <doc://com.apple.documentation/documentation/Foundation/Date>. The returned date's time value is `00:00:00` in this time zone.
  - dateSeparator: The character that separates year, month, and day sections of the date substring.

- Returns: A `RegexComponent` that matches ISO 8601-formatted date substrings as Foundation <doc://com.apple.documentation/documentation/Foundation/Date> instances.
