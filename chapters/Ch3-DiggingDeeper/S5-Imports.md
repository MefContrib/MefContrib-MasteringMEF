### Imports

#### Where can I import? Fields, properties, constructors, delegates, etc.

You can export fields, properties, methods and entire types

#### Cardinality

There are three modes of cardinality that are controlled by the ImportAttribute.  
One of the modes requires exactly one object is imported.

[Import] public IShape Shape { get; set; }

By setting the AllowDefault property to true on the ImportAttribute we are allowing the value to be null.

[Import(AllowDefault = true)] public IShape Shape { get; set; }

In order to import any number of objects, we need to use the ImportManyAttribute rather than the ImportAttribute, and the type to import must be an IEnumerable of the given type or an array of the given type.

[ImportMany] public IEnumerable Shape { get; set; }

#### Lazy Importing

The .NET Framework 4.0 brings us a new class to handle lazy initialization. Lazy initialization allows developers to defer the construction of large, resource-intensive, or otherwise inconvenient classes, until the class is needed, if at all. There are two generic versions of the Lazy class, Lazy, and one with attached metadata, Lazy<T, TMetadata>. Lazy initialization the first time the Lazy.Value property is accessed or the Lazy.ToString() method is called.

##### Lazy

*   Use an instance of Lazy to defer the creation of a large or resource-intensive object or the execution of a resource-intensive task, particularly when such creation or execution might not occur during the lifetime of the program.

##### Lazy<T, TMetadata>

*   Provides a lazy loading mechanism that allows developers to interrogate metadata, which can be used to decide if a given “lazy” item should be instantiated.

#### Importing a factory

If you need to create multiple unique instances of an export you can import an ExportFactory, once you have an instance of the ExportFactoryif you call CreateExport().Value on that instance, you will receive a new instance of T.

#### Importing into IEnumerable, arrays, and ICollections

When using ImportManyAttribute, we can import into IEnumerable, an array of a type or interface (IMyType[], or MyType[]) and any type that implements ICollection.

#### Importing with custom metadata