# CKTech GhostCert 👻✅ — Phantom ACME Issuer

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Built For: PowerDNS](https://img.shields.io/badge/Built%20for-PowerDNS-orange.svg)](https://www.powerdns.com/)
[![ACME Automation](https://img.shields.io/badge/ACME-Automated-green.svg)](https://github.com/acmesh-official/acme.sh)

---

## 🔍 About

**GhostCert** is a professional-grade Bash script designed to simplify and automate wildcard SSL/TLS certificate issuance for domains managed through a **self-hosted PowerDNS authoritative DNS server**.

Built by **CK Technology** and developed by **Ghostkellz**, GhostCert handles:
- Dynamic DNS TXT validation using the **PowerDNS API**.
- Automated wildcard + apex certificate requests (example: `cktech.dev` + `*.cktech.dev`).
- Intelligent folder creation for certificate organization.
- Automated Nginx reloads after certificate deployment.
- Monthly renewal cronjob setup to stay compliant with Let's Encrypt expiry policies.

All with an easy-to-use CLI menu!

---

## 🔨 Features

- 🔄 Fully automates wildcard cert issuance using [acme.sh](https://github.com/acmesh-official/acme.sh)
- 🤔 DNS validation directly against **your own** PDNS API
- 🔍 Smart TXT record polling (with retries)
- 🏠 Auto installs certs into `/etc/nginx/certs/<domain>` structure
- 🔧 Auto reloads Nginx after every cert install
- 🕒 Monthly renewal cronjob, if missing
- 📅 Clean and professional output with emojis 🚀

---

## 🔻 Prerequisites

- [acme.sh](https://github.com/acmesh-official/acme.sh) installed and configured
- A running [PowerDNS Authoritative Server](https://doc.powerdns.com/authoritative/) with API access enabled
- Your PowerDNS API credentials already configured for `dns_pdns` plugin usage
- Bash shell environment (Linux server, typically Debian/Ubuntu preferred)

---

## 👨‍💻 How to Use

```bash
# Clone or download ghostcert.sh
chmod +x ghostcert.sh

# Run it
./ghostcert.sh
```

You'll be prompted for the **base domain** (e.g., `cktech.dev`) and the script will:
- Issue cert for `cktech.dev` and `*.cktech.dev`
- Create `/etc/nginx/certs/cktech.dev/` if missing
- Install certs into proper locations
- Reload nginx
- Setup monthly cron if missing

---

## 🔧 Install Example for Existing Domain (Manual)

```bash
acme.sh --install-cert -d ghostctl.io \
  --cert-file /etc/nginx/certs/ghostctl.io/cert.pem \
  --key-file /etc/nginx/certs/ghostctl.io/privkey.pem \
  --fullchain-file /etc/nginx/certs/ghostctl.io/fullchain.pem \
  --reloadcmd "systemctl reload nginx"
```

---

## 🔒 License

Released under the [MIT License](LICENSE) ✨

---

## 👻 About the Author

GhostCert was crafted by **CK Technology** 🌐 and **Ghostkellz** 👻 with love for clean infrastructure, self-hosting, and professional SSL automation.

> "Real ops automate the chaos."

---

## 🌐 Links
- [acme.sh Project](https://github.com/acmesh-official/acme.sh)
- [PowerDNS Documentation](https://doc.powerdns.com/authoritative/)
- [Let's Encrypt](https://letsencrypt.org/)

---

**💪 Pro self-hosting. Pro security. No compromises.**

