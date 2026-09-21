# PF-04 — DNS Walkthrough

## What happens when someone opens my website?

When someone types my website address into a browser, the browser needs to find the server where the website is hosted.

### 1. Browser

The user enters a website address such as:

`lokesh-ai-ml-portfolio.netlify.app`

The browser needs the network address associated with that hostname.

### 2. DNS resolver

The browser or operating system asks a DNS resolver to find the address for the hostname.

A DNS resolver is a service that looks up DNS information on behalf of the user.

### 3. Nameserver

The resolver contacts the authoritative nameserver responsible for the domain information.

The nameserver contains the DNS records that tell the resolver where the hostname should point.

### 4. DNS record

A DNS record provides information about where a hostname should go.

Common records include:

- A record — maps a hostname to an IP address.
- CNAME record — points one hostname to another hostname.

For a hosted website, the exact record depends on the hosting provider and domain setup.

### 5. Response

The DNS resolver returns the information needed to reach the hosting service.

The browser can then connect to the correct server over HTTPS.

### 6. Website loads

The hosting service receives the request and returns the website files.

The browser downloads those files and renders the website.

## Simple flow

Browser  
→ DNS resolver  
→ authoritative nameserver  
→ DNS record  
→ hosting service  
→ HTTPS response  
→ website in the browser

## What I learned

DNS is the system that helps turn a human-readable website hostname into the information needed to reach the correct service.

A CNAME record does not contain the website itself. It points one hostname to another hostname, which can then be resolved to the appropriate destination.

For my current portfolio, Netlify provides the hosted HTTPS URL. I do not need to configure a custom domain for this assignment.
