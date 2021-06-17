# Standard Endpoints

Endpoints are defined by specifying an address, a binding, and a contract. Other parameters that may be set on an endpoint include behavior configuration, headers, and listen URIs. For certain types of endpoints these values do not change.

For example: 

Metadata exchange endpoints always use the [IMetadataExchange](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.description.imetadataexchange) contract. 

Other endpoints, such as [WebHttpEndpoint](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.description.webhttpendpoint) always require a specified endpoint behavior. 



## Infrastructure Endpoints

A service may expose endpoints with some of the properties not explicitly implemented by the service author.

For example 

The metadata exchange endpoint exposes the [IMetadataExchange](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.description.imetadataexchange) contract but as a service author you do not implement that interface, it is implemented by WCF.

Such infrastructure endpoints have default values for one or more endpoint properties, some of which may be unalterable. The [Contract](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.description.serviceendpoint.contract) property of the metadata exchange endpoint must be [IMetadataExchange](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.description.imetadataexchange), while other properties like binding can be supplied by the developer. Infrastructure endpoints are identified by setting the [IsSystemEndpoint](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.description.serviceendpoint.issystemendpoint) property to `true`.

## Application Endpoints

Application developers can define their own standard endpoints which specify default values for the address, binding, or contract. You define a standard endpoint by deriving a class from [ServiceEndpoint](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.description.serviceendpoint) and setting the appropriate endpoint properties. You can provide default values for properties that can be changed. Some other properties will have static values that cannot change. The following example shows how to implement a standard endpoint.

```C#
public class CustomEndpoint : ServiceEndpoint
{
    public CustomEndpoint()
        : this(string.Empty)
    { }  

    public CustomEndpoint(string address)
        : this(address, ContractDescription.GetContract(typeof(ICalculator)))
    { }  

    // Create the custom endpoint with a fixed binding
    public CustomEndpoint(string address, ContractDescription contract)
        : base(contract)
    {
        this.Binding = new BasicHttpBinding();
        this.IsSystemEndpoint = false;
    }

    // Definition of the additional property of this endpoint
    public bool Property { get; set; }
}
```



The [StandardEndpointElement](https://docs.microsoft.com/en-us/dotnet/api/system.servicemodel.configuration.standardendpointelement) provides configuration support for the standard endpoint, as shown in the following example.



```c#
public class CustomEndpointElement : StandardEndpointElement
{
    // Definition of the additional property for the standard endpoint element
    public bool Property
    {
        get { return (bool)base["property"]; }
        set { base["property"] = value; }
    }

    // The additional property needs to be added to the properties of the standard endpoint element
    protected override ConfigurationPropertyCollection Properties
    {
        get
        {
            ConfigurationPropertyCollection properties = base.Properties;
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));
            return properties;
        }
    }

    // Return the type of this standard endpoint
    protected override Type EndpointType
    {
        get { return typeof(CustomEndpoint); }
    }

    // Create the custom service endpoint
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)
    {
        return new CustomEndpoint();
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)
    {
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)
    {
    }
}
```

