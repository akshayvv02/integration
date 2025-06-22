# 🔐 **JWT + OAuth 2.0 – Complete Integration Gist (with Interview Q\&A)**

---

## ✅ **1. What is JWT (JSON Web Token)?**

* A **compact**, **URL-safe**, **digitally signed** token format used for secure transmission of claims.
* Structure:

  ```
  <header>.<payload>.<signature>
  ```

### Components:

| Part          | Description                                                           |
| ------------- | --------------------------------------------------------------------- |
| **Header**    | Algo & token type (`{"alg": "HS256", "typ": "JWT"}`)                  |
| **Payload**   | Claims like `sub`, `role`, `exp`, etc. **Not encrypted**              |
| **Signature** | Generated using header+payload and **secret key** to ensure integrity |

---

## 🔄 **2. JWT Flow in HTTP/API**

1. **Login:**

   * `POST /login` → with username/password
2. **Server:**

   * Validates credentials
   * Creates and **signs JWT**
   * Sends JWT back to client
3. **Client:**

   * Stores token (in `localStorage`, `cookie`, etc.)
   * Sends token in header:

     ```
     Authorization: Bearer <JWT>
     ```
4. **Server (on every request):**

   * Verifies JWT signature
   * Validates claims (e.g., expiration, role, issuer)
   * Grants or denies access

---

## 🧠 **3. Why JWT Cannot Be Tampered**

> 🔒 **JWT is digitally signed** – only the server knows the secret key

### Common attack scenario:

* Attacker changes payload from `"role": "user"` → `"role": "admin"`
* But:

  * ❌ Cannot generate valid signature (no access to server's secret)
  * ✅ Server will recalculate signature and **detect mismatch**
  * ➡️ Token is **rejected as invalid/tampered**

### Signature ensures:

* **Integrity**
* **Authenticity**
* **Self-verifiability**

---

## 🔐 **4. JWT vs Basic Auth**

| Feature       | **JWT**                        | **Basic Auth**                    |
| ------------- | ------------------------------ | --------------------------------- |
| Format        | `Bearer <token>`               | `Basic base64(username:password)` |
| Security      | ✅ Signed, no creds after login | ❌ Sends creds every time          |
| Stateless     | ✅ Yes                          | ❌ Often requires sessions         |
| Custom Claims | ✅ Yes (roles, scopes, etc.)    | ❌ No                              |
| Scalability   | ✅ Great for APIs               | ❌ Not suitable for modern apps    |

---

## ⚙️ **5. JWT Implementation Requirements**

* 🔸 **On Server:**

  * Logic to generate and sign JWT using a secret or private key
  * Logic to decode and validate JWT on every request
* 🔸 **On Client:**

  * Store JWT securely (avoid XSS, CSRF)
  * Send it in HTTP header

---

## 🎯 **6. OAuth 2.0 + JWT**

> **OAuth 2.0 is a framework**
> **JWT is a token format used in that framework**

### When JWT is used in OAuth2:

* As **access\_token**: for API access
* As **id\_token**: for user identity (OpenID Connect)

> Not all OAuth tokens are JWTs — they could be **opaque strings**

---

## 🔍 **7. Opaque Token vs JWT Token in OAuth 2.0**

| Feature        | **Opaque Token**        | **JWT Token**           |
| -------------- | ----------------------- | ----------------------- |
| Self-contained | ❌ No                    | ✅ Yes                   |
| Needs lookup   | ✅ Yes (DB/Auth server)  | ❌ No                    |
| Revocation     | ✅ Easy                  | ❌ Hard (unless expired) |
| Custom claims  | ❌ Stored on server      | ✅ In token              |
| Stateless      | ❌ No                    | ✅ Yes                   |
| Performance    | ⏳ Slower                | ⚡ Faster                |
| Use Cases      | Internal/strict control | APIs, SPAs, mobile apps |

---

## 🧪 **8. How Server Detects Forged JWTs**

* Attacker **cannot**:

  * Guess the server's **secret key**
  * Sign modified payload with valid signature
* Even if header/payload are changed:

  * Signature check will **fail on server**
  * Token is invalid → **request rejected**

---

## 💡 **9. When to use JWT over opaque token?**

Use **JWT** when:

* You want **stateless**, scalable systems
* You want to pass **custom claims** (e.g., role, region) in token itself
* You don’t need server-side revocation

Use **opaque token** when:

* You need **instant revocation**
* You’re okay with **server-side token store**
* You want tighter control and privacy

---

## 📌 **10. JWT in Postman**

* Add to headers:

  ```
  Authorization: Bearer <your_JWT>
  ```
* OR use Authorization tab → Type = Bearer Token

---

## ✅ **INTERVIEW QUESTIONS + ANSWERS**

### 🔹 Q1: What is JWT and how does it work?

A JWT is a signed token carrying claims used for authentication and authorization. It includes a header, payload, and signature.

---

### 🔹 Q2: Can a client modify a JWT and re-sign it?

No. The client does not have the server’s secret key. Any modified token will fail signature validation.

---

### 🔹 Q3: Is JWT encrypted?

No. It is only **base64-encoded** and **signed**. Use HTTPS for secure transit.

---

### 🔹 Q4: Why use JWT over session or basic auth?

JWTs are stateless, self-contained, and secure after initial login. They scale well in distributed systems unlike sessions.

---

### 🔹 Q5: What prevents a user from changing their role in the token?

Signature validation ensures the token wasn't altered. Modified tokens will not match the server’s signature.

---

### 🔹 Q6: Does OAuth2 use JWT?

Yes, OAuth2 often uses JWT as the **access\_token** or **id\_token**, especially with OpenID Connect or identity providers like Google, Auth0, Azure AD.

---

### 🔹 Q7: What’s the tradeoff between opaque token and JWT in OAuth2?

Opaque tokens are safer to revoke and store data on server. JWTs are stateless and faster but harder to revoke.

---

### 🔹 Q8: How does server verify a JWT?

By re-generating the signature using header+payload and secret key, then comparing it to the token’s signature.

---

### 🔹 Q9: Can a JWT carry roles and custom claims?

Yes. That’s one of its main advantages — it can include `"role": "admin"` or other data directly in the payload.
