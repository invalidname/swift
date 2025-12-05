# ``Swift/RegexComponent/localizedDoublePercentage(locale:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Creates a regex component that matches a localized percentage string, capturing it as a double-precision floating-point value.

This method matches percentage substrings in accordance with the provided locale. For example, in the `en_US` locale, `0.75` formats as `75%`, and `12345.67` formats as `1,234,567%`. Other locales use different separators, or omit them entirely. Because of this, the regex needs to know what locale convention to match against.

The following example creates a ``Swift/Regex`` that matches a date and time followed by whitespace and a percentage string formatted in the `en_US` locale. It then matches this regex against a source string containing a date with this format, some whitespace, and a percentage string.

    let enUSLocale = Locale(languageCode: .english, languageRegion: .unitedStates)
    let source = "7/31/2022, 5:15:12 AM  75.3%"
    let matcher = Regex {
        One(.dateTime(date: .numeric,
                      time: .standard,
                      locale: enUSLocale,
                      timeZone: TimeZone(identifier: "PST")!))
        OneOrMore(.horizontalWhitespace)
        Capture {
            One(.localizedDoublePercentage(locale: enUSLocale))
        }
    }
    guard let match = source.firstMatch(of: matcher) else { return }
    let percentage = match.1 // percentage == 0.753

- Parameters:
  - locale: The locale that specifies formatting conventions to use when matching percentage strings.
  
- Returns: A `RegexComponent` that matches localized percentage substrings as ``Swift/Double`` instances.
