**Tenancy** - having a separate instance even with similar IPs
# Network & Content Delivery
- IPv4 (32-bit) - less accurate address; decimal in 8-bit value
- IPv6 (128-bit) - more accurate address; hexadecimal in 4-bit value

## Classless Inter-Domain Routing (CIDR)
- Network identifier (routing prefix)
- Enables you to specify a range of IP addresses
- Expressed as an IP address followed by a slash (/) and a number (e.g., 192.0.2.0/24)
- The number after the slash indicates the number of bits in the network portion of the address.

## Open Systems Interconnection (OSI) Model
- **Application**: means for an application to access a computer network (HTPPS, FTP, DHCP, LDAP)
- **Presentation**: ensures that the application layer can read the data; encryption (ASCI, ICA)
- **Session**: enables orderly exchange of data (NetBIOS, RPC)
- **Transport**: provides protocols to support host-to-host communication (TCP, UDP)
- **Network**: routing and packet forwarding (routers; IP)
- **Data link**: transfer data in the same LAN network (hubs and switches; MAC)
- **Physical**: transmission and reception of raw bitstreams over a physical medium (1s and 0s)

# Amazon Virtual Private Cloud (VPC) / Networking
- gives us an **isolated version** in the cloud
- users have their own **isolated** instance
- gives us **control over our virtual networking resources**, including:
    - selection of IP address range
    - creation of subnets
    - config of route tables and network gateways
- enables you to customize the network configuration for your VPC
- enables you to use multiple layers of security

## VPCs and Subnets
### VPCs:
- logically isolated from other VPCs
- dedicated to your AWS account
- belongs to a single AWS Region
### Subnets:
- range of IP addresses in your VPC
- cannot span multiple Availability Zones (AZs)
- can be public (with direct internet access) or private (no direct internet access)
- CIDR block of subnets cannot overlap

*Note: Routers function the same as firewalls*

Ex: x.x.x.x/28 has 16 addresses
32-28 = 4 = 2^4 = 16

### Public IP Address Types
#### Public IPv4 address
- manually assigned thru an **Elastic IP address**
- automatically assigned through the auto-assign public IP address settings at the subnet level
- address can change if you reboot your server or turn it off
- Instance-based
- No Public Service

#### Elastic IP address
- associated with an AWS account
- can be allocated and remapped anytime
- additional costs might apply
- expensive but at least your IP won't change
- address is semi-permanent but you pay for a reservation cost if you use it or not
- Account-based
- Public Service

#### Routing Tables
- A set of rules that control where network traffic is directed.
- Each subnet in a VPC must be associated with a routing table.

## Networks
### Network ACLs
- has separate inbound and outbound rules
- allows or deny traffic
- default network ACLs allow all inbound and outbound IPv4 traffic
- ACLs are stateless (meaning responses to allowed inbound traffic are subject to outbound rules)

# Amazon Route 53
- 53 is the port num of DNS
- a highly available and scalable DNS web service

## Supported Routing
- **simple routing** - use in single-server environments
- **weighted round robin routing** - assign weights to resource record sets to frequency
- **latency routing** - help improve your global apps by routing requests to the AWS region that provides the lowest latency
- **geolocation routing** - route traffic based on location of your users
- **geoproximity routing** - route traffic based on location of your resources
- **failover routing** - fail over to a backup site when the primary resource is unhealthy
- **multi-value answer routing** - returns up to eight healthy records selected at random from the many healthy records

# Amazon CloudFront
- A Content Delivery Network (CDN) service provided by AWS.
- **Globally distributed system of caching servers**.
- Caches copies of commonly requested files (static content) at edge locations.
- Delivers a local copy of the requested content from a nearby cache edge or Point of Presence (PoP).
- Accelerates delivery of dynamic content.
- Improves application performance and scaling.

## CloudFront Infrastructure
- **Edge locations**: Network of data centers that CloudFront uses to serve popular content quickly to customers. These are where content is cached for quick delivery.
- **Regional edge cache**: CloudFront location that caches content that is not popular enough to stay at an edge location. It is located between the origin server and the global edge location, acting as an intermediate cache layer.

## CloudFront Benefits
- **Fast and global**: Content is delivered quickly from edge locations close to users.
- **Security at the edge**: Provides built-in security features such as DDoS protection and SSL/TLS encryption.