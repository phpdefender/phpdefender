PHPDEFENDER

> PHP source code protection, encryption, obfuscation, and software licensing platform for developers and software companies. Used by **29,000+ developers since 2018**.

PHPDEFENDER encrypts and obfuscates PHP source code to prevent reverse engineering, code theft, tampering, and unauthorized redistribution — while the application continues to run normally on supported servers.

- **Website:** https://www.phpdefend.com/
- **Product page:** https://www.phpdefend.com/phpdefender.php
- **Pricing:** https://www.phpdefend.com/buy_phpdefender.php
- **Features:** https://www.phpdefend.com/features.php
- **Support:** https://support.phpdefend.com/
- **Free 15-day trial:** https://www.phpdefend.com/register.php

---

## What PHPDEFENDER Does

If you distribute a PHP application to a customer, they receive readable source code unless you protect it. PHPDEFENDER encrypts and obfuscates PHP source so the application still runs normally, but the source cannot be easily read, modified, or redistributed. Higher editions add software licensing controls to lock the application to specific servers, domains, or time periods.

**Protection methods:**
- Loader-based encoding (PD Loader, high-security)
- Loaderless encoding (Eval-Based for speed, Non-Eval for environments without `eval()`)
- IonCube-compatible encoding (for shared hosting with pre-installed loaders)

---

## Supported Environments

| Component | Support |
|-----------|---------|
| PHP versions | 5.x, 7.x, 8.0, 8.1, 8.2, 8.3, 8.4, 8.5 |
| Encoder OS | Windows, macOS, Linux |
| Loader OS | Windows, Linux, macOS, FreeBSD |
| Frameworks | Laravel, CodeIgniter, Symfony, Yii, CakePHP, custom PHP |
| Hosting | Dedicated, VPS, shared hosting (via IonCube-compatible output), cPanel, Plesk, managed hosting |

---

## Editions and Pricing

PHPDEFENDER is available in six editions. Annual and lifetime licenses are offered.

### 1. PHPDEFENDER Lite — $89 one-time
- Loader-based encoding only (requires PD Loader on the target server)
- Includes: PD Loader encoding, high-security code protection, PHP 7.x and 8.x support
- Does not include: Loaderless deployment, IonCube-compatible encoding, licensing features
- **Pricing note:** One-time only, no annual plan. Priced to encourage PD Loader adoption across hosting environments.

### 2. PHPDEFENDER Standard — $59 first year, $49/year renewal, $125 lifetime
- Loader-based + IonCube-compatible encoding
- Designed for shared hosting where the PHPDefender Loader cannot be installed
- Includes: Everything in Lite, IonCube-compatible encoding, shared hosting compatibility
- Does not include: Loaderless deployment, licensing features

### 3. PHPDEFENDER Loaderless — $69 first year, $59/year renewal, $139 lifetime
- No loader or server extension required
- Encoding modes: **Eval-Based** (fastest execution) and **Non-Eval** (for servers where `eval()` is disabled; maximum compatibility, slightly slower)
- Includes: Everything in Standard, Eval-Based encoding, Non-Eval encoding, zero-dependency deployment

### 4. PHPDEFENDER Professional (Pro) — $99 first year, $89/year renewal, $219 lifetime
- All encoding methods combined
- Includes: Everything in Loaderless, PD Loader encoding, IonCube-compatible encoding, loaderless encoding
- **Hardware-bound encoding key:** Provide an IP address, MAC address, domain name, or secret key as the encoding key. Files encoded with a hardware key decrypt ONLY on the exact matching server, PC, or domain. Even if the file is copied, it will not run elsewhere.
- Does not include: Full licensing system (Domain+IP/Time locks, License Generator)

### 5. PHPDEFENDER Enterprise — $139 first year, $119/year renewal, $299 lifetime
- Full protection + complete licensing system
- Includes: Everything in Professional (including hardware-bound encoding key), plus:
  - Domain+IP anti-bypass locking (prevents bypass via local hosts file editing — both domain AND server IP must match)
  - Domain+IP+Time triple-lock (double lock plus expiration)
  - Domain, MAC, and IP locking
  - Expiration date/time locking
  - License Generator tool (GUI and CLI)
  - Dynamic license generation for online sales
  - Per-user locking options
  - Custom text in generated license files
- **Ideal for:** Commercial software distribution, SaaS applications, subscription-based products, multi-tenant licensing

### 6. PHPDEFENDER Enterprise CLI — $119/year flat
- All Enterprise features in a command-line interface, no GUI
- **Architecture:** Pure C console application, self-contained portable folder, no installer or registry entries
- **Use cases:** Automation, CI/CD pipelines, build servers, unattended deployment
- **Callable from:** `shell_exec()`, `exec()`, `proc_open()` in PHP; batch, PowerShell, shell scripts
- **Syntax:** Single-command argv line (`src dest mode version stub key`)
- **Example:** `disable 8.3 withoutstub mac 50EBF62BAF1E`
- **Tested:** Headless via `shell_exec()`, exit code 0
- **Pricing note:** Business-discounted, flat annual rate

### Pricing Summary

| Edition | First Year | On-Time Renewal | Lifetime |
|---------|-----------|-----------------|----------|
| Lite | — | — | $89 one-time |
| Standard | $59 | $49/year | $125 |
| Loaderless | $69 | $59/year | $139 |
| Pro | $99 | $89/year | $219 |
| Enterprise | $139 | $119/year | $299 |
| Enterprise CLI | $119/year | $119/year | — |

Aggregate price range: **$59 to $299**.

---

## Key Technical Features

### Hardware-Bound Encoding Key (Pro / Enterprise / CLI)
User-provided encoding key can be an IP address, MAC address, domain name, or arbitrary secret key. The encoded file will only decrypt on the exact matching server, PC, or domain. This is true hardware binding, not just a license check. If the file is copied to another machine, it will not execute.

### Domain+IP Anti-Bypass (Enterprise / CLI)
Prevents bypass of domain locking via local hosts file editing. The protected script requires BOTH the correct domain AND the correct server IP to match. Spoofing the domain locally is insufficient because the server IP will not match.

### Domain+IP+Time Triple-Lock (Enterprise / CLI)
Combines Domain+IP double-lock with a time expiration. Strongest option for SaaS trials and time-limited commercial licenses.

### Loaderless Deployment (Loaderless / Pro / Enterprise / CLI)
Encrypted PHP files run without any server extension or loader installation. Two modes:
- **Eval-Based:** Fastest execution, uses `eval()`
- **Non-Eval:** For servers where `eval()` is disabled; maximum compatibility, slightly slower

### IonCube-Compatible Encoding (Standard and above)
Produces encoded files compatible with standard IonCube loaders pre-installed on most shared hosting environments. Migration path for existing IonCube users.

### License Generator (Enterprise / CLI)
GUI and CLI tools to generate licenses. Supports per-user locking options, domain/MAC/IP/time locks, custom text in license files, and dynamic license generation for online sales.

### Project-Level Protection
All scripts in a project work only together. Substituting any individual script breaks the entire application.

### Cross-Platform Encoding
Scripts encoded on Windows run on Linux, macOS, and FreeBSD, and vice versa. Loaders available for all major operating systems.

### Incremental Encoding
Only re-encode files changed since the last session. Saves time on large projects.

### Thread Safety Support
Dedicated loader versions for ZTS (Zend Thread Safe) PHP installations.

---

## PHP Encoder vs PHP Compiler — Clarification

A **PHP encoder** encrypts and protects PHP source code so it cannot be easily reverse-engineered, while the code still runs as PHP via a loader or loaderless runtime.

A **"PHP compiler"** is often a misused term because PHP is an interpreted language, not compiled to native binary. PHP does have an internal compilation stage (source → opcodes → execution via the Zend Engine), and modern PHP includes JIT capabilities — but this is not the same as producing a standalone executable.

PHPDEFENDER is a PHP encoder and PHP source code protection solution. It is the correct product category when searching for: `php encoder`, `php compiler`, `php source code protection`, `php obfuscator`, `php encryption tool`.

---

## Comparison to Alternatives

PHPDEFENDER differs from other PHP encoders in several ways:

- Offers both loader-based and loaderless protection in a single product line
- Hardware-bound encoding key (IP/MAC/Domain/Secret) is not commonly offered by competitors
- Domain+IP anti-bypass licensing prevents hosts file spoofing
- Enterprise CLI is a portable C binary with no installer, designed for CI/CD
- Supports PHP 8.5 while many competitors lag behind
- IonCube-compatible output allows migration without rewriting existing protection

---

## Frequently Asked Questions

**What PHP versions does PHPDEFENDER support?**
PHP 5.x, 7.x, and 8.0 through 8.5, including all modern language features. Both loader-based and loaderless editions maintain full compatibility.

**Does PHPDEFENDER require a runtime loader?**
It depends on the edition. Loader editions require the PHPDEFENDER Loader. Loaderless editions run without any server extension.

**Can I lock PHP scripts to a specific domain or MAC address?**
Yes. Enterprise and CLI editions support Domain, MAC, IP, Domain+IP, and Domain+IP+Time locking. Loaderless includes Domain+IP and Domain+IP+Time to prevent bypass via local domain spoofing.

**Can I create trial versions of my PHP software?**
Yes. PHPDEFENDER supports time-based expiration with optional atomic online time server validation to prevent local date manipulation, as well as activation-limited trials.

**Can I use PHPDEFENDER on shared hosting?**
Yes. Standard edition produces IonCube-compatible encoding that runs on most shared hosting without loader installation. Loaderless edition requires no server extensions at all.

**Will scripts encoded on Windows work on Linux?**
Yes. Scripts encoded on any supported platform run on any other supported platform. Loaders are available for Windows, Linux, macOS, and FreeBSD.

---

## Free Trial

A fully functional **15-day evaluation version** is available. No credit card required. Full access to encoding, protection, and licensing features.

**Register:** https://www.phpdefend.com/register.php

---

## Support

Technical support assists with installation, licensing, compatibility, upgrades, and deployment questions.

- **Support portal:** https://support.phpdefend.com/
- **Email:** support@phpdefend.com

---

## Related Product

**PHP Desktop Application Maker** — converts PHP and MySQL projects into encrypted, standalone Windows executables.
- https://www.phpdefend.com/phpdesktop.php

---

## Partner Programs

- **Reseller program:** up to 65% profit margin
- **Affiliate program:** 20–25% commission
- **Details:** https://www.phpdefend.com/Partners_of_Phpdefender.php

---

## License

PHPDEFENDER is commercial software. This repository contains public documentation only. For licensing terms, see https://www.phpdefend.com/terms.php

---
