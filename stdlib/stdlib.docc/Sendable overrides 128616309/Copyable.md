# ``Swift/Copyable``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

A type whose values can be implicitly or explicitly copied.

Conforming to this protocol indicates that a type's value can be copied;
this protocol doesn’t have any required methods or properties.
You don't generally need to write an explicit conformance to `Copyable`.
The following places implicitly include `Copyable` conformance:

* Structure declarations,
  unless it has a noncopyable stored property
* Enumeration declarations,
  unless it has a case whose associated value isn't copyable
* Class declarations
* Actor declarations
* Protocol declarations
* Associated type declarations
* The `Self` type in a protocol extension
* In an extension, the generic parameters of the type being extended

A class or actor can contain noncopyable stored properties,
while still being copyable itself ---
classes and actors are copied by retaining and releasing references.

In a declaration that includes generic type parameters,
each generic type parameter implicitly includes `Copyable`
in its list of requirements.
Metatypes and tuples of copyable types are also implicitly copyable,
as are boxed protocol types.
For example,
all of the following pairs of declarations are equivalent:

    struct MyStructure { }
    struct MyStructere: Copyable { }

    protocol MyProtocol { }
    protocol MyProtocol: Copyable { }

    protocol AnotherProtocol {
        associatedtype MyType
        associatedtype MyType: Copyable
    }

    func genericFunction<T>(t: T) { }
    func genericFunction<T>(t: T) where T: Copyable { }

    let x: any MyProtocol
    let x: any MyProtocol & Copyable

To suppress an implicit conformance to `Copyable` you write `~Copyable`.
For example,
only copyable types can conform to `MyProtocol` in the example above,
but both copyable and noncopyable types
can conform `NoRequirements` in the example below:

    protocol NoRequirements: ~Copyable { }

Extensions to the `Copyable` protocol are not allowed.
