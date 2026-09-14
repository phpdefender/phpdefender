# Changelog

All notable changes to PHPDEFENDER and PHP Desktop Application Maker are
documented in this file.

The format is based on the version numbering used in the applications.
Version history is reconstructed from official release announcements and update
pages. Earlier versions (1.x through 7.3.8.9) are not documented here — records
for that period were lost and are not being fabricated.

---

## Product Status — As of 2026-08-14

As of **14 August 2026**, PHPDEFENDER has consolidated its product line due to
branding and product strategy changes.

**Two products remain in active development and sale:**

- **PHPDEFENDER** (six variants: Lite, Standard, Loaderless, Pro, Enterprise, Enterprise CLI)
- **PHP Desktop Application Maker (PDAM)**

All other applications in the PHPDEFENDER family have been discontinued. Their
sale, support, and updates have ended.

### Discontinued products (as of 2026-08-14)

- Ultimate Encoder
- PDW Encoder
- PHP Desktop Application Add-ons Compiler
- PD Mass Mailer
- PD File Protector
- PD Token

Historical release information for these discontinued products is preserved at
the bottom of this file for reference only.

### Current product 1: PHPDEFENDER (six variants)

PHPDEFENDER is the only PHP encoder product from phpdefend.com. It is
available in six variants:

| Variant | Purpose |
|---------|---------|
| **Lite** | Loader-based encoding only |
| **Standard** | Loader-based + IonCube-compatible encoding |
| **Loaderless** | No loader or server extension required |
| **Pro** | All encoding methods + hardware-bound encoding key |
| **Enterprise** | Full protection + complete licensing system |
| **Enterprise CLI** | All Enterprise features in a command-line interface for developers |

PHPDEFENDER consolidates all facilities from the previous Ultimate Encoder,
PHP Defender, and PDW Encoder products, distributed across these six variants.

**Important:** PHPDEFENDER is a completely new and separate project, not an
updated version of the previous products. It was built from the ground up with
a new architecture.

### Current product 2: PHP Desktop Application Maker (PDAM)

PHP Desktop Application Maker converts PHP and MySQL projects into encrypted,
standalone Windows executables. Current version: 8.59.

- Product page: https://www.phpdefend.com/phpdesktop.php

---

## PHPDEFENDER — Active Product

### [10.5.0.1] — 2026-09-14

**Solid security release — hardware-bound encoding and license enforcement**

This release implements significant security features across PHPDEFENDER's
loader-based and loaderless encoding paths.

#### Hardware-bound encoding key (Pro, Enterprise, CLI)

- Users can now encode PHP code using a **self-declared secret key, domain, IP, or MAC address as the encoding key**.
- The encoded file will **only decode into the Zend Engine on the exact matching location** (server, domain, IP, or machine).
- If the file is copied to another location, it will not decode or run. This is true hardware binding at the encoding layer, not just a license check.

#### Hardware MAC licensing enforcement (Enterprise and CLI)

- Enterprise and CLI license generation now **requires the original hardware MAC address**.
- Previously, license validation could accept a network adapter MAC (which can be spoofed or changed).
- From this version, the license is bound to the **physical hardware MAC** of the target machine.

#### Domain+IP and Domain+IP+Time combined locking (Loaderless)

- Loaderless applications now support **Domain+IP** and **Domain+IP+Time** combined locking.
- Domain+IP prevents bypass via local hosts file spoofing because both the domain AND the server IP must match.
- Domain+IP+Time adds an expiration layer for SaaS trials and time-limited licenses.

#### Performance and reliability

- **Removed MAC-based license read delay** from encoded files. License validation is now faster and does not introduce execution delay.

---

### [10.0.0.1] — 2026-08-14

**Initial release of the new PHPDEFENDER architecture**

This is the first release of PHPDEFENDER as a completely new and separate
project, consolidating functionality from the previous Ultimate Encoder,
PHP Defender, and PDW Encoder products into a single multi-variant platform.

#### Product consolidation

- PHPDEFENDER replaces the previous separate products (Ultimate Encoder, PHP Defender, PDW Encoder) with six variants: Lite, Standard, Loaderless, Pro, Enterprise, and Enterprise CLI.
- All other applications in the PHPDEFENDER family discontinued on this date, except PHP Desktop Application Maker (PDAM).

#### Loaderless edition — major improvements

The Loaderless edition introduces several major improvements over previous
loaderless encoding technology:

- **Advanced anti-reverse-engineering techniques** — new protection layers against code analysis and decompilation attempts.
- **Eval-less encoding** — beneficial because some production servers block or restrict `eval()`. Applications now run without requiring `eval()` to be enabled.
- **Improved PHP code checking and validation** — source code is validated before encoding, catching errors early.
- **Faster execution performance** — optimized runtime with reduced overhead.
- **More robust and reliable encoding technology** — rebuilt encoding engine with better stability.
- **Additional security and protection mechanisms** — multiple security layers beyond the base encoding.

#### New architecture

- PHPDEFENDER is a completely new and separate project, not an updated version of prior products.
- Built from the ground up with a new encoding engine and new deployment model.

---

### [9.1.0.1] — 2025-04-27

**Minor update** (previous PHP Defender product line)

- Added constant controller separately.
- Improved security patches.
- Fixed path error issue of `__FILE__` and `__DIR__` after encoding.
- Fixed startup issue with environment for trial version.

---

### [9.0.0.1] — 2024-12-16

**Major update** (previous PHP Defender product line)

- PHP 8.4 encoding now available on normal encoding and all dynamic encoding.
- Encoding now uses the latest IonCube encoding method. Encoded files no longer support IonCube Loader 12.02. Minimum required loader: **IonCube Loader 14** to run encoded files.
- Encoding support for PHP 8.4, 8.3, 8.2, 8.1, 7.4, and additional versions.
- Encoding language choice simplified and now set as a range (minimum and maximum PHP version to target).
- Added multiple security layers and improved encoding security.
- Fixed small bugs in the GUI.
- Fixed license corruption issue of application during Windows updates.

---

### [8.4.0.1] — 2023-02-17

**Minor update** (previous PHP Defender product line)

- Added PHP 7.4 encoding into normal encoding.
- Added PHP 7.4 to 8.1 combined encoding into normal encoding.
- Fixed major issue: "file corrupted. F16" error on all normal encoded pages in trial version for normal encoding.
- Improved security patches.
- Fixed trial version reinstallation within trial period issue.

---

### [8.3.0.1] — 2022-11-11

**Massive update under minor updates** (previous PHP Defender product line)

- Improved license repair tool with more options for users.
- Encoding now uses the latest IonCube encoding method. Encoded files no longer support IonCube Loader 10.2. Minimum required loader: **IonCube Loader 12.02** to run encoded files.
- Dynamic encoding: added new security against code decoding.
- PHP 8.1 encoding now available on normal encoding and all dynamic encoding.
- Added PHP 7.4 and 7.4-to-8.1 encoding into dynamic encoding.
- Added code checker and bypass system before encoding.
- PHP 8.1 normal encoding now supports encoding without php preamble.
- `__FILE__` and `__DIR__` magic constants can now be used in code without issues. This restriction was removed in this version.

---

### [8.0.0.1] — 2022-09-25

**Major update** (previous PHP Defender product line)

- Users now receive all application information from inside the application.
- Users can force-repair all application license issues without contacting support.
- Dynamic encoding: added new security against code decoding.
- PHP 8.1 encoding is now available on normal encoding. Dynamic encoding support was added automatically within a few days.
- Auto-renew notification 15 days before expiry for yearly licensed users, with direct renewal option from the application.
- PHP header correction for encoded files for more flexibility.
- Auto-update notification set up for all users (minor and major releases).
- GUI design completely changed for improved usability.
- License Manager changes: Dynamic encoding licenses are now generated per PHP version (not common as in previous versions). Normal encoding license generation remains unchanged.

---

### [7.3.8.9] and earlier — before 2022-09-25

**Records not available**

Version history for PHPDEFENDER 1.x through 7.3.8.9 is not documented in this
changelog. Records from that period were lost.

If you are a long-time PHPDEFENDER user and have saved update notifications,
release emails, or screenshots from earlier versions, please contact
support@phpdefend.com. Recovered information may be added to this changelog
with attribution.

---

## PHP Desktop Application Maker (PDAM) — Active Product

### [8.59] — 2026-05-15

**Major release**

- Chromium 130 engine integration.
- PHP 8.3.13 runtime support.
- MySQL and MariaDB 11 compliance (rebuilt database connections, fixed handshake and local connection drop issues).
- Windows native menu system (add, customize, or remove window layout menus without code overrides).
- Advanced EXE compilation and security (built-in protection options for raw source scripts, customizable app startup splash screens).

---

### [7.0.0.1] — 2024-11-02

**Update from 6.5.0.1**

- Internally changed many features to open a path for future updates.
- Fixed issues and removed the cause that stopped the compiler in step 5.

---

## Discontinued Products — Historical Reference Only

The following products were part of the PHPDEFENDER family but have been
discontinued as of **14 August 2026**. Their release histories are preserved
for reference. They are no longer sold, supported, or updated.

### PHP Desktop Application Add-ons Compiler

- **4.9** — 2024-11-02 (from 4.8: internally changed features and removed unnecessary ones per user recommendations; price reduced from $159 to $79 lifetime and from $69 to $39 yearly)

### Ultimate Encoder

- **2025.2** — 2025-04-29 (from 2025.1)
- **2025.1** — 2025-01-01 (Major update: reworked encoding based on newest loader, increased encoding limit)
- **2024.1** — 2024-04-27 (Major update: completely changed ultimate encoding with enhanced security)
- **2023.4** — 2023-02-17 (from 2023.3: added PHP 7.4 and 7.4-to-8.1 combined encoding into loader-based normal encoding)
- **2023.3** — 2022-11-20 (from 2023.1: encoded files no longer support IonCube Loader 10.2; require IonCube Loader 12+)
- **2023.1** — 2022-10-10 (Major update: new encoding security)

### PDW Encoder (Loaderless / Without Loader)

- **8.1.0.1** — 2025-04-28 (from 8.0.0.1: fixed magic constant path error)
- **8.0.0.1** — 2024-12-19 (Major update: support up to PHP 8.4 encoding, added encoding security)
- **7.5.0.1** — 2024-04-14 (from 7.3.0.3: new security patches, small bug fixes)
- **7.3.0.3** — 2023-07-12 (from 7.3.0.2: fixed small bug in License Manager / License Generator)
- **7.2.0.1** — 2022-10-24 (Major update: new Encoder 7 with high encoding security; Legacy Version 6 and Obsolete Version 5 retained)

### PD Mass Mailer

- **5.0.0.1** — 2022-07-05 (Desktop-based bulk email sending software)

### PD File Protector

- **2.5** — 2022-06-15 (GUI tool to protect any file from reading or viewing)

### PD Token

- **Initial launch** — 2023-01-09 (Internal currency for phpdefend.com; discounted pricing for purchases made with PD Token)

---

## Notes on This Changelog

### What is included

- Version numbers and dates from official release announcements
- Update details as published on official update pages
- Active product status as of 2026-08-14
- Full PHPDEFENDER 10.0 and 10.5 release details
- Full PDAM release history
- Discontinued product release histories for reference

This changelog documents public release notes beginning with version 8.0.0.1 (25 September 2022). Earlier releases are not covered.

*Last updated: 2026-09-14*
