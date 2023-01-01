# SIPT

## description
SIPT is a sip protocol tool to simulate sip user-agent to do communication with sip-server.
the target of SIPT is used to do performance test. usually if we want to know the performance of a sip-server(SBC, sip-proxy, sip-server) , we need a tool
to simulate endpoint's behavior which support SIP protocol. and also this tool must have a high performance.
in the real world, sip-server is usually not only a register server, but also a sip-call server. So we need a tool must be able to  produce all the sip message that
a endpoint(sip software client or hardware voip phone) can do.
now the basic target of SIPT is simulating many client's behavior, including:
1) must be able to configure many sip user info, including the sip-user-name, sip-domain, sip-authentication-name, sip-authentication-password and other info need.
   Usually the sip-client does a tls connection with SBC/SIP-proxy, So a SIPT instance, I expect it can support 40K tls connection(one tls connection per sip-user).
   And we must specify that the min-resource of the test platform, for x86-64 centos/ubuntu/almalinux platform, 8G memory and 4cpu(8threads) is needed. all these 
   40K sip-users can make al least 4K concurrent sip calls.
   if you have a very powerful test platform, you can create servial KVM instance.
   if you do using the KVM, please do some configuration of KVM, for example the cpu, NIC.
   why 40K? totally because of the tcp client ports one SIPT can used. 
2) SIPT must be able to simulate the behavior of a sip-user, it can create sip-register sessions, sip subscriber session, sip-call dialogs concurrently.
   
3) support UDP/TCP/TLS/websocket/websocket-tls 

4) support multi-connection with sip-proxy(one tcp/udp client port per user) or using one sip client port communicating ith sip server.

5) support srtp 
