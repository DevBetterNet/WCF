# Address

Because Address if one of 4 properties in EndPoint. So we can call it Endpoint Addresses



Every endpoint has an address associated with it, which is used to locate and identify the endpoint. This address consists primarily of a Uniform Resource Identifier (URI), which specifies the location of the endpoint. The endpoint address is represented in the Windows Communication Foundation (WCF) programming model by the [EndpointAddress](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.endpointaddress) class, which contains an optional [Identity](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.endpointaddress.identity) property that enables the authentication of the endpoint by other endpoints that exchange messages with it, and a set of optional [Headers](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.endpointaddress.headers) properties, which define any other SOAP headers required to reach the service. The optional headers provide additional and more detailed addressing information to identify or interact with the service endpoint. The address of an endpoint is represented on the wire as a WS-Addressing endpoint reference (EPR).



```xml
<system.serviceModel>  
  <serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="net.tcp://payroll.myorg.com:8000"/>  
        <add prefix="http://shipping.myorg.com:8000"/>  
    </baseAddressPrefixFilters>  
  </serviceHostingEnvironment>  
</system.serviceModel>
```



```xml
<system.serviceModel>  
  <serviceHostingEnvironment multipleSiteBindingsEnabled="true" >  
  </serviceHostingEnvironment>  
</system.serviceModel>
```

