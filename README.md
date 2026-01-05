
# ⚫ BlackEye (Modified Version) - Phishing Toolkit with Cloudflared & LAN Support

This is a modified version of the **BlackEye** phishing toolkit. The original version was limited to Ngrok and LocalTunnel for exposing the phishing server to the internet. These have been removed and replaced with:

- ✅ **Cloudflared** support (secure, reliable, no warning screens)
- ✅ **Localhost (LAN)** option for internal network testing
- ✅ Optional support to manually SSH tunnel (e.g. via localhost.run)
- ❌ Ngrok/LocalTunnel fully removed (no more forced downloads or errors)

---

## 📦 Requirements

- `php`
- `cloudflared` (for WAN tunneling)
- `bash`

Install `cloudflared`:

```bash
wget https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb
sudo dpkg -i cloudflared-linux-amd64.deb
```

---

## 🚀 How to Use

1. **Clone the repository** (if not already):
   ```bash
   git clone https://github.com/ashardian/BlackEye.git
   unzip blackeye-v2.zip
   cd blackeye-v2
   ```

2. **Make the script executable**:
   ```bash
   chmod +x blackeye.sh
   ```

3. **Run the script**:
   ```bash
   ./blackeye.sh
   ```

4. **Choose a phishing template**, e.g. Instagram, Facebook, etc.

5. **Choose the tunnel method**:
   ```
   1) Cloudflared (WAN access)
   2) Localhost (LAN only)
   ```

6. 🔗 The script will:
   - Launch PHP server on `localhost:5555`
   - If **Cloudflared** is chosen: Start a WAN tunnel and show the link
   - If **Localhost** is chosen: Show your LAN IP (e.g., `http://192.168.1.5:5555`)

---



![alt text](https://github.com/ashardian/BlackEye/blob/main/img/1.png)

## 🌐 Optional: Using SSH Tunnel (like localhost.run)

If you prefer not to use Cloudflared, you can also manually run:

```bash
ssh -R 80:localhost:3333 ssh.localhost.run
```

This will give you a public URL like `https://yourname.localhost.run`

---

## 🧠 Notes

- All Ngrok/LocalTunnel code and logic has been removed.
- The phishing pages still reside in the `sites/` directory.
- You must ensure the phishing template folder (like `instagram/`) exists before launching.

---

## 🛡️ Disclaimer

This tool is strictly for **educational purposes** and **authorized security testing** only. Unauthorized use is illegal and unethical. Use responsibly.

---
