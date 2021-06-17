# WCF Course Overview

**Introduction to WCF**

- [WCF Web Services Architecture](01Introduction/WCFWebServicesArchitecture.md) 
- [Addresses, Bindings and Contracts](01Introduction/AddressesBindingsandContracts.md) 
- [WCF Service Libraries](01Introduction/WCFWebServicesArchitecture.md) 
- WCF Test Host and Test Client
- ChannelFactory Class
- Configuring WCF Clients
- Standard Endpoints



**Service Addresses**

- Address Types
  - Endpoint Address
  - Base Address
  - MEX (Message Exchange) Address
- Metadata Exchange
- Address Formats

**Selecting Binding Options**

- Binding Selection
- HTTP Bindings
- TCP and Named Pipe Bindings
- MSMQ Binding
- BasicHttpBinding Class

**Managing a Service Instance**

- Configuring Behaviors
- Service Instance Models
  - Per-Call
  - Per-Session
  - Singleton
- Threading Considerations
- Consuming WCF Application Services with .NET Applications
- Consuming WCF Application Services on foreign platforms



**Defining Service Contracts**

- Service and Operation Contracts

- Creating Contracts at the Class and Interface Level

- Using ServiceContractAttribute

- Types of Service Contracts
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

- Endpoints Explained

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
