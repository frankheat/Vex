# Vex

**Vex** (Vulnerability Explorer) — a fast, clean web interface for searching CVEs via the [NIST NVD API v2.0](https://nvd.nist.gov/developers/vulnerabilities).

Navigate from vendor → product → version to find the exact CPE you need, then instantly see all associated vulnerabilities with CVSS scores, severity ratings, and full details.

<p align="center">
  <img src="docs/logo.png" width="200" />
</p>

![Vex screenshot](docs/screenshot.png)

---

## Usage

Open `index.html` directly in a browser, or serve it with any static web server (Apache, Nginx, etc.).

### NVD API key

Without a key: 5 requests / 30 s. With a key: 50 requests / 30 s.
Rate limit details: [nvd.nist.gov/developers/start-here](https://nvd.nist.gov/developers/start-here).

Enter your key directly in the UI — it is stored in `localStorage` and never sent anywhere except the NVD API.

Request a free key at [nvd.nist.gov/developers/request-an-api-key](https://nvd.nist.gov/developers/request-an-api-key).

## Data source

All vulnerability data is sourced in real time from the [NIST National Vulnerability Database](https://nvd.nist.gov/).
