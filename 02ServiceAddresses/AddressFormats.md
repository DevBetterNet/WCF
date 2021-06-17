# Address Formats

Endpoint addresses are formatted based on the selected transport used in communication. As in the example above, most address formats contain the following parts:

- Scheme that specifies the protocol.
- A fully qualified domain name.
- Based on requirements some services uses ports (default 80)
- The specific or multiples paths of the services.

Now we will list different Address Formats and the differences.

- **HTTP Address**

  The most common address format for a service is HTTP Address.

  *format: http://domainname|machinename [:port]/path or paths*

  

- **HTTPS Address**

  Same as HTTP Address but HTTPS ca be secured by using SSL (Secure Socket Layer) and need to obtain a valid certificates.

  *format: https://domainname|machinename [:port]/path or paths*

  

- **TCP Address**

  WCF provides a new TCP based network protocol for high performance communication.

  *format: net.tcp://domainname|machinename [:port]/path or paths*

  

- **MSMQ Address**

  MSMQ address format differs from others.

  *format: net.msmq://host name/ [private]/queue-name*

  

- - Scheme that specifies the MSMQ protocol.

  - A fully qualified domain name of the machine running MSMQ or localhost.

  - [private] is optional, but when used it contains the address of a target queue that is private queue.

  - Queue-name is the name of the MSMQ name.

    

- **Named Pipe Address**

  This address has no port number and communication using named pipes cannot be "cross-machine" (between two machines).

  *format: net.pipe://localhost/service*

  

- **IIS Address**

  Here also a different in address format because IIS address requires a virtual directory name as well as a service (.svc) filename.

  *format: http://domainname|machinename [:port]/virtual directory name [.svc filename]*