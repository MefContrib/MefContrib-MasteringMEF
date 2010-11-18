## Basic Overview

To get started with MEF there are only three main concepts that need to be understood, Imports, Exports and Parts. Imports are used to inform the surroundings that you need a particular type. Exports are used to inform the surroundings that you have a service to offer of service. A part is the name of an item that has imports and exports.

### Composable Parts

Composable Parts contain information about what information needs to be imported as well as what needs to be exported. When we talk about MEF, this is the fundamental unit that is dealt with. Imports and Exports do not directly interact with one another. Instead they use a contract of sorts, made up of a string and a .NET Type.

### Contracts

The contracts used by MEF are declared by an "Export" and requested by an "Import". A quick example would be one class exporting, by advertising that it is an ILogger and the string to find it by is "MainLogger". If there were another class that was requesting to know about any ILogger's that have the "MainLogger" contract name, the import would be correctly resolved.

### Exports

Exports are used to notify the environment that a service of some sort is being offered. In order to declare something as an export use the System.ComponentModel.Composition.ExportAttribute attribute. The Export attribute has four different constructors, that ultimately set two variables (ContractName, and ContractType)

*   [ExportAttribute()]
*   [ExportAttribute(string contractName)]
*   [ExportAttribute(Type contractType)]
*   [ExportAttribute(string contractName, Type contractType) ]

### Imports

Imports are used to notify the environment that a service is required. In order to declare something as an import use the System.ComponentModel.Composition.ImportAttribute attribute. Imports can be resolved in the constructor by using the System.ComponentModel.Composition.ImportingConstructorAttribute on the chosen constructor. Like the Export attribute, the ImportAttribute has four different constructors.

*   [ImportAttribute()]
*   [ImportAttribute(string contractName)]
*   [ImportAttribute(Type contractType)]
*   [ImportAttribute(string contractName, Type contractType)]

It also has three more attributes:

*   AllowDefault - this sets an import to not require a Export to be found.
*   AllowRecomposition - sets whether an Import will be recomposed when exports with a matching contract have changed.
*   RequiredCreationPolicy - denotes that an import requires a specific CreationPolicy (CreationPolicy's will be described in detail in a later section).