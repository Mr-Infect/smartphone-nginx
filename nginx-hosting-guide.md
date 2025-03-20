# 📱 Simple Portfolio Hosting Using a Rooted Smartphone 🚀

This guide outlines how to host a simple portfolio website using a rooted Android smartphone running NetHunter and LineageOS. Let's turn your spare phone into a mini web server! ✨

**Prerequisites:**

* 📱 Rooted Android phone with NetHunter and LineageOS.
* 💻 Termux installed.
* 📂 Your portfolio website files (HTML, CSS, JavaScript, images, etc.).
* 📶 A Wi-Fi connection (recommended for stability).

**Step 1: Setting up Termux and Debian 🐧**

1.  **Open Termux:** Launch the Termux app. 🚀
2.  **Update Packages:** Run the following commands to update the package list:

    ```bash
    apt update && apt upgrade -y
    ```

3.  **Install `proot-distro`:** This tool allows you to install and run Linux distributions within Termux. 🛠️

    ```bash
    apt install proot-distro -y
    ```

4.  **Install Debian:** Install a Debian environment. 📦

    ```bash
    proot-distro install debian
    ```

5.  **Enter the Debian Environment:** Access the Debian environment. 🚪

    ```bash
    proot-distro login debian
    ```

**Step 2: Installing and Configuring Nginx 🌐**

1.  **Update Debian Packages:** Once inside the Debian environment, update the package list: 🔄

    ```bash
    apt update && apt upgrade -y
    ```

2.  **Install Nginx:** Install the Nginx web server: 🚀

    ```bash
    apt install nginx -y
    ```

3.  **Check Nginx Status:** Verify that Nginx is installed: ✅

    ```bash
    systemctl status nginx
    ```

    * If it's not running, start it: ▶️

        ```bash
        systemctl start nginx
        ```

    * To enable nginx to start automatically on boot: ⚙️

        ```bash
        systemctl enable nginx
        ```

4.  **Find Nginx's Document Root:** The default directory where Nginx looks for website files is usually `/var/www/html`. 📂

**Step 3: Placing Your Portfolio Files 📁**

1.  **Transfer Files:** You need to transfer your portfolio website files to the `/var/www/html` directory. There are several ways to do this:

    * **Using `scp` (if you have another computer on the same network):** 💻➡️📱
        * Enable SSH in Termux (`apt install openssh` and configure it).
        * Use `scp` from your computer to copy the files.
    * **Using `termux-setup-storage` and moving files:** 📂➡️📱
        * Run `termux-setup-storage` in the main termux window.
        * Place your files into the `storage/shared` directory.
        * Then from within the debian proot, copy the files.

        ```bash
        cp /storage/shared/* /var/www/html/
        ```
    * **Using a text editor within Termux:** 📝
        * Use `nano` or `vim` to create files manually.

2.  **Replace Default Files:** Delete the default `index.nginx-debian.html` file in `/var/www/html`: 🗑️

    ```bash
    rm /var/www/html/index.nginx-debian.html
    ```

**Step 4: Port Forwarding (if using Wi-Fi) 📡**

1.  **Find Your Phone's Local IP Address:** 🔍

    * In Termux, run `ip addr`.
    * Look for the `wlan0` interface and note the `inet` address.

2.  **Access Your Router's Settings:** 🌐

    * Open a web browser on your computer and enter your router's IP address.
    * Log in with your router's credentials.

3.  **Find Port Forwarding Settings:** ⚙️

    * Look for sections like "Port Forwarding," "NAT," or "Virtual Servers."

4.  **Create a Port Forwarding Rule:** ➡️

    * Forward port 80 (HTTP) to your phone's local IP address.
    * If using HTTPS, also forward port 443.

5.  **Save and Apply Changes:** ✅

**Step 5: Dynamic DNS (if needed) 🌐➡️🔗**

1.  **Choose a Dynamic DNS Provider:** DuckDNS, No-IP, DynDNS.
2.  **Create an Account and Domain:** 📝
3.  **Install a Dynamic DNS Client:** 💻➡️📱
4.  **Configure the Client:** ⚙️

**Step 6: Testing Your Website 🧪**

1.  **From Your Local Network:** 🏠

    * Open a web browser on a device on the same Wi-Fi network.
    * Enter your phone's local IP address.

2.  **From the Internet (after port forwarding and dynamic DNS):** 🌍

    * Open a web browser on any device with internet access.
    * Enter your dynamic DNS domain name.

**Step 7: Security Considerations 🔒**

1.  **Firewall:** AFWall+ is a good firewall application. 🛡️
2.  **Updates:** Keep Termux, Debian, and Nginx updated. 🔄
3.  **HTTPS:** Obtain an SSL/TLS certificate from Let's Encrypt. 🔐
4.  **Backups:** Regularly back up your website files. 💾

**Important Notes:**

* This setup is for basic hosting. For more advanced features, you may need to configure Nginx further. 🛠️
* Power consumption and heat are important factors. Keep your phone plugged in and monitor its temperature. 🌡️🔌
* If you are using cellular data, be aware of data usage. 📊
* Consider using a "no sleep" app to keep your phone from sleeping. 😴➡️🌞

Enjoy hosting your portfolio! 🎉
