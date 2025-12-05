# ``Swift/String``

## Topics

### Creating a String

In addition to creating a string from a single string literal, you can also create
an empty string, a string containing an existing group of characters, or a string
repeating the contents of another string.

- ``Swift/String/init(decoding:)-nm7v``
- ``Swift/String/init()``
- ``Swift/String/init(_:)-8v3fo``
- ``Swift/String/init(_:)-8og6g``
- ``Swift/String/init(_:)-1ip93``
- ``Swift/String/init(_:)-50pwi``
- ``Swift/String/init(_:)-14lv5``
- ``Swift/String/init(repeating:count:)-23xjt``
- ``Swift/String/init(repeating:count:)-11bpi``
- ``Swift/String/init(unsafeUninitializedCapacity:initializingUTF8With:)``

### Inspecting a String

- ``Swift/String/isEmpty-vc7l``
- ``Swift/String/count-7qyfb``

### Creating a String from Unicode Data

- ``Swift/String/init(_:)-8ay23``
- ``Swift/String/init(data:encoding:)``
- ``Swift/String/init(validatingUTF8:)-208fn``
- ``Swift/String/init(validating:as:)-84qr9``
- ``Swift/String/init(validating:as:)-5cw2c``
- ``Swift/String/init(utf8String:)-8qmaq``
- ``Swift/String/init(utf8String:)-3mcco``
- ``Swift/String/init(utf16CodeUnits:count:)``
- ``Swift/String/init(utf16CodeUnitsNoCopy:count:freeWhenDone:)``
- ``Swift/String/init(decoding:as:)``

### Creating a String Using Formats

- ``Swift/String/init(format:_:)``
- ``Swift/String/init(format:arguments:)``
- ``Swift/String/init(format:locale:_:)``
- ``Swift/String/init(format:locale:arguments:)``
- ``Swift/String/localizedStringWithFormat(_:_:)``

### Creating a Localized String

- ``Swift/String/init(localized:table:bundle:locale:comment:)``
- ``Swift/String/init(localized:options:table:bundle:locale:comment:)``
- ``Swift/String/LocalizationValue``
- ``Swift/String/LocalizationOptions``
- ``Swift/String/init(localized:defaultValue:table:bundle:locale:comment:)``
- ``Swift/String/init(localized:defaultValue:options:table:bundle:locale:comment:)``
- ``Swift/String/init(localized:)``
- ``Swift/String/init(localized:options:)``

### Converting Numeric Values

- ``Swift/String/init(_:radix:uppercase:)``

### Converting a C String

- ``Swift/String/init(bytes:encoding:)``
- ``Swift/String/init(bytesNoCopy:length:encoding:freeWhenDone:)``
- ``Swift/String/init(validatingCString:)-992vo``
- ``Swift/String/init(validatingCString:)-98wra``
- ``Swift/String/init(cString:)-2p84k``
- ``Swift/String/init(cString:)-6kr8s``
- ``Swift/String/init(cString:encoding:)-3h7bc``
- ``Swift/String/init(cString:encoding:)-3qgzd``
- ``Swift/String/init(decodingCString:as:)-8way7``
- ``Swift/String/decodeCString(_:as:repairingInvalidCodeUnits:)-46n2p``

### Converting Other Types to Strings

- ``Swift/String/init(_:)-1ywfq``
- ``Swift/String/init(describing:)-588wb``
- ``Swift/String/init(describing:)-hsqw``
- ``Swift/String/init(describing:)-6ttci``
- ``Swift/String/init(describing:)-67ncf``
- ``Swift/String/init(reflecting:)``

### Creating a String from a File or URL

- ``Swift/String/init(contentsOf:)``
- ``Swift/String/init(contentsOf:encoding:)``
- ``Swift/String/init(contentsOf:usedEncoding:)``
- ``Swift/String/init(contentsOfFile:)``
- ``Swift/String/init(contentsOfFile:encoding:)``
- ``Swift/String/init(contentsOfFile:usedEncoding:)``

### Writing to a File or URL

- ``Swift/String/write(_:)``
- ``Swift/String/write(to:)``

### Appending Strings and Characters

- ``Swift/String/append(_:)-4xa8f``
- ``Swift/String/append(_:)-4xi3j``
- ``Swift/String/append(contentsOf:)-oxek``
- ``Swift/String/append(contentsOf:)-9vb4t``
- ``Swift/String/append(contentsOf:)-7est5``
- ``Swift/String/append(contentsOf:)-9foms``
- ``Swift/String/reserveCapacity(_:)-1ozk3``
- ``Swift/String/+(_:_:)-655mi``
- ``Swift/String/+=(_:_:)-4pvxa``
- ``Swift/String/+(_:_:)-6h59y``
- ``Swift/String/+(_:_:)-n329``
- ``Swift/String/+(_:_:)-9fm57``
- ``Swift/String/+=(_:_:)-676gx``

### Inserting Characters

- ``Swift/String/insert(_:at:)-1uqvy``
- ``Swift/String/insert(_:at:)-88yqh``
- ``Swift/String/insert(contentsOf:at:)-rdu9``
- ``Swift/String/insert(contentsOf:at:)-4may``

### Replacing Substrings

- ``Swift/String/replaceSubrange(_:with:)-1wyxa``
- ``Swift/String/replaceSubrange(_:with:)-72947``

### Removing Substrings

- ``Swift/String/remove(at:)-4n29z``
- ``Swift/String/remove(at:)-5g0wm``
- ``Swift/String/removeAll(keepingCapacity:)-b1dr``
- ``Swift/String/removeAll(where:)``
- ``Swift/String/removeFirst()``
- ``Swift/String/removeFirst(_:)``
- ``Swift/String/removeLast()``
- ``Swift/String/removeLast(_:)``
- ``Swift/String/removeSubrange(_:)-8y51u``
- ``Swift/String/removeSubrange(_:)-8maxn``
- ``Swift/String/removeSubrange(_:)-9twng``
- ``Swift/String/filter(_:)``
- ``Swift/String/drop(while:)``
- ``Swift/String/dropFirst(_:)``
- ``Swift/String/dropLast(_:)``
- ``Swift/String/popLast()``

### Changing Case

- ``Swift/String/lowercased()``
- ``Swift/String/uppercased()``

### Comparing Strings Using Operators

Comparing strings using the equal-to operator (==) or a relational operator (like
&lt; and &gt;=) is always performed using the Unicode canonical representation, so
that different representations of a string compare as being equal.

- ``Swift/String/==(_:_:)-9812z``
- ``Swift/String/==(_:_:)-8kzxf``
- ``Swift/String/!=(_:_:)-1bb05``
- ``Swift/String/!=(_:_:)-frzf``
- ``Swift/String/_(_:_:)-1incq``
- ``Swift/String/_(_:_:)-8d1wy``
- ``Swift/String/_=(_:_:)-1ih6``
- ``Swift/String/_=(_:_:)-5y22v``
- ``Swift/String/_(_:_:)-24u5x``
- ``Swift/String/_(_:_:)-6o7qv``
- ``Swift/String/_=(_:_:)-8lyim``
- ``Swift/String/_=(_:_:)-nd86``
- ``Swift/String/~=(_:_:)``

### Comparing Characters

- ``Swift/String/elementsEqual(_:)``
- ``Swift/String/elementsEqual(_:by:)``
- ``Swift/String/starts(with:)``
- ``Swift/String/starts(with:by:)``
- ``Swift/String/lexicographicallyPrecedes(_:)``
- ``Swift/String/lexicographicallyPrecedes(_:by:)``

### Creating and Applying Differences

- ``Swift/String/applying(_:)``
- ``Swift/String/difference(from:)``
- ``Swift/String/difference(from:by:)``

### Finding Substrings

- ``Swift/String/hasPrefix(_:)``
- ``Swift/String/hasSuffix(_:)``

### Finding Characters

- ``Swift/String/contains(_:)``
- ``Swift/String/allSatisfy(_:)``
- ``Swift/String/contains(where:)``
- ``Swift/String/first(where:)``
- ``Swift/String/firstIndex(of:)``
- ``Swift/String/firstIndex(where:)``
- ``Swift/String/last(where:)``
- ``Swift/String/lastIndex(of:)``
- ``Swift/String/lastIndex(where:)``
- ``Swift/String/max()``
- ``Swift/String/max(_:_:)``
- ``Swift/String/max(by:)``
- ``Swift/String/min()``
- ``Swift/String/min(_:_:)``
- ``Swift/String/min(by:)``

### Getting Substrings

- ``Swift/String/subscript(_:)-2so14``
- ``Swift/String/subscript(_:)-4h7s3``
- ``Swift/String/subscript(_:)-4al9c``
- ``Swift/String/prefix(_:)``
- ``Swift/String/prefix(through:)``
- ``Swift/String/prefix(upTo:)``
- ``Swift/String/prefix(while:)``
- ``Swift/String/suffix(_:)``
- ``Swift/String/suffix(from:)``

### Splitting a String

- ``Swift/String/split(separator:maxSplits:omittingEmptySubsequences:)``
- ``Swift/String/split(maxSplits:omittingEmptySubsequences:whereSeparator:)``

### Getting Characters and Bytes

- ``Swift/String/subscript(_:)-lc0v``
- ``Swift/String/first``
- ``Swift/String/last``
- ``Swift/String/randomElement()``
- ``Swift/String/randomElement(using:)``

### Working with Encodings

- ``Swift/String/availableStringEncodings``
- ``Swift/String/defaultCStringEncoding``
- ``Swift/String/localizedName(of:)``
- ``Swift/String/isContiguousUTF8``
- ``Swift/String/makeContiguousUTF8()``
- ``Swift/String/withUTF8(_:)``

### Working with String Views

- ``Swift/String/unicodeScalars``
- ``Swift/String/init(_:)-2t931``
- ``Swift/String/init(_:)-11jx3``
- ``Swift/String/utf16``
- ``Swift/String/init(_:)-wbcx``
- ``Swift/String/init(_:)-expd``
- ``Swift/String/utf8``
- ``Swift/String/init(_:)-6sprj``
- ``Swift/String/init(_:)-83bub``

### Transforming a String's Characters

- ``Swift/String/compactMap(_:)``
- ``Swift/String/flatMap(_:)-i3m9``
- ``Swift/String/flatMap(_:)-6chuq``
- ``Swift/String/reduce(_:_:)``
- ``Swift/String/reduce(into:_:)``
- ``Swift/String/lazy``

### Iterating over a String's Characters

- ``Swift/String/forEach(_:)``
- ``Swift/String/enumerated()``
- ``Swift/String/makeIterator()``
- ``Swift/String/underestimatedCount-4ggs3``

### Reordering a String's Characters

- ``Swift/String/sorted()``
- ``Swift/String/sorted(by:)``
- ``Swift/String/reversed()``
- ``Swift/String/shuffled()``
- ``Swift/String/shuffled(using:)``

### Getting C Strings

- ``Swift/String/utf8CString``
- ``Swift/String/withCString(_:)``
- ``Swift/String/withCString(encodedAs:_:)``

### Working with Paths

- ``Swift/String/init(_:)-3a5mh``
- ``Swift/String/init(validatingUTF8:)-6i0in``

### Manipulating Indices

- ``Swift/String/startIndex``
- ``Swift/String/endIndex``
- ``Swift/String/index(after:)``
- ``Swift/String/formIndex(after:)``
- ``Swift/String/index(before:)``
- ``Swift/String/formIndex(before:)``
- ``Swift/String/index(_:offsetBy:)``
- ``Swift/String/index(_:offsetBy:limitedBy:)``
- ``Swift/String/formIndex(_:offsetBy:)``
- ``Swift/String/formIndex(_:offsetBy:limitedBy:)``
- ``Swift/String/distance(from:to:)``
- ``Swift/String/indices-swift.property``

### Creating a Range Expression

- ``Swift/String/.._(_:_:)``
- ``Swift/String/...(_:_:)``
- ``Swift/String/.._(_:)``
- ``Swift/String/...(_:)-4mm4o``
- ``Swift/String/...(_:)-6ct5g``

### Encoding and Decoding

- ``Swift/String/encode(to:)``
- ``Swift/String/init(from:)-qki5``

### Describing a String

- ``Swift/String/description``
- ``Swift/String/debugDescription``
- ``Swift/String/customMirror``
- ``Swift/String/hashValue``
- ``Swift/String/hash(into:)``

### Using a String as a Data Value

- ``Swift/String/init(from:)-gcys``
- ``Swift/String/dataValue``
- ``Swift/String/identifierValue``
- ``Swift/String/dataValueType``

### Infrequently Used Functionality

- ``Swift/String/index(of:)``
- ``Swift/String/init(_:)-5a5lw``
- ``Swift/String/init(stringInterpolation:)-1jjv``
- ``Swift/String/init(stringLiteral:)``
- ``Swift/String/init(unicodeScalarLiteral:)``
- ``Swift/String/init(extendedGraphemeClusterLiteral:)``
- ``Swift/String/customPlaygroundQuickLook``
- ``Swift/String/withContiguousStorageIfAvailable(_:)``

### Reference Types

Use bridged reference types when you need reference semantics or Foundation-specific
behavior.

- <doc://com.apple.documentation/documentation/foundation/nsstring>
- <doc://com.apple.documentation/documentation/foundation/nsmutablestring>

### Related String Types

- ``Swift/Substring``
- ``Swift/StringProtocol``
- ``Swift/String/Index``
- ``Swift/String/UnicodeScalarView``
- ``Swift/String/UTF16View``
- ``Swift/String/UTF8View``
- ``Swift/String/Iterator``
- ``Swift/String/Encoding``
