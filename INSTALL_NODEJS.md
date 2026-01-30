# Node.js Installation Guide for Nexora SAR

## ⚠️ Node.js Not Detected

To run this project, you need to install Node.js first.

## 📥 Installation Steps

### For Windows

1. **Download Node.js**
   - Visit: https://nodejs.org/
   - Download the **LTS (Long Term Support)** version
   - Choose the Windows Installer (.msi) - 64-bit

2. **Run the Installer**
   - Double-click the downloaded file
   - Click "Next" through the installation wizard
   - Accept the license agreement
   - Keep default installation path
   - **Important**: Make sure "Add to PATH" is checked
   - Click "Install"

3. **Verify Installation**
   Open a NEW terminal/command prompt and run:
   ```bash
   node --version
   npm --version
   ```
   You should see version numbers (e.g., v18.17.0 and 9.6.7)

### For Mac

1. **Option A: Using Official Installer**
   - Visit: https://nodejs.org/
   - Download the macOS Installer (.pkg)
   - Run the installer and follow prompts

2. **Option B: Using Homebrew** (Recommended)
   ```bash
   brew install node
   ```

3. **Verify Installation**
   ```bash
   node --version
   npm --version
   ```

### For Linux (Ubuntu/Debian)

```bash
# Update package index
sudo apt update

# Install Node.js and npm
sudo apt install nodejs npm

# Verify installation
node --version
npm --version
```

## 🚀 After Installing Node.js

Once Node.js is installed, follow these steps:

### 1. Install Project Dependencies

```bash
# In the nexora folder
npm install

# Then install client dependencies
cd client
npm install
cd ..
```

### 2. Run the Application

```bash
# Start both frontend and backend
npm run dev
```

### 3. Access the Application

Open your browser and go to:
- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:5000

## 🔍 Troubleshooting

### "npm is not recognized"

If you see this error after installing Node.js:
1. Close ALL terminal windows
2. Open a NEW terminal
3. Try again

If still not working:
1. Search for "Environment Variables" in Windows
2. Check if `C:\Program Files\nodejs\` is in your PATH
3. Add it if missing
4. Restart terminal

### Permission Errors (Mac/Linux)

If you get permission errors:
```bash
# Don't use sudo! Instead, fix npm permissions:
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.profile
source ~/.profile
```

### Installation Hangs

If npm install hangs:
```bash
# Clear npm cache
npm cache clean --force

# Try again
npm install
```

## 📚 Additional Resources

- [Node.js Official Docs](https://nodejs.org/en/docs/)
- [npm Documentation](https://docs.npmjs.com/)
- [Node.js Troubleshooting](https://nodejs.org/en/docs/guides/debugging-getting-started/)

## ✅ Quick Checklist

Before running the project, ensure:
- [ ] Node.js is installed (v16 or higher)
- [ ] npm is installed (comes with Node.js)
- [ ] You can run `node --version` successfully
- [ ] You can run `npm --version` successfully
- [ ] You've closed and reopened your terminal after installation

## 🎯 Next Steps

After installing Node.js:
1. ✅ Install dependencies: `npm install`
2. ✅ Install client dependencies: `cd client && npm install`
3. ✅ Start the app: `npm run dev`
4. ✅ Open browser: http://localhost:3000

---

**Need help? Check the QUICKSTART.md guide for detailed instructions!**
