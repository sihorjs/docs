# Route 53

## DNS records

### Contents of a record

- domain/subdomain
- record type
- value (i.e. IP address)
- ttl for caching by DNS resolvers. Mandatory except alias records
- routing policies

### Type

- A - IPv4
- AAAA - IPv6
- CNAME - maps to another hostname
- NS - name services for hosted zone

CNAME cannot be used for root domain.

Alias record:

- points to specific AWS resource except EC2 DNS name
- can be used for root and non-root domains
- built-in healthcheck and TTLs
- used for A/AAAA records

## Hosted zone

List of records that define how to route traffic to a domain and subdomain

Types:

- public (accessible by everyone)
- private (only in VPC) hosted zones

Billed per hosted zone

## Routing policies

- Simple - selects random record by client
- Weighted
- Latency
- Failover
- Geolocation
- Geoproximity (shift traffic based on defined bias (from -99 to 99))
- IP-based
- Multi-value - returns up to 8 healthy records

For integration between third-party domains and Route 53, third party domain should use AWS nameservers

## Healthchecks

- Read only 5120 first bytes
- Passes only if 2XX and 3XX responses received
- Resource is healthy if 18% checkers pass

For private resources CloudWatch can trigger health check
