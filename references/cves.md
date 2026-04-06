# AI and LLM CVE References

This file indexes public CVEs relevant to self-hosted LLM platforms, inference servers, orchestration frameworks, and AI-adjacent tooling.

## How To Use This List

- Use it during architecture review and patch tracking for self-hosted AI components.
- Treat it as a starter index, not a complete vulnerability feed.
- Prefer upstream advisories and the NVD entry for current remediation status.

## CVE Index

| CVE | Component | Area | Short description |
| --- | --- | --- | --- |
| [CVE-2024-28224](https://nvd.nist.gov/vuln/detail/CVE-2024-28224) | Ollama | Local serving | DNS rebinding risk affecting localhost trust assumptions |
| [CVE-2024-37014](https://nvd.nist.gov/vuln/detail/CVE-2024-37014) | Langflow | Workflow platform | Remote code execution risk through unsafe component handling |
| [CVE-2024-7297](https://nvd.nist.gov/vuln/detail/CVE-2024-7297) | Langflow | Platform security | Web application weakness affecting AI workflow deployments |
| [CVE-2024-39719](https://nvd.nist.gov/vuln/detail/CVE-2024-39719) | Ollama | File handling | File existence or path-related information disclosure |
| [CVE-2024-39720](https://nvd.nist.gov/vuln/detail/CVE-2024-39720) | Ollama | Robustness | Malformed model input handling issue leading to instability |
| [CVE-2024-39722](https://nvd.nist.gov/vuln/detail/CVE-2024-39722) | Ollama | Artifact handling | Path traversal or unsafe file handling in model operations |
| [CVE-2024-42835](https://nvd.nist.gov/vuln/detail/CVE-2024-42835) | Langflow | Tool execution | Python tool execution risk with RCE implications |
| [CVE-2024-45436](https://nvd.nist.gov/vuln/detail/CVE-2024-45436) | Ollama | Archive extraction | Unsafe archive extraction or artifact handling behavior |
| [CVE-2024-48061](https://nvd.nist.gov/vuln/detail/CVE-2024-48061) | Langflow | Sandboxing | Unsandboxed code execution concerns in workflow components |
| [CVE-2025-30202](https://nvd.nist.gov/vuln/detail/CVE-2025-30202) | vLLM | Distributed serving | Protocol/runtime issue affecting serving stability or safety |
| [CVE-2025-46719](https://nvd.nist.gov/vuln/detail/CVE-2025-46719) | Open WebUI | Frontend security | Stored XSS that can lead to account takeover and possible RCE chains |
| [CVE-2025-59425](https://nvd.nist.gov/vuln/detail/CVE-2025-59425) | vLLM | Authentication | Timing attack against built-in API key validation |
| [CVE-2025-62164](https://nvd.nist.gov/vuln/detail/CVE-2025-62164) | vLLM | Inference integrity | Prompt embedding or request handling issue |
| [CVE-2025-63391](https://nvd.nist.gov/vuln/detail/CVE-2025-63391) | Open WebUI | Access control | Auth or configuration weakness in a self-hosted AI frontend |
| [CVE-2025-64495](https://nvd.nist.gov/vuln/detail/CVE-2025-64495) | Open WebUI | Frontend security | DOM XSS in rendered prompt or transcript content |
| [CVE-2025-64496](https://nvd.nist.gov/vuln/detail/CVE-2025-64496) | Open WebUI | Integration security | Direct connection path enabling code injection or unsafe execution |
| [CVE-2025-65958](https://nvd.nist.gov/vuln/detail/CVE-2025-65958) | Open WebUI | Network security | SSRF risk through connector or fetch functionality |
| [CVE-2025-65959](https://nvd.nist.gov/vuln/detail/CVE-2025-65959) | Open WebUI | Document rendering | XSS risk tied to notes, PDFs, or rendered artifacts |
| [CVE-2025-68664](https://nvd.nist.gov/vuln/detail/CVE-2025-68664) | LangChain | Serialization | Injection risk when user data is deserialized as framework objects |
| [CVE-2026-22773](https://nvd.nist.gov/vuln/detail/CVE-2026-22773) | vLLM | Multimodal serving | Crafted inputs causing denial-of-service in multimodal paths |
| [CVE-2026-25130](https://nvd.nist.gov/vuln/detail/CVE-2026-25130) | CAI | Agent CLI | Argument injection and unsafe command handling |
| [CVE-2026-25750](https://nvd.nist.gov/vuln/detail/CVE-2026-25750) | LangSmith Studio | Developer tooling | Token leakage through URL or configuration handling |
| [CVE-2026-26216](https://nvd.nist.gov/vuln/detail/CVE-2026-26216) | Crawl4AI | Crawling and ingestion | Unauthenticated RCE via executable hooks parameter |
| [CVE-2026-27597](https://nvd.nist.gov/vuln/detail/CVE-2026-27597) | Enclave | Isolation | Sandbox escape affecting agent or coding runtime assumptions |

## Review Checklist

- Which of these components are present in the stack today?
- Are self-hosted AI tools patched on the same cadence as standard web infrastructure?
- Does the deployment rely on localhost trust, browser trust, or unsandboxed component execution?
- Are connectors, renderers, and admin surfaces exposed to untrusted users?
