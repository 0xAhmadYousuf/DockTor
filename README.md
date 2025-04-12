![Screenshot_6](https://github.com/user-attachments/assets/535fc71b-04c3-4bae-b575-0ace1af136a0)

# 🌐 DockTor

> Expose local apps to the Tor network via Docker.

DockTor is a minimal Docker project that installs Tor and launches a hidden service for your local TCP app. By default, it runs a sample Flask app and exposes it to the Tor network.

---

## 🚀 Features

- Runs a simple Flask server on `localhost:5000`
- Installs and configures Tor inside the container
- Automatically generates a `.onion` address
- Exposes any local TCP service to Tor
- Customizable and lightweight

---

## 📦 Usage

### 1. Clone the repo

```bash
git clone https://github.com/0xAhmadYousuf/DockTor.git
cd DockTor
```

### 2. Build the Docker image

```bash
docker build -t docktor .
```

### 3. Run the container

```bash
docker run --rm docktor
```

You’ll see output like:

```
Waiting for Tor to create the hidden service...
Your service is available at:
exampleabc123.onion
```

You can then access the Flask app through the Tor browser at the given `.onion` address.

---

## 🔧 Customize

To expose a different local service, modify:

- The `HiddenServicePort` line in the Dockerfile or `torrc`
- The service running on `localhost` (e.g., Flask, SSH, etc.)

---

## 🛡️ Disclaimer

This is for educational and testing purposes. Don’t expose sensitive services without proper authentication or sandboxing.

---

## 🧠 Author

[0xAhmadYousuf](https://github.com/0xAhmadYousuf)
```
