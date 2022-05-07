---
title: "Remote Traffic Interception for Thick Application Assessments"
date: 2022-05-07T13:34:43+10:00
draft: false
---

## Thick application testing scenarios

Thick application security testing, from the perspective of a consultancy, usually involves a customer who has obtained an off the shelf solution from a vendor or who has engaged an external developer to produce the internal tooling. It is substantially less common for the customer to have developed the application-under-test inhouse. The impact of this is usually the customer does not have the institutional understanding or documentation about the inner workings of the application and primarily manage the infrastructure which supports the application.

Another aspect affecting how testing is performed, is in the initial scoping stage, in which the engagement is framed around some variety of breach scenario. Most of the time, this is framed around a single workstation takeover, where an end-user with low rights access to the application succomes to a phishing or similar attack which provides and adversary access to the application at their access level, with elevated privileges on the workstation.

## "As Deployed" Thick Application Testing

This frames common thick application testing where the customer would provide a domain joined user credential, a corporate workstation with the application-under-test deployed as usual, such as through a CCM platform, (Software Center, etc) and a local administrative credential on the workstation.

In order to achieve a comprehensive assessment of the application-under-test, the tester needs to get visiblity of three primary scopes:

- The applications presence on disk
- The applications network communications with the backend systems
- The applications interaction with the host operating system, and functionality exposed by such

Of these, the network communications is often the most fruitful area, as there is an explicit security boundary between code running under the control of the adversary and code running under the control of the organisation.

Some security protections on the workstation can get in the way of achieving this visibility. Enterprises often lock down network and proxy settings, limiting even local administrators from changing these settings. Also, many thick applications are not proxy aware or use unusual or even proprietary network protocols. It is also notable that these limitations are very similar to mobile application testing and much of this advice would extend there as well

## External router based network observation

For most assessments involving a customer device, the quickest approach to network visibility is intercepting the entire device. The requirements to achieve this are as follows:

- The intercepting device or VM must be able to service both a client connection to an upstream network and a server/router connection to the device-under-test
- The interceptor must provide basic network services to the device-under-test, such as DHCP and atleast DNS configuration, if not DNS relaying
- The interceptor must provide traffic forwarding to the upstream network to allow normal application and domain operation
- The interceptor must be able to redirect traffic of interest to an intercepting transparent proxy or similar to allow observation and manipulation of the traffic

## My approach to external interception

This will use the following moving parts:

- A kali linux or similar linux VM to act as a NAT router
- A usb ethernet NIC to connect to the upstream network
- A usb WiFi NIC to host an access point for the workstation

I rely on usb NIC's primarily to allow usb passthrough to provide network level isolation of the NAT router VM from any other network traffic on my testing laptop. Under VMware, Libvirt, etc, it is possible to pass the usb NIC through to the VM with no host visibility of the network traffic. For the WiFi NIC, this also allows the router VM to control 100% of the configuration of the NIC.

## Configuration

### Setting up WiFi drivers

This step varies based on the network card being used. I currently use an RTL8812AU based USB NIC which has readily available drivers under the Aircrack-NG github project. These are easily installed under Kali following the instructions from the GitHub repo: [https://github.com/aircrack-ng/rtl8812au]

### Hosting an access point

For ap hosting, I frequently use berate-ap, from SensePost. It is a useful utility to have around for Wireless testing, but also is the simplest one line way to establish an access point.

```bash
apt update
apt install -y berate-ap
berate_ap [wireless interface] [upstream interface] [ssid name] [preshared key]
```

Berate-ap will automatically set up DHCP in the 192.168.12.0 range, and all the necessary packet forwarding and masquerade NAT configuration in iptables.

### Redirecting traffic

For traffic redirection to a local service, a one-line iptables command will configure the necessary behaviour. In this example, lets say BurpSuite is listening on port 8081, on the 192.168.12.1 interface, in a transparent proxy configuration. Two iptables rules would configure port 80 and port 443 redirection to this BurpSuite instance:

```bash
iptables -t nat -A PREROUTING -s 192.168.12.0/24 -p tcp -m tcp --dport 80 -j REDIRECT --to-port 8081
iptables -t nat -A PREROUTING -s 192.168.12.0/24 -p tcp -m tcp --dport 443 -j REDIRECT --to-port 8081
```

### BurpSuite Specific

If you keep both the normal proxy listener, as well as a transparent listener, you can hit the normal proxy port directly from a browser to download the BurpSuite CA certificate to install on the workstation.

### Wireshark FTW, Python for the Lulz

For unknown traffic, running wireshark will provide some immediate visibility. Python is generally useful as a make a thing happen problem solver, so dont be afraid to build something quickly that is bespoke to this app.
