# ``Swift/RegexComponent/iso8601(timeZone:includingFractionalSeconds:dateSeparator:dateTimeSeparator:timeSeparator:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Creates a regex component that matches an ISO 8601-formatted date string, capturing the matched substring as a Foundation date in the specified time zone.

This method matches an ISO 8601 date string using the provided separator characters. It doesn't look for a time zone in the source string, and the match doesn't include time zone characters if they're present. Instead, the matcher interprets the string as being in the provided `timeZone`.

The following example creates a ``Swift/Regex`` that matches an ISO 8601-formatted date. The format looks for a dash for the date separator, the standard date/time separator (none), and a colon for the time separator. It also interprets the source string as being in the current time zone. The example then matches this regex against a source string containing a date with this format, some whitespace, a substring, more whitespace, and a currency value.

    let iso860Source = "2022-07-14T21:10:15   Lemon-lime slushie      $1.99"
    let matcher = Regex {
        Capture {
            One(.iso8601(timeZone: .current,
                         includingFractionalSeconds: false,
                         dateSeparator: .dash,
                         dateTimeSeparator: .standard,
                         timeSeparator: .colon))
        }
        OneOrMore(.horizontalWhitespace)
        OneOrMore(.any)
        OneOrMore(.horizontalWhitespace)
        One(.localizedCurrency(code:Locale.Currency("USD"),
                                   locale:Locale(identifier: "en_US")))
    }
    let match = iso860Source.firstMatch(of: matcher)
    let date = match?.1 // date == Jul 14, 2022 at 9:10 PM (may vary depending on current locale)

- Parameters:
  - timeZone: The time zone to use when returning a captured <doc://com.apple.documentation/documentation/Foundation/Date>. The returned date's time value is `00:00:00` in this time zone.
  - includingFractionalSeconds: A Boolean value that specifies whether the source string contains fractional seconds. The default is `false`.
  - dateSeparator: The character that separates year, month, and day sections of the date substring. The default is <doc://com.apple.documentation/documentation/foundation/date/iso8601formatstyle/dateseparator-swift.enum/dash>.
  - dateTimeSeparator: The character that separates the date and time sections of the substring. The default is <doc://com.apple.documentation/documentation/foundation/date/iso8601formatstyle/datetimeseparator-swift.enum/standard>.
  - timeSeparator: The character that separates the date and time sections of the substring. The default is <doc://com.apple.documentation/documentation/foundation/date/iso8601formatstyle/timeseparator-swift.enum/colon>.

- Returns: A `RegexComponent` that matches ISO 8601-formatted date substrings as Foundation <doc://com.apple.documentation/documentation/Foundation/Date> instances.
