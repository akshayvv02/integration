
## 🌐 Commonly Used Ports for Protocols

| **Port**      | **Protocol/Service**     | **Use Case / Notes**                      |
| ------------- | ------------------------ | ----------------------------------------- |
| **20**        | FTP (Data Transfer)      | Used for transferring data (active mode)  |
| **21**        | FTP (Control)            | Command/control channel for FTP           |
| **22**        | SSH / SFTP / SCP         | Secure shell, secure file transfer        |
| **23**        | Telnet                   | Unsecured remote login (legacy, insecure) |
| **25**        | SMTP                     | Sending email (non-encrypted)             |
| **53**        | DNS                      | Domain name resolution                    |
| **67/68**     | DHCP                     | Dynamic IP address allocation             |
| **80**        | HTTP                     | Web traffic (non-secure)                  |
| **110**       | POP3                     | Receiving email (non-encrypted)           |
| **143**       | IMAP                     | Email retrieval (non-encrypted)           |
| **161/162**   | SNMP                     | Network monitoring/management             |
| **389**       | LDAP                     | Directory access (unencrypted)            |
| **443**       | HTTPS                    | Secure web traffic                        |
| **465**       | SMTP over SSL            | Secure email sending                      |
| **993**       | IMAP over SSL            | Secure email retrieval                    |
| **995**       | POP3 over SSL            | Secure email retrieval                    |
| **1433**      | Microsoft SQL Server     | SQL Server DB connections                 |
| **1521**      | Oracle DB                | Oracle listener port                      |
| **3306**      | MySQL                    | MySQL/MariaDB database port               |
| **5432**      | PostgreSQL               | PostgreSQL DB access                      |
| **5671/5672** | AMQP / RabbitMQ          | Messaging queue (5671 is secure with TLS) |
| **5984**      | CouchDB                  | RESTful JSON API for CouchDB              |
| **6379**      | Redis                    | Default Redis port (in-memory DB/cache)   |
| **6380**      | Redis over TLS           | Secure Redis port                         |
| **7001**      | WebLogic (HTTP)          | Admin/console access                      |
| **8080**      | HTTP (Alternative)       | Common for testing/dev environments       |
| **8443**      | HTTPS (Alternative)      | SSL for custom apps                       |
| **9092**      | Apache Kafka (plaintext) | Kafka broker default                      |
| **2181**      | Apache ZooKeeper         | Kafka’s coordination service              |
| **9093**      | Apache Kafka (TLS/SSL)   | Secure Kafka communication                |
| **8888**      | Jupyter Notebook / APIs  | Localhost development (e.g. ML apps)      |
| **27017**     | MongoDB                  | NoSQL DB default port                     |

---

## 📌 Interview Tip:

Always mention that ports can be **customized** depending on the firewall, network policies, or reverse proxies in enterprise deployments.
