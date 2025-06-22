## 🔗 **GIST: HTTPS, SFTP, JDBC – Integration Focus**

### 🔐 HTTPS (Hypertext Transfer Protocol Secure)

* **Protocol:** Secure HTTP over SSL/TLS
* **Port:** 443 (default)
* **Used For:** REST APIs, Web Services, secure browser communication
* **Security:** Encrypts data in transit (via TLS); uses X.509 certificates
* **Key Concepts:** Handshake, Public-Private Keys, Certificates, CA, Cipher Suites

---

### 📂 SFTP (SSH File Transfer Protocol)

* **Built on:** SSH (Port 22)
* **Secure:** ✅ Encrypts *both credentials and file content*
* **Auth Modes:**

  * **Username/Password** (encrypted via SSH)
  * **SSH Key-based Auth** (preferred for automation, secure)

    * Generate SSH key pair → Add public key to server → Use private key to login
* **Used For:** Secure B2B file exchange, file-based ETL, batch data transfer
* **Common Tools:** `sftp`, `psftp`, `WinSCP`, Mule/Java connectors

---

### 🔌 JDBC (Java Database Connectivity)

* **What:** Java API for connecting to relational databases
* **Used For:** Executing SQL queries via Java/Integration platforms
* **Supports:** SELECT, INSERT, UPDATE, DELETE
* **Requires:** JDBC Driver per DB (MySQL, PostgreSQL, Oracle)
* **Security Tip:** Store DB creds securely via env variables/secrets manager
* **Integration Use:** Reading from DB, writing ETL output to DB

---

## 🤔 Clarified Concepts (Interview-Friendly Q\&A)

**Q1. What is key-based authentication in SFTP?**
A: Instead of a password, a private key is used on the client, and the public key is stored on the server. It’s the same SSH concept used in GitHub SSH cloning. More secure and ideal for automation.

**Q2. How are credentials encrypted in SFTP?**
A: In SFTP, even when using username/password, the entire session (including credentials) is encrypted over the SSH tunnel. No risk of password sniffing.

**Q3. Difference: FTP vs FTPS vs SFTP?**

| Feature      | FTP               | FTPS             | SFTP                             |
| ------------ | ----------------- | ---------------- | -------------------------------- |
| Encryption   | ❌ No              | ✅ Yes (SSL/TLS)  | ✅ Yes (SSH)                      |
| Port         | 21                | 21/990           | 22                               |
| Data Channel | Separate          | Separate         | Single SSH session               |
| Auth         | Username/Password | User/Pass + Cert | Password or SSH Key              |
| Use Today    | Legacy systems    | Some secure use  | ✅ Preferred secure file transfer |

---

## 💼 Interview Questions

### 🔹 Q1. Why is SFTP preferred over FTP in integration scenarios?

**A:** Because it encrypts both authentication credentials and file data, reducing security risks.

### 🔹 Q2. What’s the difference between SFTP and FTPS?

**A:** SFTP runs over SSH (port 22), uses one connection, and supports key-based auth. FTPS runs over SSL/TLS (port 21/990), uses multiple connections.

### 🔹 Q3. How does JDBC connect to a database securely?

**A:** By using JDBC URL with secure parameters (`useSSL=true`) and credentials managed via environment variables or vaults.

### 🔹 Q4. Can you use JDBC with NoSQL databases?

**A:** No, JDBC is designed for relational databases only.

### 🔹 Q5. Why do we use HTTPS in API integrations?

**A:** To ensure that data in transit is encrypted and tamper-proof using TLS.
