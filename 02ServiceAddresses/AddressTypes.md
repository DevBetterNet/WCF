# Address Types

Different types of addresses are associates with each endpoints and it is through addresses that the client communicates with the end point.

- **Endpoint Address**

  The example given above specifies the address of a specific service endpoint which client can access.

  Once the client has accessed the service from above endpoint address, all the communication happens

  

- **Base Address**

  Base address provide a way to specify a single, primary address for a given service and assign relative addresses to each individual endpoint.

  For example this base address assigned to a service: http://www.domain.com/Publish.

  Also we can have multiple individual endpoints to the address above.

  http://domain.com/Publish/service1
  http://domain.com/Publish/service2
  http://domain.com/Publish/service3
  http://domain.com/Publish/service4 etc..

  

- **MEX (Metadata exchange) Address**

  Address allows a client to gather information about a particular service. MEX is an http endpoint address used to obtain service information.

  The information is provided through the service metadata, which describes the service.

  For example: http://domain.com/Publish/mex
