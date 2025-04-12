![DockTor Banner](https://github.com/user-attachments/assets/75516ea8-ee49-4004-bf78-e6390fa2e140)

# 🌐 DockTor

> Expose local apps to the Tor network via Docker.

DockTor is a modular Docker-based project that helps you expose any local service (Flask, Django, FastAPI, Node.js, Go, PHP, and more) to the Tor network using a hidden service.

Each project lives in its own directory with its own Dockerfile, and is fully customizable.

---

## 🚀 Features

- Automatically creates a `.onion` hidden service address
- Exposes any app running on localhost (any language or framework)
- Docker-based for easy portability and isolation
- A `base/` folder with a reusable, minimal Tor layer

---

## 📂 Project Structure

```
DockTor/
├── base/         # Base Dockerfile to extend/customize in other projects
├── flask/        # Flask app exposed via Tor
├── fastapi/      # FastAPI app exposed via Tor
├── django/       # Django app exposed via Tor
├── php/          # Raw PHP exposed via Tor
├── laravel/      # Laravel app exposed via Tor
├── node/         # Node.js app exposed via Tor
├── go/           # Go app exposed via Tor
├── ...
└── README.md     # You're here!
```

Each subdirectory contains its **own README.md** file with setup and usage instructions specific to that framework or language.

---

## 🧱 Base Tor Dockerfile

The [`base/tor.Dockerfile`](./base/tor.Dockerfile) provides a minimal foundation with only Tor installed. You can copy and extend it into any subproject like so:

```Dockerfile
FROM base-tor-image

# Add your app setup and run command here
```

Use this when building a custom service or a new language integration.

---

## 📦 Quick Start Example

### 1. Clone the repo

```bash
git clone https://github.com/0xAhmadYousuf/DockTor.git
cd DockTor/flask
```

### 2. Build the Docker image

```bash
docker build -t docktor-flask .
```

### 3. Run the container

```bash
docker run --rm docktor-flask
```

You’ll see:

```
Waiting for Tor to create the hidden service...
Your service is available at:
abc123xyz.onion
```

You can now access your app through the Tor Browser at that `.onion` address.

---

## ⚙️ Supported Projects

- ✅ Python
  - [x] Raw Python
  - [x] Flask
  - [x] Django
  - [x] FastAPI
- ✅ PHP
  - [x] Raw PHP
  - [x] Laravel
- ✅ JavaScript
  - [x] Node.js
- ✅ Go
  - [x] Raw Go apps

More languages and templates coming soon!

---

## 🔐 Security Disclaimer

This project is for **educational/testing purposes**. Don't expose sensitive services to the public internet or Tor without proper hardening, authentication, and isolation.

---

## 🧠 Author

[0xAhmadYousuf](https://github.com/0xAhmadYousuf)
