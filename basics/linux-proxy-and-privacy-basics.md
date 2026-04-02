# Linux Basics - Proxy Configuration and Privacy Concepts

## 📌 Overview

Today I learned about proxies, VPNs, and encrypted communication. I also configured an HTTP proxy in Linux using a configuration file and observed its behavior.

---

## 🔧 Proxy Configuration (APT)

I created a proxy configuration file for APT:

/etc/apt/apt.conf.d/proxy.conf

Added the following lines:

Acquire::http::Proxy "[http://IP:PORT](http://IP:PORT)";
Acquire::https::Proxy "[http://IP:PORT](http://IP:PORT)";

This tells APT to route its traffic through the specified proxy.

---

## 🧪 Practical Observation

* The proxy was working because `apt update` started successfully
* The connection became very slow
* Eventually, the process had to be stopped

### Conclusion:

* Free proxies are often slow and unreliable
* Proxy configuration was correct, but performance depends on proxy quality

---

## 🧠 What is a Proxy?

A proxy is an intermediary between the user and the internet.

Instead of connecting directly:

You → Proxy → Internet

The target server sees the proxy’s IP instead of the user’s real IP.

---

## 🔐 VPN (Virtual Private Network)

A VPN provides:

* IP masking
* encrypted communication

Traffic flow:

You → VPN → Internet

Unlike proxies, VPNs encrypt traffic, making them more secure.

---

## 📧 Encrypted Email (ProtonMail)

* Provides end-to-end encrypted email
* Emails are encrypted so that even the provider cannot read them (in theory)
* Based in Switzerland (privacy-focused laws)

---

## ⚠️ Important Notes

* Proxies do not provide full anonymity
* The proxy server can still see the user’s real IP
* Free proxies may be unsafe or unreliable
* Privacy tools must be used carefully to avoid leaks

---

## 🧩 What I Learned

* How to configure a proxy using a Linux config file
* How system behavior can be modified using configuration files
* The difference between proxy and VPN
* Practical limitations of free proxies

---

## 🚀 Next Steps

* Configure and use Tor proxy
* Test IP changes using proxy tools
* Explore secure routing methods like proxychains
