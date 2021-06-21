**Service contract**
Ties together multiple related operations into a single functional unit. The contract can define service-level settings, such as the namespace of the service, a corresponding callback contract, and other such settings. In most cases, the contract is defined by creating an interface in the programming language of your choice and applying the [ServiceContractAttribute](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.servicecontractattribute) attribute to the interface. The actual service code results by implementing the interface.



https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.servicecontractattribute?view=dotnet-plat-ext-5.0

Indicates that an interface or a class defines a service contract in a Windows Communication Foundation (WCF) application.



**Operation contract**
An operation contract defines the parameters and return type of an operation. When creating an interface that defines the service contract, you signify an operation contract by applying the [OperationContractAttribute](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.operationcontractattribute) attribute to each method definition that is part of the contract. The operations can be modeled as taking a single message and returning a single message, or as taking a set of types and returning a type. In the latter case, the system will determine the format for the messages that need to be exchanged for that operation.



https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.operationcontractattribute?view=dotnet-plat-ext-5.0

Indicates that a method defines an operation that is part of a service contract in a Windows Communication Foundation (WCF) application.
