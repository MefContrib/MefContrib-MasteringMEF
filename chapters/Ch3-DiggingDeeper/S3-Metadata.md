### Metadata

*   Enables parts and exports to carry additional information -The simplest form of metadata is added with the help of the ExportMetadataAttribute
*   The ExportMetadataAttribute is weakly-typed and relies on magic-strings
*   Internally metadata is stored as a Dictionary<string, object> instance
*   Metadata can be obtained and read by importing Lazy<T,K> instances, more specifically Lazy<T, Dictionary<string, object>>
*   The MetadataAttributeAttribute can be used to decorate a custom attribute to tell \---| - MEF what it defines metadata for the export or part
*   A custom metadata attribute provides a strongly-typed write experience for metadata
*   To provide a strongly-typed read experience for metadata, a metadata contract can be created
*   A metadata contract is an interface with read-only members that can be used with Lazy<T,K> to add strong-typing
*   Export metadata has to satisfy the entire metadata contract (i.e all members need to have values defined in the metadata) or the export will be rejected
*   Members of the metadata contract can be made optional with the help of the DefaultValueAttribute
*   MEF uses "structural duck-typing" for metadata, meaning MEF doesn't care about the type of the contract, only that the available metadata satisfies all the metadata requirements defined by the contract
