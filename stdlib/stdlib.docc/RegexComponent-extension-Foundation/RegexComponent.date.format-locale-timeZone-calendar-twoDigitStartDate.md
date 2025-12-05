# ``Swift/RegexComponent/date(format:locale:timeZone:calendar:twoDigitStartDate:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Creates a regex component that matches a localized date string formatted in accordance with a format string, capturing it as a Foundation date.

This method matches date substrings in accordance with a format from a <doc://com.apple.documentation/documentation/Foundation/Date/FormatString>.

If a time value follows the date substring, the matcher ignores it, treating it as any other character sequence. To match date and time substrings, use ``Swift/RegexComponent/dateTime(date:time:locale:timeZone:calendar:)``.

If the date substring uses a two-digit year, the matcher uses the `twoDigitStartDate` parameter, which defines the earliest date a string with a two-digit year can denote. The matcher ignores this parameter if the year contains more than two digits.

The following example creates a ``Swift/Regex`` that matches a date formatted with two-digit month, day, and year fields, and slash (`/`) separator characters. It sets midnight on January 1, 1970, as the `twoDigitStartDate`, and `PST` as the time zone. It then matches this regex against a source string containing a date with this format and a two-digit year, some whitespace, a substring, more whitespace, and a currency value. Because the source year `76` is after `thetwoDigitStartDate`, the date substring matches as `1976`.

    let enUSLocale = Locale(languageCode: .english, languageRegion: .unitedStates)
    let source = "4/1/76  Lemon-lime slushie      $0.40"
    let matcher = Regex {
        Capture {
            One(.date(format: "\(month: .twoDigits)/\(day: .twoDigits)/\(year: .twoDigits)",
                      locale: enUSLocale,
                      timeZone: TimeZone(identifier: "PST")!,
                      twoDigitStartDate: try! Date("1970-01-01T00:00:00-0800", strategy: .iso8601)))
        }
        OneOrMore(.horizontalWhitespace)
        OneOrMore(.any)
        OneOrMore(.horizontalWhitespace)
        One(.localizedCurrency(code: Locale.Currency("USD"),
                               locale: enUSLocale))
    }

    let match = source.firstMatch(of: matcher)
    let date = match?.1 // date == Mar 1, 1976 at 12:00 AM (may vary based on current locale)

- Parameters:
  - format: A <doc://com.apple.documentation/documentation/Foundation/Date/FormatString> to use when matching date substrings. 
  - locale: The locale to use when matching date substrings. Matching uses this locale to evaluate the order of date components. It also uses the locale's language for date format styles that use words.
  - timeZone: The time zone to use when returning a captured <doc://com.apple.documentation/documentation/Foundation/Date>. The returned date's time value is `00:00:00` in this time zone.
  - calendar: The calendar to use when matching date substrings. If `nil`, matching uses the default calendar of the specified `locale`.
  - twoDigitStartDate: The earliest date a matched two-year date can represent. For example, with the default value of `Date(timeIntervalSince1970: 0)`, the matcher treats `22` as 2022, and `84` as 1984. The matcher ignores this parameter for date substrings that contain year components with more than two digits.
  
- Returns: A `RegexComponent` that matches date substrings as Foundation <doc://com.apple.documentation/documentation/Foundation/Date> instances.
