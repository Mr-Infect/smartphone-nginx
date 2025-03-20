# Portfolio Hosting on a Rooted Smartphone - Introduction

This repository provides a step-by-step guide to hosting a personal portfolio website on a rooted Android smartphone. This approach offers a cost-effective way to get your website online, leveraging existing hardware.

## Key Concepts Explained

Here's a brief overview of the core technologies and concepts involved:

**1. Rooting (Android):**

* Rooting is the process of gaining privileged control (root access) over an Android device.
* This allows you to modify system files, install custom ROMs (like LineageOS), and use advanced tools.
* **Caution:** Rooting can void your warranty and introduce security risks if not handled carefully.

**2. LineageOS:**

* LineageOS is a free and open-source operating system for smartphones and tablet computers, based on the Android mobile platform.
* It provides enhanced customization, performance, and privacy features compared to stock Android.

**3. NetHunter:**

* Kali NetHunter is an Android penetration testing platform. It provides a suite of security tools and allows you to run Kali Linux on your Android device.
* We are using it here because it allows easy access to root features, and makes using termux more effective.

**4. Termux:**

* Termux is an Android terminal emulator and Linux environment app.
* It allows you to run Linux commands and install Linux software directly on your Android device.
* We use this to install and run our webserver.

**5. Nginx:**

* Nginx (pronounced "engine-x") is a high-performance web server.
* It's known for its speed, stability, and low resource consumption, making it ideal for hosting websites on resource-constrained devices like smartphones.
* Nginx will serve your website files to visitors.

**6. Web Hosting:**

* Web hosting is the service of providing storage space and access for websites on servers connected to the internet.
* When someone visits your website, their browser requests the website files from the server, and the server sends those files back.
* In this case, your android phone is the server.

**7. Servers:**

* A server is a computer or software system that provides services to other computers or users (clients).
* Web servers store and deliver website files.
* Servers can be physical machines or virtual instances in the cloud.

**8. Port Forwarding:**

* Port forwarding is a technique that allows external devices to access services on a device within a private network (like your home Wi-Fi).
* It involves configuring your router to forward specific ports (like port 80 for HTTP or 443 for HTTPS) to your phone's local IP address.
* This is required for your website to be accessible from the internet.

**9. Domains:**

* A domain name is a human-readable address for a website (e.g., `example.com`).
* It translates to an IP address, which is the numerical address of the server hosting the website.

**10. Purchasing Domains:**

* Domain names can be purchased from domain registrars like GoDaddy, Namecheap, Google Domains, etc.
* The cost of a domain name varies depending on the registrar and the domain extension (.com, .org, .net, etc.).
* You will also need to use a dynamic DNS service, because most home internet connections have dynamic IP addresses.

**11. Dynamic DNS:**

* Dynamic DNS is a service that updates a domain name's IP address to match a changing IP address. This is required because most home internet IP addresses change. Services like DuckDNS and No-IP, provide free and paid services.

## Repository Contents

This repository contains:

* A detailed step-by-step guide to installing and configuring Nginx on a rooted Android smartphone.
* Instructions on port forwarding and dynamic DNS setup.
* Security considerations.

## Disclaimer

* Rooting your Android device can void your warranty and introduce security risks. Proceed with caution.
* This guide is provided for educational purposes only.
* Hosting a website on a smartphone has limitations in terms of performance and reliability.
