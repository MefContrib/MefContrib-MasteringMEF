### Exports

#### Where can I export? Fields, properties, constructors, delegates, etc.

#### Exporting with custom metadata

#### Custom Exports

*   Enables you to bring in your domain into the mix

*   Not everybody cares about the implementation details and forcing implementers to use MEF vocabulary such as Export(typeof(foo)) can be confusing

*   Can create a custom export attribute by inheriting from ExportAttribute

*   When inheriting from ExportAttribute, it is important to call the base constructor with the right contract name and type identity

*   The custom export attribute can also implement a metadata contract, making it possible to define an export with a custom attribute and at the same time define a strongly-typed write experience for adding metadata

*   The custom attribute can take in metadata in the constructor or as properties. The properties help to make it friendlier to read since the property name is also shown

*   Make sure to set AllowMultiple to false or MEF will treat metadata as a "collection of collections" instead

#### Export Inheritance

*   Enables very transparent scenarios
*   Tag a class or interface with the InheritedExportAttribute
*   All types that derive from the class or implement the interface will automatically be treated as an export of the same type as defined in the InheritedExportAttribute constructor
*   The behavior can be opted out from by adding the PartNotDiscoverableAttribute on the type
*   The PartNotDiscoverableAttribute will also prevent all children of the tagged type from being discoverable to MEF
*   There are restrictions with metadata and inherited exports.

### Composition

#### Containers

*   Is known as the Composition Container
*   CompositionContainer is an ExportProvider
*   The container is responsible for "gluing everything together"
*   Satisfies imports on an instance by looking for matching (contract name, type identity, cardinality, type casting) exports

#### Catalogs

*   What are they (they discover parts)
*   They inherit from ComposablePartCatalog
*   Provide ComposablePartDefinitions

##### AssemblyCatalog

*   An immutable catalog created from a managed code assembly.

##### AggregateCatalog

*   A mutable collection of ComposablePartCatalogs.

##### DirectoryCatalog

*   A catalog created from all the *.dll file in a given directory.
*   Note: This is not found in Silverlight.

##### DeploymentCatalog

*   Discovers attributed parts in a XAP file, and provides methods for asynchronously downloading XAP files.
*   Note: This is only found in Silverlight.

##### TypeCatalog

*   An immutable catalog created from a type array or a list of managed types. Custom Catalogs
*   Can create custom catalogs by inheriting ComposablePartCatalog

Implementing the INotifyComposablePartCatalogChanged enables you to notify the surroundings that the parts the catalog have available has changed

#### Export Providers

AggregateExportProvider  
CatalogExportProvider  
ComposablePartExportProvider  
CompositionContainer  
DynamicInstantiationExportProvider

#### Recomposition

Allows imports on parts to be automatically updated as new exports are available  
Silverlight recomposition by downloading .XAPs

#### Stable Composition

What is it, what does it mean  
Ensures that part resolution failures will not crash the application