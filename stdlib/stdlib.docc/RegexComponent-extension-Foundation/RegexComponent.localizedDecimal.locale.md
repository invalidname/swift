# ``Swift/RegexComponent/localizedDecimal(locale:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Creates a regex component that matches a localized decimal string, capturing it as a Foundation decimal.

This method matches decimal substrings in accordance with the provided locale. For example, the value `1234567890.1234` formats as `1,234,567,890.1234` in the `en_US` locale, as `1 234 567 890,1234` in the `FR` locale, and as `1234567890.1234` in the `JP` locale. Because of this, the regex needs to know what locale convention to match against.

The following example creates a ``Swift/Regex`` that matches a date and time followed by whitespace and a decimal formatted in the `en_US` locale. It then matches this regex against a source string containing a date with this format, some whitespace, and a decimal value.

    let enUSLocale = Locale(languageCode: .english, languageRegion: .unitedStates)
    let source = "7/31/2022, 5:15:12 AM  1,234,567,890.1234"
    let matcher = Regex {
        One(.dateTime(date: .numeric,
                      time: .standard,
                      locale: enUSLocale,
                      timeZone: TimeZone(identifier: "PST")!))
        OneOrMore(.horizontalWhitespace)
        Capture {
            One(.localizedDecimal(locale: enUSLocale))
        }
    }
    guard let match = source.firstMatch(of: matcher) else { return }
    let decimal = match.1 // decimal == 1234567890.1234

- Parameters:
  - locale: The locale that specifies formatting conventions to use when matching decimal strings.
  
- Returns: A `RegexComponent` that matches localized decimal substrings as Foundation <doc://com.apple.documentation/documentation/Foundation/Decimal> instances.
