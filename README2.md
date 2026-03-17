# 🧠 Recommended Setup (Laptop / Dev)

## ▶️ Start (manual, foreground — best for dev)

```bash
node scripts/run-node.mjs gateway
```

or:

```bash
pnpm openclaw gateway
```

---

## 🛑 Stop

```text
Ctrl + C
```

---

# ❗ Your Current Command

```bash
node scripts/run-node.mjs gateway restart
```

### What it does

* Restarts **systemd service**
* Runs in background
* Harder to debug

👉 Not ideal for local testing

---

# 🔧 If You Want to Use Service Mode (Optional)

### ▶️ Start / Restart

```bash
systemctl --user restart openclaw-gateway.service
```

### 🛑 Stop

```bash
systemctl --user stop openclaw-gateway.service
```

---

# ⚠️ Important Rule

```text
DEV MODE → use terminal (manual)
SERVICE MODE → use systemctl
```

👉 Do NOT mix both

---

# 🔥 Clean Recommendation (Your Case)

Use this:

```bash
# start
pnpm gateway:dev   # or pnpm openclaw gateway

# stop
Ctrl + C
```

And disable service completely:

```bash
systemctl --user disable openclaw-gateway.service
systemctl --user stop openclaw-gateway.service
```

---

# 🧾 Final Cheat Setup

### Dev (recommended)

```bash
pnpm gateway:dev
# Ctrl + C to stop
```

### Service (if needed later)

```bash
systemctl --user restart openclaw-gateway.service
systemctl --user stop openclaw-gateway.service
```

---

# Bottom Line

> For your laptop: **don’t use `gateway restart`**

Use:

```bash
pnpm gateway:dev
```

---

If you want, I can:

* create a **1-command alias (`oc up` / `oc down`)**
* or set up **dual-mode (dev + prod profile switching)** cleanly
