# ``Swift/RegexComponent``

## Topics

### Creating a regex component

- ``Swift/RegexComponent/init(_:_:)``

### Getting a regex from a component

- ``Swift/RegexComponent/regex``

### Matching substring sequences

- ``Swift/RegexComponent/anyOf(_:)-3pexl``
- ``Swift/RegexComponent/anyOf(_:)-4xgea``
- ``Swift/RegexComponent/any``
- ``Swift/RegexComponent/anyGraphemeCluster``
- ``Swift/RegexComponent/anyNonNewline``
- ``Swift/RegexComponent/digit``
- ``Swift/RegexComponent/hexDigit``
- ``Swift/RegexComponent/word``

### Matching whitespace and line endings

- ``Swift/RegexComponent/horizontalWhitespace``
- ``Swift/RegexComponent/newlineSequence``
- ``Swift/RegexComponent/verticalWhitespace``
- ``Swift/RegexComponent/whitespace``

### Matching dates and times

- ``Swift/RegexComponent/date(_:locale:timeZone:calendar:)``
- ``Swift/RegexComponent/date(format:locale:timeZone:calendar:twoDigitStartDate:)``
- ``Swift/RegexComponent/dateTime(date:time:locale:timeZone:calendar:)``
- ``Swift/RegexComponent/iso8601``
- ``Swift/RegexComponent/iso8601Date(timeZone:dateSeparator:)``
- ``Swift/RegexComponent/iso8601(timeZone:includingFractionalSeconds:dateSeparator:dateTimeSeparator:timeSeparator:)``
- ``Swift/RegexComponent/iso8601WithTimeZone(includingFractionalSeconds:dateSeparator:dateTimeSeparator:timeSeparator:timeZoneSeparator:)``

### Matching numeric formats

- ``Swift/RegexComponent/localizedInteger(locale:)``
- ``Swift/RegexComponent/localizedDouble(locale:)``
- ``Swift/RegexComponent/localizedDecimal(locale:)``
- ``Swift/RegexComponent/localizedCurrency(code:locale:)``
- ``Swift/RegexComponent/localizedIntegerCurrency(code:locale:)``
- ``Swift/RegexComponent/localizedIntegerPercentage(locale:)``
- ``Swift/RegexComponent/localizedDoublePercentage(locale:)``

### Matching URLs

- ``Swift/RegexComponent/url(scheme:user:password:host:port:path:query:fragment:)``

### Supporting types

- ``Swift/RegexComponent/RegexOutput``
- ``Swift/RegexComponent/DateStyle``
- ``Swift/RegexComponent/TimeStyle``
