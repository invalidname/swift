# ``Swift/RegexComponent/localizedInteger(locale:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Creates a regex component that matches a localized numeric string, capturing it as an integer value.

This method matches decimal substrings in accordance with the provided locale. For example, the value `1234567890` formats as `1,234,567,890` in the `en_US` locale, as `1 234 567 890` in the `FR` locale, and as `1234567890` in the `JP` locale. Because of this, the regex needs to know what locale convention to match against.

The following example creates a ``Swift/Regex`` that matches a date and time followed by whitespace and an integer formatted in the `en_US` locale. It then matches this regex against a source string containing a date with this format, some whitespace, and an integer value.

    let enUSLocale = Locale(languageCode: .english, languageRegion: .unitedStates)
    let source = "7/31/2022, 5:15:12 AM  49,525"
    let matcher = Regex {
        One(.dateTime(date: .numeric,
                      time: .standard,
                      locale: enUSLocale,
                      timeZone: TimeZone(identifier: "PST")!))
        OneOrMore(.horizontalWhitespace)
        Capture {
            One(.localizedInteger(locale: enUSLocale))
        }
    }
    guard let match = source.firstMatch(of: matcher) else { return }
    let matchedInteger = match?.1 // matchedInteger == 49525

- Parameters:
  - locale: The locale that specifies formatting conventions to use when matching numeric strings.
  
- Returns: A `RegexComponent` that matches localized substrings as ``Swift/Int`` instances.
