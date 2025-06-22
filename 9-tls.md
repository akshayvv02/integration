## ✅ **TLS 1.3: Final Gist for Quick Revision**

### 🔐 **Purpose:**

TLS (Transport Layer Security) secures communication between client & server — replacing old, insecure SSL protocols.

---

### 🚫 SSL vs TLS:

* **SSL 2.0/3.0**: Deprecated (due to POODLE, BEAST, etc.)
* **TLS 1.2**: Common today
* ✅ **TLS 1.3**: Modern, secure, fast

---

### 🔁 **TLS 1.3 Handshake Flow:**

1. **ClientHello →**

   * Sends: TLS version, cipher suites, random number, **ephemeral public key (key share)**
2. **ServerHello →**

   * Sends: TLS version, chosen cipher, random number, **ephemeral public key (key share)**, certificate
3. **Both compute shared secret** using ECDHE
4. **Derived keys (via HKDF)**: Client write key, server write key
5. **Encrypted "Finished" messages exchanged**
6. ✅ **Secure, encrypted communication begins**

---

### 🔐 **Encryption Begins When?**

* After the **Finished** messages (encrypted with derived symmetric keys) are exchanged.

---

### 🧠 **Shared Secret:**

* Not used directly for encryption
* Used as input to HKDF (Key Derivation Function)
* Generates fast **symmetric keys** (e.g., AES-GCM)

---

### 🔁 **New Key per Session:**

* Yes — every TLS connection = new **ephemeral key pair** & new shared secret
* Ensures **Perfect Forward Secrecy** (PFS)

---

### 💡 **Why TLS 1.3 is Better:**

* 1-RTT handshake (faster)
* No support for old ciphers (RSA, RC4, etc.)
* No renegotiation/compression (reduces attack surface)
* Only **forward-secret key exchanges** (ECDHE)

---

### 🔐 Common Use Cases:

* HTTPS, API calls, OAuth servers, SFTP over TLS
* Java/MuleSoft integrations, Kafka with TLS encryption

---

### 🧠 **Interview Flash Q\&A:**

**Q1: What replaces SSL?**
✅ TLS (v1.2 or v1.3)

**Q2: When does encryption begin in TLS 1.3?**
✅ After "Finished" messages are exchanged

**Q3: What is the shared secret used for?**
✅ As input to derive symmetric encryption keys (not direct encryption)

**Q4: Is a new key generated every session?**
✅ Yes — for forward secrecy (new ECDHE pair per session)

**Q5: What is ECDHE?**
✅ Ephemeral Diffie-Hellman over elliptic curves — used for secure key agreement
