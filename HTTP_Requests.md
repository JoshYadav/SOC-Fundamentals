# 🌐 HTTP REQUEST METHODS (TYPES OF REQUEST METHODS)

HTTP request methods define **what action the client wants to perform on a server resource (URL)**.

---

## 1️⃣ GET

**Purpose:** Retrieve data from the server

- Sends data through the **URL**
- Data is **visible**
- Data is **not secure**
- Can be cached and bookmarked
- Used for **reading data**

Example:

```
GET /login?user=admin

```

📌 SOC relevance:

- Sensitive data in URL = security risk
- Used in recon and enumeration

---

## 2️⃣ POST

**Purpose:** Send data to the server

- Data is sent in the **request body**
- Data is **not visible in URL**
- More secure than GET (but still needs HTTPS)
- Used for **forms, login, uploads**

Example:

```
POST /login

```

📌 SOC relevance:

- Credential submission
- Malware data exfiltration often uses POST

---

## 3️⃣ PUT

**Purpose:** Replace an existing resource

- Replaces **entire content** of the target resource
- Sends updated data in request body
- If resource doesn’t exist, it may be created

Example:

```
PUT /user/123

```

📌 SOC relevance:

- Unauthorized PUT can lead to data tampering

---

## 4️⃣ DELETE

**Purpose:** Remove a resource

- Deletes the resource identified by the URL
- Permanent action (if allowed)

Example:

```
DELETE/user/123

```

📌 SOC relevance:

- Dangerous if access control is weak

---

## 5️⃣ OPTIONS

**Purpose:** Check allowed communication methods

- Tells which HTTP methods are allowed on a resource
- Used by browsers before requests (CORS)

Example:

```
OPTIONS /api

```

📌 SOC relevance:

- Helps attackers identify allowed actions
- Used in reconnaissance

---

## 6️⃣ TRACE

**Purpose:** Diagnostic loop-back test

- Echoes the received request
- Used to debug request path

⚠️ Security risk:

- Can expose headers and cookies
- Often disabled

📌 SOC relevance:

- Enabled TRACE = misconfiguration

---

## 7️⃣ CONNECT

**Purpose:** Establish a tunnel

- Used mainly for **HTTPS through proxy**
- Creates a secure tunnel

Example:

```
CONNECT example.com:443

```

📌 SOC relevance:

- Used in proxy-based communication
- Can hide malicious traffic

---

## 🔐 IMPORTANT NOTE (CORRECTION)

> GET is not insecure by itself.
> 
> 
> It becomes secure when used with **HTTPS**.
> 

---

## 🧠 EASY MEMORY TRICK

- **GET** → Read
- **POST** → Send
- **PUT** → Replace
- **DELETE** → Remove
- **OPTIONS** → Ask permissions
- **TRACE** → Debug
- **CONNECT** → Tunnel

---

## 📌 Web Server Examples (Correct)

- **Windows** → Microsoft IIS
- **Linux** → Apache / Nginx
