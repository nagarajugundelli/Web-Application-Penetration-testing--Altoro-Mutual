# Reflected Cross-Site Scripting (XSS) — Search / Input Parameter

## Summary
A Reflected Cross-Site Scripting (XSS) vulnerability was identified on **Altoro Mutual (`testfire.net`)** where user-supplied input was reflected in the HTTP response without proper output encoding, allowing arbitrary JavaScript execution in the user's browser context.

## Affected Target & Parameter
- **Target:** Altoro Mutual (`http://testfire.net` — Authorized Practice Lab)
- **Affected Area:** Search / Input Parameter *(update with exact URL/parameter name if needed)*
- **Severity:** Medium

## Steps to Reproduce
1. Open the target page on Altoro Mutual (`testfire.net`) with traffic routed through Burp Suite.
2. Submit a unique test marker first to observe how and where the input reflects in the response.
3. Submit an XSS test payload in the vulnerable input/parameter and observe unencoded reflection and JavaScript execution in the browser.
4. Replay and verify the request and response in Burp Repeater to confirm consistent behavior.

## Proof of Concept (PoC)
- **Browser Alert Execution:** ![XSS Alert Popup](../Screenshots/xss-alert-popup.jpg)
- **HTTP Request & Response:** ![XSS Request and Response](../Screenshots/xss-request-response.jpg)

## Impact
An attacker could craft a malicious link containing an XSS payload and convince a victim to visit it, resulting in arbitrary JavaScript execution within the victim's browser session on that origin.

## Remediation
- Apply context-aware output encoding (HTML entity encoding for HTML body/attributes, or proper escaping for script contexts) before rendering user input.
- Validate/sanitize input where appropriate and implement a strong Content Security Policy (CSP).
