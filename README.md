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

### Rate limits

The NVD API allows 5 requests / 30 s ([details](https://nvd.nist.gov/developers/start-here)). Responses are cached for 5 minutes to make the most of that budget.

NVD API keys raise the limit to 50 requests / 30 s, but they cannot be used here: the NVD server rejects the CORS preflight triggered by the `apiKey` header, so keyed requests never work from browser-side JavaScript.

## CVSS scoring

A CVE can carry several CVSS scores (NVD, the CNA that published it, ADPs) across different CVSS versions, and they often disagree, sometimes by several severity levels. Vex takes the **worst case**: the highest base score across all sources and versions is used for the severity badge, sorting and counts. A `+N` marker next to the badge flags CVEs with additional scores, and the detail panel lists every score with its source, type (Primary = NVD, Secondary = CNA/ADP) and vector.

## Data source

All vulnerability data is sourced in real time from the [NIST National Vulnerability Database](https://nvd.nist.gov/).
