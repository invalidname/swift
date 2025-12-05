# ``Swift/RegexComponent/date(_:locale:timeZone:calendar:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Creates a regex component that matches a localized date string formatted in accordance with a style, capturing it as a Foundation date.

This method matches date substrings in accordance with the formatting of Foundation's <doc://com.apple.documentation/documentation/Foundation/Date/FormatStyle>.

If a time value follows the date substring, the matcher ignores it, treating it as any other character sequence. To match date and time substrings, use ``Swift/RegexComponent/dateTime(date:time:locale:timeZone:calendar:)``.

The following example creates a ``Swift/Regex`` that matches a date formatted with the <doc://com.apple.documentation/documentation/foundation/date/formatstyle/datestyle/numeric> style in the `en_US` locale. It then matches this regex against a source string containing a date with this format, some whitespace, a substring, more whitespace, and a currency value.

    let source = "7/31/2022  Lemon-lime slushie      $1.99"
    let matcher = Regex {
        Capture {
            One(.date(.numeric,
                      locale: Locale(identifier: "en_US"),
                      timeZone: TimeZone(identifier: "PST")!))
        }
    }
    guard let match = source.firstMatch(of: matcher) else { return }
    let date = match.1 // date == Jul 31, 2022 at 12:00 AM PST

- Parameters:
  - style: A <doc://com.apple.documentation/documentation/Foundation/Date/FormatStyle/DateStyle> to use when matching date substrings.
  - locale: The locale to use when matching date substrings. Matching uses this locale to evaluate the order of date components. It also uses the locale's language for date format styles that use words.
  - timeZone: The time zone to use when returning a captured <doc://com.apple.documentation/documentation/Foundation/Date>. The returned date's time value is `00:00:00` in this time zone.
  - calendar: The calendar to use when matching date substrings. If `nil`, matching uses the default calendar of the specified `locale`.
  
- Returns: A `RegexComponent` that matches date substrings as Foundation <doc://com.apple.documentation/documentation/Foundation/Date> instances.
