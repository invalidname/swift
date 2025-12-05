# ``Swift/RegexComponent/dateTime(date:time:locale:timeZone:calendar:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Creates a regex component that matches a localized date and time string, capturing it as a Foundation date.

This method matches date substrings in accordance with the formatting of Foundation's <doc://com.apple.documentation/documentation/Foundation/Date/FormatStyle>. If your source contains only a date or a time, use the `.omitted` value for the `date` or `time` style parameter to ignore the missing part.

The following example creates a ``Swift/Regex`` that matches a date and time formatted with the <doc://com.apple.documentation/documentation/foundation/date/formatstyle/datestyle/numeric> style in the `en_US` locale. It then matches this regex against a source string containing a date with this format, some whitespace, a substring, more whitespace, and a currency value.

    let enUSLocale = Locale(languageCode: .english, languageRegion: .unitedStates)
    let source = "7/31/2022, 5:15:12 PM  Lemon-lime slushie      $1.99"
    let matcher = Regex {
        Capture {
            One(.dateTime(date: .numeric,
                          time: .standard,
                          locale: enUSLocale,
                          timeZone: TimeZone(identifier: "PST")!))
        }
        OneOrMore(.horizontalWhitespace)
        OneOrMore(.any)
        OneOrMore(.horizontalWhitespace)
        One(.localizedCurrency(code: Locale.Currency("USD"),
                               locale: enUSLocale))
    }

    guard let match = source.firstMatch(of: matcher) else { return }
    let date = match.1 // date == Jul 31, 2022 at 5:15 PM PST

- Parameters:
  - date: A <doc://com.apple.documentation/documentation/Foundation/Date/FormatStyle/DateStyle> to use when matching date substrings. Pass <doc://com.apple.documentation/documentation/foundation/date/formatstyle/datestyle/omitted> to match a time-only substring.
  - time: A <doc://com.apple.documentation/documentation/Foundation/Date/FormatStyle/TimeStyle> to use when matching time substrings. Pass <doc://com.apple.documentation/documentation/foundation/date/formatstyle/timestyle/omitted> to match a date-only substring.
  - locale: The locale to use when matching date substrings. Matching uses this locale to evaluate the order of date components. It also uses the locale's language for date format styles that use words.
  - timeZone: The time zone to use when capturing the date and time values. The regex component ignores this parameter if the source string contains a time zone substring that the format style supports.
  - calendar: The calendar to use when matching date substrings. If `nil`, matching uses the default calendar of the specified `locale`.
  
- Returns: A `RegexComponent` that matches date substrings as Foundation <doc://com.apple.documentation/documentation/Foundation/Date> instances.
