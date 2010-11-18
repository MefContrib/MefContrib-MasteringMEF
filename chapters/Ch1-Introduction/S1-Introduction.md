## Introduction

### What is it?

The Managed Extensibility Framework (MEF) is an exciting new technology in the .NET framework 4.0, and Silverlight 4, located in the System.ComponentModel.Composition namespace. In order to understand what it does, it might help to learn how and why it came into existence. Not so long ago, a number of groups within Microsoft were independently working to solve a common problem, how to develop more reusable components, components that may even be reused in other applications. The Patterns and Practices team started developing a library that allows components to be discovered, reused and composed dynamically, and MEF is a result of this effort. MEF should simplify your application development and helps in creating lightweight, loosely coupled and extensible applications. It enables applications to avoid hard dependencies, and discover and use extensions without the need for configuration.

### Why should I use it?

If you have ever written or worked on a very large application, there are issues that you will naturally run into. Many of these issues are due to the complexity and interconnectivity of the components. By allowing components to not be explicitly dependent on another specific component, code can become more flexible, reusable, and more easily refactored.

### How do I get it and where can I use it?

Built into the .NET 4.0 framework

Or available on Codeplex for earlier versions of .NET (http://mef.codeplex.com/)

Can be used in any type of .NET application

### How does it compare to similar solutions?

Many of the libraries that are similar to MEF are too costly to use/host, and many were not extensible enough.

Microsoft analyzed the available solutions and attempted to address the pain points in each.

*   Give Specific solution comparisons
