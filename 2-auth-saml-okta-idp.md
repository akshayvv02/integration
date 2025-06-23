## 🔐 **Integration Security: Gist Summary**

### ✅ OAuth 2.0

* **Purpose**: Authorization (delegated access without password)
* **Actors**: Resource Owner, Client, Resource Server, Auth Server
* **Tokens**: Access Token, Refresh Token
* **Grant Types**: Authorization Code (most secure), Client Credentials, Password, Implicit

### 🔒 SSL/TLS

* **Purpose**: Secure transport layer (encryption in-transit)
* **Used in**: HTTPS, SFTP, API calls
* **TLS 1.2/1.3** replaces SSL
* **Process**: TLS Handshake → Certificate → Encrypted session

### 👤 SSO (Single Sign-On)

* **Purpose**: One login for many apps
* **Tech behind**: OAuth, SAML, OpenID Connect
* **Benefit**: Seamless access, less password fatigue

### 🔄 SAML

* **Purpose**: Authentication + SSO
* **Format**: XML assertions
* **Used in**: Enterprise SSO (Okta, ADFS)
* **Flow**: User → SP → IDP → Auth → Assertion → SP

### 🏷️ IDP (Identity Provider)

* **Purpose**: Authenticates users and issues identity tokens/assertions
* **Examples**: Google, Okta, Auth0, ADFS
* **Protocols used**: SAML, OAuth, OIDC

---

## 🔁 Comparison Table

| Concept | Function        | Format | Used In           |
| ------- | --------------- | ------ | ----------------- |
| OAuth   | Authorization   | JWT    | APIs, Web Apps    |
| SAML    | Authentication  | XML    | SSO, Enterprise   |
| SSO     | Unified Login   | —      | Web & Mobile Apps |
| SSL/TLS | Encryption      | —      | HTTPS, APIs       |
| IDP     | Identity Source | Varies | SAML, OIDC, OAuth |

---

## 📋 Interview Questions (Quick)

* **Q1**: OAuth vs SAML?
  **A**: OAuth = authorization (APIs), SAML = authentication (SSO)

* **Q2**: How does OAuth work?
  **A**: Uses tokens (access/refresh) to delegate access to resources

* **Q3**: What is an IDP?
  **A**: Authenticates users and issues assertions (e.g., Okta)

* **Q4**: Why is TLS needed in APIs?
  **A**: Encrypts traffic; protects token and data in transit

* **Q5**: SSO real-world example?
  **A**: Google login for Gmail, YouTube, Drive from one sign-in

---

| Term          | Stands For                         | Purpose                                       | Used In                                            |
| ------------- | ---------------------------------- | --------------------------------------------- | -------------------------------------------------- |
| **OAuth 2.0** | Open Authorization                 | **Delegated access** to APIs (scopes, tokens) | **Mobile apps, APIs, cloud services**              |
| **SAML 2.0**  | Security Assertion Markup Language | **Single Sign-On (SSO)** via browser          | **Web enterprise apps**                            |
| **SSO**       | Single Sign-On                     | **Allow login once → access multiple apps**   | Implemented using **SAML**, **OAuth**, or **OIDC** |



