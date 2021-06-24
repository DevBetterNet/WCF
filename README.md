# WCF Course Overview

**Introduction to WCF**

- [WCF Web Services Architecture](01Introduction/WCFWebServicesArchitecture.md) 
- [Addresses, Bindings and Contracts](01Introduction/AddressesBindingsandContracts.md) 
- [WCF Service Libraries](01Introduction/WCFWebServicesArchitecture.md) 
- WCF [Test Host](01Introduction/WCFServiceHost.md) and [Test Client](01Introduction/WCFTestClient.md) 
- [ChannelFactory Class](01Introduction/ChannelFactoryClass.md) 
- [Configuring WCF Clients](01Introduction/ClientConfiguration.md) 
- [Standard Endpoints](01Introduction/StandardEndpoints.md) 



**Service Addresses**

- [Address Types](02ServiceAddresses/AddressTypes.md) 
  - Endpoint Address
  - Base Address
  - MEX (Message Exchange) Address
- Metadata Exchange
- [Address Formats](02ServiceAddresses/AddressFormats.md) 

**Selecting Binding Options**

- [Binding Selection](03SelectingBindingOptions/Bindings.md) :  HTTP Bindings, TCP and Named Pipe Bindings, MSMQ Binding, BasicHttpBinding Class

**Managing a Service Instance**

- [Configuring Behaviors](04ManagingaServiceInstance/ConfiguringBehaviors.md) 
- [Service Instance Models](04ManagingaServiceInstance\ServiceInstanceModels.md) 
  - Per-Call
  - Per-Session
  - Singleton
- [Threading Considerations](04ManagingaServiceInstance/ThreadingConsiderations.md) 
- [Consuming WCF Application Services with .NET Applications](04ManagingaServiceInstance\ConsumingWCFApplicationServiceswithNETApplications.md) 
- [Consuming WCF Application Services on foreign platforms](04ManagingaServiceInstance\ConsumingWCFApplicationServicesonforeignplatforms.md) 



**Defining Service Contracts**

- [Service and Operation Contracts](05DefiningServiceContracts\ServiceandOperationContracts.md) 

- [Creating Contracts at the Class and Interface Level](05DefiningServiceContracts\Creating ContractsattheClassandInterfaceLevel.md) 

- [Using ServiceContractAttribute](05DefiningServiceContracts\UsingServiceContractAttribute.md) 

- [Types of Service Contracts](04ManagingaServiceInstance\TypesofServiceContracts.md) 
  - Oneway
  - Request-Reply
  - Duplex
  
- Callbacks

- Asynchronous Proxies

- WSDL Files

- Contract Inheritance and Overloading

- Implementing Message Exchange Patterns

- Versioning

  

**Defining Data Contracts**

- Using DataContractAttribute

- Mapping Data to Schema

- Returning Arrays

- Returning Generic Collections

- Data Serialization

- Versioning

  

**Endpoints**

- [Endpoints Explained](07Endpoints\EndpointsExplained.md) 

- Working with Endpoints

- Configuring Endpoints

- Using Multiple Endpoints

  

**Fault Handling**

- FaultException class
- FaultCode class
- FaultContract class
- Client Exception Handling
- Including Exception Details



**Securing WCF Applications**

- Security Issues with Services

- Types of Security

- - Transfer Security
  - Transport Security
  - Message Security

- Configuring Security on Client and Server

- Managing Certificates

- Configuring Client Certificates

- Sending Credentials



**WCF Routing Configuration**

- WCF Routing Service

- Hosting the Service

- Consuming the Service

- Service Contract and Implementation

- Routing Contracts

- Message Filters

- Common Routing Scenarios

- - Load Balancing
  - Content Based Routing
  - Service Partitioning
  - Protocol Bridging
