# ``Swift/RegexComponent/iso8601``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

A regex component that matches a default ISO 8601-formatted date string, capturing it as a Foundation date.

This property matches date substrings in accordance with the formatting of Foundation's <doc://com.apple.documentation/documentation/Foundation/Date/ISO8601FormatStyle>. This matches the default format of the ISO 8601 format style.

The following example creates a ``Swift/Regex`` that matches a date formatted with the base ISO 8601 format. It then matches this regex against a source string containing a date and time with this format (using the default UTC time zone, which `Z` indicates), some whitespace, a substring, more whitespace, and a currency value.

    let iso860Source = "2022-07-14T21:10:15Z   Lemon-lime slushie      $1.99"
    let matcher = Regex {
        Capture {
            One(.iso8601)
        }
        OneOrMore(.horizontalWhitespace)
        OneOrMore(.any)
        OneOrMore(.horizontalWhitespace)
        One(.localizedCurrency(code:Locale.Currency("USD"),
                               locale:Locale(identifier: "en_US")))
    }
    let match = iso860Source.firstMatch(of: matcher)
    let date = match?.1 // date == Jul 14, 2022 at 2:10 PM PST
