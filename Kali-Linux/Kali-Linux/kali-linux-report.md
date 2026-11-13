````
# Kali Linux – Footprinting and Reconnaissance Report

## 1. Introduction

Footprinting and reconnaissance are the first steps of cybersecurity. They involve collecting information about a target website, its domain, IP address, technologies, and DNS records.

In this practical, I used different Kali Linux tools to gather basic information about **networkwalks.com**.

## 2. Objectives

- Learn basic footprinting and reconnaissance.
- Collect domain information.
- Identify website technologies.
- Find domain IP addresses.
- Check HTTP response headers.
- Detect Web Application Firewalls.
- Gather DNS information.

## 3. Tools Used

| Tool | Purpose |
|---|---|
| WHOIS | Domain information |
| WhatWeb | Website technology detection |
| NSLookup | DNS and IP lookup |
| cURL | HTTP header checking |
| WAFW00F | Firewall detection |
| DNSRecon | DNS enumeration |

## 4. Practical Activities

### 4.1 WHOIS

**Command:**
```bash
whois networkwalks.com
````

**Purpose:**\
To collect domain registration information.

**Key Findings:**

- Registrar: GoDaddy
- Creation Date: 06 November 2019
- Expiry Date: 06 November 2027
- DNSSEC: Unsigned
- Domain privacy protection enabled.

**Explanation:**\
WHOIS provided basic registration and management information about the domain.

### **4.2 WhatWeb**

**Command:**

```
whatweb networkwalks.com
```

**Purpose:**\
To identify technologies used by the website.

**Key Findings:**

- Web Server: Apache
- IP Address: 192.232.216.135
- CMS: WordPress 7.1.4
- jQuery: 3.7.1
- WordPress Download Manager: 3.3.76
- HTTPS response: 200 OK

**Explanation:**\
WhatWeb identified the website's server, CMS, and other technologies.

### **4.3 NSLookup**

**Command:**

```
nslookup networkwalks.com
```

**Purpose:**\
To find the IP address associated with a domain.

**Key Findings:**

- DNS Server: 192.168.1.1
- Domain: networkwalks.com
- IPv4 Address: 192.232.216.135

**Explanation:**\
NSLookup successfully resolved the domain name into an IP address.

### **4.4 cURL**

**Command:**

```
curl -I https://networkwalks.com
```

**Purpose:**\
To check HTTP response headers.

**Key Findings:**

- HTTP Status: 200 OK
- Web Server: Apache
- Content Type: text/html
- WordPress REST API reference observed.

**Explanation:**\
cURL displayed the server response headers and provided basic information about the website.

### **4.5 WAFW00F**

**Command:**

```
wafw00f networkwalks.com
```

**Purpose:**\
To detect whether a Web Application Firewall is being used.

**Key Findings:**

- Target: networkwalks.com
- Detected WAF: ModSecurity
- Identification: SpiderLabs

**Explanation:**\
WAFW00F identified ModSecurity as the Web Application Firewall protecting the website.

### **4.6 DNSRecon**

**Command:**

```
dnsrecon -d networkwalks.com
```

**Purpose:**\
To collect DNS records and domain infrastructure information.

**Key Findings:**

- DNSSEC: Not configured
- SOA: ns6135.hostgator.com
- Name Servers:
  - ns6135.hostgator.com
  - ns6136.hostgator.com
- MX Record: mail.networkwalks.com
- Email-related SRV records were found.

**Explanation:**\
DNSRecon collected DNS information, including name servers, mail server details, and service records.

## **5. Summary of Findings**

| Tool     | Result                                |
| -------- | ------------------------------------- |
| WHOIS    | Domain registration details collected |
| WhatWeb  | Apache and WordPress detected         |
| NSLookup | IP address identified                 |
| cURL     | HTTP 200 OK response                  |
| WAFW00F  | ModSecurity detected                  |
| DNSRecon | DNS records collected                 |

## **6. Risk Analysis**

| Observation                | Potential Risk                      |
| -------------------------- | ----------------------------------- |
| Public domain information  | Information exposure                |
| Website technology details | Software identification             |
| Public IP address          | Infrastructure exposure             |
| HTTP headers               | Server information disclosure       |
| DNS records                | Infrastructure information exposure |

*These are potential risks, not confirmed vulnerabilities.*

## **7. Recommendations**

- Keep website software and plugins updated.
- Review publicly exposed technology information.
- Configure appropriate HTTP security headers.
- Regularly review DNS records.
- Restrict unnecessary DNS recursion.
- Maintain and monitor the Web Application Firewall.
- Review API access controls.

## **8. Screenshots and Evidence**

Screenshots are available in the `Screenshots` folder:

- WhatWeb
- WAFW00F
- NSLookup

## **9. Skills Learned**

- Domain information gathering.
- Website technology identification.
- DNS lookup and enumeration.
- HTTP header inspection.
- Web Application Firewall detection.
- Basic security risk analysis.

## **10. Conclusion**

This practical provided basic hands-on experience with footprinting and reconnaissance using Kali Linux tools.

I learned how to collect domain, website, DNS, and server information and understand its importance in cybersecurity.

```
```
