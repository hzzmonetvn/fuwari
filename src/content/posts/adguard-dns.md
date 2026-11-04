---
title: "AdGuard DNS: Private DNS Filtering with dns.hzzmonet.io.vn"
published: 2026-11-04
description: "An overview of the AdGuard Home DNS service at dns.hzzmonet.io.vn, its supported encrypted DNS protocols, and how to configure a device."
tags: [DNS, AdGuard Home, Privacy]
category: Technology
draft: false
---

## What is this DNS service?

[AdGuard DNS](https://dns.hzzmonet.io.vn/) is a DNS resolver powered by AdGuard Home. It can filter requests to known advertising, tracking, and malicious domains, depending on the active filter lists and settings. Filtering happens at the domain lookup level; it is not a VPN and does not hide your IP address or encrypt other internet traffic.

The service is hosted on my server. DNS queries are processed by that server, so use it only if you are comfortable trusting its operator with your DNS activity. DNS filtering can also cause some sites or app features to stop working. If that happens, temporarily switch back to your usual DNS provider or adjust the local filtering settings where available.

## Connection options

Use one of the following methods. Your DNS client or operating system may use different labels for the same protocol.

### DNS-over-HTTPS (DoH)

Use this endpoint in a DoH-compatible browser, operating system, or DNS client:

```text
https://dns.hzzmonet.io.vn/dns-query
```

### DNS-over-TLS (DoT)

For a client that supports DNS-over-TLS, use:

```text
dns.hzzmonet.io.vn
```

The standard DoT port is `853`.

### DNS-over-QUIC (DoQ)

For a client that supports DNS-over-QUIC, use:

```text
dns.hzzmonet.io.vn
```

The standard DoQ port is `853`.

### Regular DNS

The service also listens on the standard DNS port `53`. This is generally suitable only for clients on networks explicitly configured to use this server. Ordinary DNS does not encrypt queries between the client and resolver, and the public server address may not be reachable from every network.

## Configure a device

In your device's Private DNS or encrypted DNS settings, select the matching protocol and enter the hostname above. For DoH, paste the complete HTTPS URL into the provider URL field. Avoid entering a URL into a hostname-only field.

After saving the setting, visit a few sites and confirm that apps still work. If the client reports a certificate or connection error, check the hostname, protocol, and network policy; do not disable certificate validation. A network that blocks encrypted DNS may also prevent the connection.

## Blocklist

The DNS service uses the [HzzMonet Blacklist](https://github.com/hzzmonetvn/blacklist), a community-maintained collection of ad- and tracker-blocking domains. Visit the repository for its current sources, formats, update details, and whitelist. The contents may change over time, and filtering can occasionally affect legitimate app features. If something stops working, switch DNS providers or contact the operator with the affected domain.

## Privacy and availability

Encrypted DNS protects the connection between your client and this resolver, but the resolver itself can see the domain names requested as part of handling DNS. The service may retain operational logs according to its server configuration. Do not use it for sensitive activity unless you have reviewed and accepted the operator's logging and privacy practices.

This is a self-hosted service and is provided as-is. Availability, filtering behavior, and supported clients can change. For maximum privacy or reliability, compare the service with a DNS provider you already trust and keep a fallback option available.
