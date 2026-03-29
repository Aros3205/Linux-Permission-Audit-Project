## 📌 Overview

This project demonstrates how improper file permissions in Linux systems can introduce security vulnerabilities and how they can be identified and remediated using both numeric (octal) and symbolic methods.

---

## 🛠️ Tools Used

* Kali Linux
* Bash Terminal

---

## 🧠 Objectives

* Understand Linux file permission structures
* Identify insecure permission configurations
* Apply remediation using least privilege principles
* Demonstrate both numeric and symbolic permission management

---

## 🔢 Numeric Method

### 📸 Vulnerability (777 Permissions)

![Numeric Vulnerability](screenshots/numeric-vulnerability.png)

A file was assigned `777` permissions, making it readable, writable, and executable by all users. This introduces a security risk as any user can modify the file.

---

### 📸 Remediation (600 Permissions)

![Numeric Fix](screenshots/numeric-fix.png)

Permissions were restricted using:

```bash
chmod 600 file1.txt
```

This ensures only the file owner has read and write access.

> While permissions such as 744 allow read access to other users, a stricter permission of 600 was applied to enforce the principle of least privilege and prevent unauthorized access.

---

## 🔤 Symbolic Method

### 📸 Vulnerability (Others Write Access)

![Symbolic Vulnerability](screenshots/symbolic-vulnerability.png)

Using symbolic notation, write permission was granted to others:

```bash
chmod o+w file2.txt
```

This resulted in a world-writable file, allowing unauthorized modification.

---

### 📸 Remediation (Selective Permission Removal)

![Symbolic Fix](screenshots/symbolic-fix.png)

Permissions were corrected using:

```bash
chmod go-rw file2.txt
```

This removed read and write access from group and others, securing the file.

> Only existing permissions were removed to maintain precise control over access rights, avoiding unnecessary modification of non-existent execute permissions.

---

## 🔍 Key Takeaways

* Misconfigured permissions can expose systems to unauthorized access
* The principle of least privilege is critical in securing files
* Numeric permissions provide quick configuration
* Symbolic permissions allow precise and granular control
* Permissions can be applied selectively without affecting other files

---

## 📎 Conclusion

This project highlights the importance of proper file permission management in Linux systems and demonstrates practical techniques used to identify and mitigate security risks.

---

## 🔗 Author

**Your Name**
