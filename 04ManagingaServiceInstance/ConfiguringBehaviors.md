# Configuring Client Behaviors



**Configuration file**

When using a configuration file, behavior configuration is a named collection of configuration settings. The name of each behavior configuration must be unique. This string is used in the `behaviorConfiguration` attribute of an endpoint configuration to link the endpoint to the behavior.



```xml
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="myBehavior">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <bindings>  
            <basicHttpBinding>  
                <binding name="myBinding" maxReceivedMessageSize="10000" />  
            </basicHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="myAddress" binding="basicHttpBinding" bindingConfiguration="myBinding" behaviorConfiguration="myBehavior" contract="myContract" />  
        </client>  
    </system.serviceModel>  
</configuration>
```



**Programmatically**



```C#
public class Client
{
  public static void Main()
  {
    try
    {
      // Picks up configuration from the config file.
      ChannelFactory<ISampleServiceChannel> factory
        = new ChannelFactory<ISampleServiceChannel>("WSHttpBinding_ISampleService");

      // Add the client side behavior programmatically to all created channels.
      factory.Endpoint.Behaviors.Add(new EndpointBehaviorMessageInspector());

      ISampleServiceChannel wcfClientChannel = factory.CreateChannel();

      // Making calls.
      Console.WriteLine("Enter the greeting to send: ");
      string greeting = Console.ReadLine();
      Console.WriteLine("The service responded: " + wcfClientChannel.SampleMethod(greeting));

      Console.WriteLine("Press ENTER to exit:");
      Console.ReadLine();

      // Done with service.
      wcfClientChannel.Close();
      Console.WriteLine("Done!");
    }
    catch (TimeoutException timeProblem)
    {
      Console.WriteLine("The service operation timed out. " + timeProblem.Message);
      Console.Read();
    }
    catch (FaultException<SampleFault> fault)
    {
      Console.WriteLine("SampleFault fault occurred: {0}", fault.Detail.FaultMessage);
      Console.Read();
    }
    catch (CommunicationException commProblem)
    {
      Console.WriteLine("There was a communication problem. " + commProblem.Message);
      Console.Read();
    }
  }
```

