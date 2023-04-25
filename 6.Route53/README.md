# Route 53

Route53 is a DNS web service which routes end users to internet applications hosted in AWS.
- Register any domain or create a hosted zone
- Reliable and cost effective
- Fully compliant with IPv6
- Connects user to EC2, ELB, and others ...
- Configure DNS Health Checks

## Records

- A: hostname to IPv4
- AAAA: hostname to IPv6
- CNAME: hostname to hostname, routes to any domain, only for non-root domain
- Alias: hostname to AWS Resource, works for root and nonroot domains, and contains native healthchecks.

## Routing

Traffic Flow: Route end users based on geo-proximity, latency, health etc
Route 53 Resolve: Create conditional forwarding rules and DNS endpoints to resolve custom names

- Latency Based Routing: Route users to region that provides lowest possible latency
Geo DNS: route end users based on geographic location

The Domain Name Service (DNS) may be private. In the case of a DNS failover, route website visitors to an alternate location to avoid site outages.

Health Checks: Route53 can monitor the health and performance of application
TTL (Time To Live): time to live, expiration date for DNS Record.

TXT/MX Recirds last between an hour and a day.
There are 5 TTL values in SOA (State of Authority)
SOA TTL - the interval at which SOA is refreshed

- Refresh
- Retry
- Expiry
- NXL

- Geoproximity Routing:
  - Route traffic to resources based on geographic location of users and resources.
  - Route more or less traffic to a given resource by specifiying a bias value.
  - A bias expands or shrinks the size of a geographic region from which traffic is routed to a resource
    - To expand or route more traffic to the resource (1 -> 99)
    - To shrink or route less traffic to the resource (-1 -> -99)