# Windows Communication Foundation Bindings



A binding must specify the transport (for example, HTTP or TCP) to use. You can also set other characteristics, such as security and transaction support, through bindings.

## What a Binding Defines

The information in a binding can be very basic, or very complex. The most basic binding specifies only the transport protocol (such as HTTP) that must be used to connect to the endpoint. More generally, the information a binding contains about how to connect to an endpoint falls into one of the following categories:

**Protocols**
Determines the security mechanism being used: either reliable messaging capability or transaction context flow settings.

**Encoding**
Determines the message encoding (for example, text or binary).

**Transport**
Determines the underlying transport protocol to use (for example, TCP or HTTP).

## The Elements of a Binding

A binding basically consists of an ordered stack of binding elements, each of which specifies part of the communication information required to connect to a service endpoint. The two lowest layers in the stack are both required. At the base of the stack is the transport binding element and just above this is the element that contains the message encoding specifications. The optional binding elements that specify the other communication protocols are layered above these two required elements. For more information about these binding elements and their correct ordering, see [Custom Bindings](https://docs.microsoft.com/en-us/dotnet/framework/wcf/extending/custom-bindings).

## System-Provided Bindings

The information in a binding can be complex, and some settings may not be compatible with others. For this reason, WCF includes a set of system-provided bindings. These bindings are designed to cover most application requirements. The following classes represent some examples of system-provided bindings:

- [BasicHttpBinding](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.basichttpbinding): An HTTP protocol binding suitable for connecting to Web services that conforms to the WS-I Basic Profile specification (for example, ASP.NET Web services-based services).
- [WSHttpBinding](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.wshttpbinding): An interoperable binding suitable for connecting to endpoints that conform to the WS-* protocols.
- [NetNamedPipeBinding](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.netnamedpipebinding): Uses the .NET Framework to connect to other WCF endpoints on the same machine.
- [NetMsmqBinding](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.netmsmqbinding): Uses the .NET Framework to create queued message connections with other WCF endpoints.
- [NetTcpBinding](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.nettcpbinding): This binding offers higher performance than HTTP bindings and is ideal for use in a local network.

For a complete list, with descriptions, of all the WCF-provided bindings, see [System-Provided Bindings](https://docs.microsoft.com/en-us/dotnet/framework/wcf/system-provided-bindings).

## Using Your Own Bindings

If none of the system-provided bindings included has the right combination of features that a service application requires, you can create your own binding. There are two ways to do this. You can either create a new binding from pre-existing binding elements using a [CustomBinding](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.channels.custombinding) object or you can create a completely user-defined binding by deriving from the [Binding](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.channels.binding) binding. For more information about creating your own binding using these two approaches, see [Custom Bindings](https://docs.microsoft.com/en-us/dotnet/framework/wcf/extending/custom-bindings) and [Creating User-Defined Bindings](https://docs.microsoft.com/en-us/dotnet/framework/wcf/extending/creating-user-defined-bindings).

## Using Bindings

Using bindings entails two basic steps:

1. Select or define a binding. The easiest method is to choose one of the system-provided bindings included with WCF and use it with its default settings. You can also choose a system-provided binding and reset its property values to suit your requirements. Alternatively, you can create a custom binding or a user-defined binding to have higher degrees of control and customization.
2. Create an endpoint that uses the binding selected or defined.

## Code and Configuration

You can define bindings in two ways: through code or through configuration. These two approaches do not depend on whether you are using a system-provided binding or a custom binding. In general, using code gives you complete control over the definition of a binding at design time. Using configuration, on the other hand, allows a system administrator or the user of a WCF service or client to change the parameters of a binding without having to recompile the service application. This flexibility is often desirable because there is no way to predict specific machine requirements on which a WCF application is to be deployed. Keeping the binding (and the addressing) information out of the code allows them to change without requiring recompilation or redeployment of the application. Note that bindings defined in code are created after bindings specified in configuration, allowing the code-defined bindings to overwrite any configuration-defined bindings