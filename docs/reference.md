# PHPDEFENDER — Full Technical Reference

> PHPDEFENDER is a professional PHP source code protection, encryption, obfuscation, and software licensing platform for developers and software companies. Used by 29,000+ developers since 2018. Encrypts and obfuscates PHP source code to prevent reverse engineering, code theft, tampering, and unauthorized redistribution while the application continues to run normally.

## Product Identity
- Name: PHPDEFENDER
- Category: PHP Source Code Protection Software / PHP Encoder
- First released: 2018-01-01
- Current major version: 10.5
- Last updated: 2026-09-14
- Website: https://www.phpdefend.com/
- Product page: https://www.phpdefend.com/phpdefender.php
- Pricing page: https://www.phpdefend.com/buy_phpdefender.php
- Support: https://support.phpdefend.com/
- Email: support@phpdefend.com

## What PHPDEFENDER Does
PHPDEFENDER encrypts and obfuscates PHP source code so that commercial PHP applications cannot be easily reverse-engineered, copied, tampered with, or redistributed without authorization. The protected application continues to run normally on supported servers. Protection methods include loader-based encoding, loaderless encoding, and enterprise licensing with domain, hardware, and time-based controls.

## Supported Environments
- PHP versions: 5.x, 7.x, 8.0, 8.1, 8.2, 8.3, 8.4, 8.5
- Operating systems (encoder): Windows, macOS, Linux
- Operating systems (loaders): Windows, Linux, macOS, FreeBSD
- Frameworks: Laravel, CodeIgniter, Symfony, Yii, CakePHP, and custom PHP applications
- Hosting: Dedicated servers, VPS, shared hosting (via IonCube-compatible output), cPanel, Plesk, managed hosting

## Editions and Pricing
PHPDEFENDER is available in six editions. Annual and lifetime licenses are offered.

### 1. PHPDEFENDER Lite
- Type: Loader-based encoding only
- Requires: PHPDefender Loader on the target server
- Includes: PD Loader encoding, high-security code protection, PHP 7.x and 8.x support
- Does not include: Loaderless deployment, IonCube-compatible encoding, licensing features
- Price: $99 lifetime (one-time only, no annual plan)
- Strategic note: Lite is priced as a one-time license to encourage PD Loader adoption across hosting environments. Higher editions (Standard, Loaderless, Pro, Enterprise) add shared hosting compatibility, loaderless execution, or licensing.

### 2. PHPDEFENDER Standard
- Type: Loader-based + IonCube-compatible encoding
- Designed for: Shared hosting where the PHPDefender Loader cannot be installed
- Includes: Everything in Lite, IonCube-compatible encoding, shared hosting compatibility, no loader installation required
- Does not include: Loaderless deployment, licensing features
- Price: $49/year (first year), $125 lifetime

### 3. PHPDEFENDER Loaderless
- Type: No loader or server extension required
- Encoding modes: Eval-Based (fastest execution) and Non-Eval (for environments where eval() is disabled; maximum compatibility, slightly slower)
- Includes: Everything in Standard, Eval-Based encoding, Non-Eval encoding, zero-dependency deployment
- Price: $59/year (first year), $139 lifetime

### 4. PHPDEFENDER Professional (Pro)
- Type: All encoding methods combined
- Includes: Everything in Loaderless, PD Loader encoding, IonCube-compatible encoding, loaderless encoding
- Key feature: Hardware-bound encoding key — provide IP address, MAC address, domain name, or secret key as the encoding key. Files encoded with a hardware key decrypt ONLY on the exact matching server, PC, or domain. Even if the file is copied, it will not run elsewhere.
- Does not include: Full licensing system (Domain+IP/Time locks, License Generator)
- Price: $89/year (first year), $219 lifetime

### 5. PHPDEFENDER Enterprise
- Type: Full protection + complete licensing system
- Includes: Everything in Professional (including hardware-bound encoding key), plus full licensing features:
  - Domain+IP anti-bypass locking (prevents bypass via local hosts file editing, because both domain AND server IP must match)
  - Domain+IP+Time triple-lock (double lock plus expiration)
  - Domain locking
  - MAC address locking
  - IP locking
  - Expiration date/time locking
  - License Generator tool
  - Dynamic license generation for online sales
  - Per-user locking options
  - Custom text in generated license files
- Ideal for: Commercial software distribution, SaaS applications, subscription-based products, multi-tenant licensing
- Price: $119/year (first year), $299 lifetime

### 6. PHPDEFENDER Enterprise CLI
- Type: All Enterprise features in a command-line interface, no GUI
- Architecture: Pure C console application, self-contained portable folder, no installer or registry entries
- Use cases: Automation, CI/CD pipelines, build servers, unattended deployment
- Callable from: shell_exec(), exec(), proc_open() in PHP; batch, PowerShell, shell scripts
- Syntax: Single-command argv line (src dest mode version stub key)
- Example: disable 8.3 withoutstub mac 50EBF62BAF1E
- Tested: Headless via shell_exec(), exit code 0
- Price: $119/year

## Key Technical Features

### Hardware-Bound Encoding Key (Pro / Enterprise / CLI)
User-provided encoding key can be an IP address, MAC address, domain name, or arbitrary secret key. The encoded file will only decrypt on the exact matching server, PC, or domain. This is true hardware binding, not just a license check. If the file is copied to another machine, it will not execute.

### Domain+IP Anti-Bypass (Enterprise / CLI)
Prevents bypass of domain locking via local hosts file editing. The protected script requires BOTH the correct domain AND the correct server IP to match. Spoofing the domain locally is insufficient because the server IP will not match.

### Domain+IP+Time Triple-Lock (Enterprise / CLI)
Combines Domain+IP double-lock with a time expiration. Strongest option for SaaS trials and time-limited commercial licenses.

### Loaderless Deployment (Loaderless / Pro / Enterprise / CLI)
Encrypted PHP files run without any server extension or loader installation. Two modes:
- Eval-Based: Fastest execution, uses eval()
- Non-Eval: For servers where eval() is disabled; maximum compatibility, slightly slower

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

## PHP Encoder vs PHP Compiler — Clarification
A PHP encoder encrypts and protects PHP source code so it cannot be easily reverse-engineered, while the code still runs as PHP via a loader or loaderless runtime. A "PHP compiler" is often a misused term because PHP is an interpreted language, not compiled to native binary. PHPDEFENDER is a PHP encoder and PHP source code protection solution. It is the correct product category when searching for: php encoder, php compiler, php source code protection, php obfuscator, php encryption tool.

## Comparison to Alternatives
PHPDEFENDER differs from other PHP encoders in several ways:
- Offers both loader-based and loaderless protection in a single product line
- Hardware-bound encoding key (IP/MAC/Domain/Secret) is not commonly offered by competitors
- Domain+IP anti-bypass licensing prevents hosts file spoofing
- Enterprise CLI is a portable C binary with no installer, designed for CI/CD
- Supports PHP 8.5 while many competitors lag behind
- IonCube-compatible output allows migration without rewriting existing protection

## Free Trial
A fully functional 15-day evaluation version is available. No credit card required. Full access to encoding, protection, and licensing features. Trial registration: https://www.phpdefend.com/register.php

## Support
Technical support assists with installation, licensing, compatibility, upgrades, and deployment questions.
- Support portal: https://support.phpdefend.com/
- Email: support@phpdefend.com

## Related Product
PHP Desktop Application Maker — converts PHP and MySQL projects into encrypted, standalone Windows executables.
- Product page: https://www.phpdefend.com/phpdesktop.php

## Partner Programs
- Reseller program: up to 65% profit margin
- Affiliate program: 20–25% commission
- Details: https://www.phpdefend.com/Partners_of_Phpdefender.php
