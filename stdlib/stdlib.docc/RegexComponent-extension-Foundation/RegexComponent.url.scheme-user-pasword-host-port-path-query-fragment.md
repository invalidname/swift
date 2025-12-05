# ``Swift/RegexComponent/url(scheme:user:password:host:port:path:query:fragment:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Creates a regex component that matches a URL substring, capturing it as a Foundation URL.

All the parameters to this method take a <doc://com.apple.documentation/documentation/foundation/url/parsestrategy/componentparsestrategy> value to configure the matching behavior for one component of the URL. The three possible values are:

* <doc://com.apple.documentation/documentation/foundation/url/parsestrategy/componentparsestrategy/required> --- The URL component needs to be present for matching to succeed.
* <doc://com.apple.documentation/documentation/Foundation/URL/ParseStrategy/ComponentParseStrategy/optional> --- The URL component doesn't need to be present for matching to succeed.
* <doc://com.apple.documentation/documentation/foundation/url/parsestrategy/componentparsestrategy/defaultvalue(_:)> --- If the URL component is absent, the captured URL contains the provided default value for the component.

The following example creates a ``Swift/Regex`` that matches a URL, when it contains a scheme and a host. It then matches against a source string that contains a date formatted in the `en_US` locale, some whitespace, and a valid URL. The regex defines a default value for the port with
<doc://com.apple.documentation/documentation/foundation/url/parsestrategy/componentparsestrategy/defaultvalue(_:)>, and because the source URL doesn't include a port, the captured URL adds it.

    let source = "7/31/2022, 5:15:12 AM  https://www.example.com/productList?query=slushie"
    let matcher = Regex {
        One(.dateTime(date: .numeric,
                      time: .standard,
                      locale: Locale(identifier: "en_US"),
                      timeZone: TimeZone(identifier: "PST")!))
        OneOrMore(.horizontalWhitespace)
        Capture {
            One(.url(scheme: .required,
                     user: .optional,
                     password: .optional,
                     host: .required,
                     port: .defaultValue(8088),
                     path: .optional,
                     query: .optional,
                     fragment: .optional))
        }
    }
    guard let match = source.firstMatch(of: matcher) else { return }
    let url = match.1 // url = https://www.example.com:8088/productList?query=slushie

- Parameters:
  - scheme: A <doc://com.apple.documentation/documentation/Foundation/URL/ParseStrategy/ComponentParseStrategy> for matching the URL scheme component.
  - user: A <doc://com.apple.documentation/documentation/Foundation/URL/ParseStrategy/ComponentParseStrategy> for matching the user component.
  - password: A <doc://com.apple.documentation/documentation/Foundation/URL/ParseStrategy/ComponentParseStrategy> for matching the password component.
  - host: A <doc://com.apple.documentation/documentation/Foundation/URL/ParseStrategy/ComponentParseStrategy> for matching the host component.
  - port: A <doc://com.apple.documentation/documentation/Foundation/URL/ParseStrategy/ComponentParseStrategy> for matching the port component.
  - path: A <doc://com.apple.documentation/documentation/Foundation/URL/ParseStrategy/ComponentParseStrategy> for matching the path component.
  - query: A <doc://com.apple.documentation/documentation/Foundation/URL/ParseStrategy/ComponentParseStrategy> for matching the query component.
  - fragment: A <doc://com.apple.documentation/documentation/Foundation/URL/ParseStrategy/ComponentParseStrategy> for matching the fragment component.
  
- Returns: A `RegexComponent` that matches a URL.
