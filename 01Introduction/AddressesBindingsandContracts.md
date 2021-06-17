# Endpoints: Addresses, Bindings, and Contracts



All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service. Endpoints provide clients access to the functionality offered by a WCF service.

Each endpoint consists of four properties:

- An address that indicates where the endpoint can be found.
- A binding that specifies how a client can communicate with the endpoint.
- A contract that identifies the operations available.
- A set of behaviors that specify local implementation details of the endpoint.

This topic discusses this endpoint structure and explains how it is represented in the WCF object model.

## The Structure of an Endpoint

Each endpoint consists of the following:

- Address: The address uniquely identifies the endpoint and tells potential consumers of the service where it is located. It is represented in the WCF object model by the [EndpointAddress](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.endpointaddress) class. An [EndpointAddress](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.endpointaddress) class contains:

  - A [Uri](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.endpointaddress.uri) property, which represents the address of the service.
  - An [Identity](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.endpointaddress.identity) property, which represents the security identity of the service and a collection of optional message headers. The optional message headers are used to provide additional and more detailed addressing information to identify or interact with the endpoint.

  For more information, see [Specifying an Endpoint Address](https://docs.microsoft.com/en-us/dotnet/framework/wcf/specifying-an-endpoint-address).

- Binding: The binding specifies how to communicate with the endpoint. This includes:

  - The transport protocol to use (for example, TCP or HTTP).
  - The encoding to use for the messages (for example, text or binary).
  - The necessary security requirements (for example, SSL or SOAP message security).

  For more information, see [WCF Bindings Overview](https://docs.microsoft.com/en-us/dotnet/framework/wcf/bindings-overview). A binding is represented in the WCF object model by the abstract base class [Binding](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.channels.binding). For most scenarios, users can use one of the system-provided bindings. For more information, see [System-Provided Bindings](https://docs.microsoft.com/en-us/dotnet/framework/wcf/system-provided-bindings).

- Contracts: The contract outlines what functionality the endpoint exposes to the client. A contract specifies:

  - What operations can be called by a client.
  - The form of the message.
  - The type of input parameters or data required to call the operation.
  - What type of processing or response message the client can expect.

  For more information about defining a contract, see [Designing Service Contracts](https://docs.microsoft.com/en-us/dotnet/framework/wcf/designing-service-contracts).

- Behaviors: You can use endpoint behaviors to customize the local behavior of the service endpoint. Endpoint behaviors achieve this by participating in the process of building a WCF runtime. An example of an endpoint behavior is the [ListenUri](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.description.serviceendpoint.listenuri) property, which allows you to specify a different listening address than the SOAP or Web Services Description Language (WSDL) address. For more information, see [ClientViaBehavior](https://docs.microsoft.com/en-us/dotnet/framework/wcf/diagnostics/wmi/clientviabehavior).

## Defining Endpoints

You can specify the endpoint for a service either imperatively using code or declaratively through configuration. For more information, see [How to: Create a Service Endpoint in Configuration](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration) and [How to: Create a Service Endpoint in Code](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code).

## In This Section

This section explains the purpose of bindings, endpoints, and addresses; shows how to configure a binding and an endpoint; and demonstrates how to use the `ClientVia` behavior and `ListenUri` property.

[Addresses](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/endpoint-addresses)
Describes how endpoints are addressed in WCF.

[Bindings](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/bindings)
Describes how bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.

[Contracts](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/contracts)
Describes how contracts define the methods of a service.

[How to: Create a Service Endpoint in Configuration](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration)
Describes how to create a service endpoint in configuration.

[How to: Create a Service Endpoint in Code](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code)
Describes how to create a service endpoint in code.

[How to: Use Svcutil.exe to Validate Compiled Service Code](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code)
Describes how to detect errors in service implementations and configurations without hosting the service using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://docs.microsoft.com/en-us/dotnet/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe).