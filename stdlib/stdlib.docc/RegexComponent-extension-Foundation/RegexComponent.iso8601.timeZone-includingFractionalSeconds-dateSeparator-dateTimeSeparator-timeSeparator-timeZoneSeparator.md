# ``Swift/RegexComponent/iso8601WithTimeZone(includingFractionalSeconds:dateSeparator:dateTimeSeparator:timeSeparator:timeZoneSeparator:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Creates a regex component that matches an ISO 8601-formatted date string that includes a time zone component, capturing the matched substring as a Foundation date.

This method matches an ISO 8601 date string using the provided separator characters.

The following example creates a ``Swift/Regex`` that matches an ISO 8601-formatted date. The format looks for a dash for the date separator, the standard date/time separator (none), a colon for the time separator, and no separator for the time zone. It then matches this regex against a source string containing a date with this format (specifying a time zone five hours behind UTC), some whitespace, a substring, more whitespace, and a currency value.

    let iso860Source = "2022-07-14T21:10:15-05:00   Lemon-lime slushie      $1.99"
    let matcher = Regex {
        Capture {
            One(.iso8601WithTimeZone(includingFractionalSeconds: false,
                                     dateSeparator: .dash,
                                     dateTimeSeparator: .standard,
                                     timeSeparator: .colon,
                                     timeZoneSeparator: .omitted))
        }
        OneOrMore(.horizontalWhitespace)
        OneOrMore(.any)
        OneOrMore(.horizontalWhitespace)
        One(.localizedCurrency(code:Locale.Currency("USD"),
                               locale:Locale(identifier: "en_US")))
    }
    let match = iso860Source.firstMatch(of: matcher)
    let date = match?.1 // date == Jul 14, 2022 at 7:10 PM (may vary depending on current locale)

- Parameters:
  - includingFractionalSeconds: A Boolean value that specifies whether the source string contains fractional seconds. The default is `false`.
  - dateSeparator: The character that separates year, month, and day sections of the date substring. The default is <doc://com.apple.documentation/documentation/foundation/date/iso8601formatstyle/dateseparator-swift.enum/dash>.
  - dateTimeSeparator: The character that separates the date and time sections of the substring. The default is <doc://com.apple.documentation/documentation/foundation/date/iso8601formatstyle/datetimeseparator-swift.enum/standard>.
  - timeSeparator: The character that separates the date and time sections of the substring. The default is <doc://com.apple.documentation/documentation/foundation/date/iso8601formatstyle/timeseparator-swift.enum/colon>.
  - timeZoneSeparator: The character that separates the hour, minute, and second sections of the substring. The default is <doc://com.apple.documentation/documentation/foundation/date/iso8601formatstyle/timeseparator-swift.enum/colon>
  
- Returns: A `RegexComponent` that matches ISO 8601-formatted date substrings as Foundation <doc://com.apple.documentation/documentation/Foundation/Date> instances.
