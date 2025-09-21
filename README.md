# CORS Vulnerability PoC

🔒 **Cross-Origin Resource Sharing (CORS) Misconfiguration Proof of Concept**

This repository contains an educational demonstration of a CORS vulnerability where a server incorrectly reflects the `Origin` header in the `Access-Control-Allow-Origin` response header, potentially allowing attackers to read sensitive data from authenticated user sessions.

## ⚠️ Disclaimer

**This tool is for educational and authorized security testing purposes only.** 

- Use only on systems you own or have explicit permission to test
- Do not use for malicious purposes
- Always follow responsible disclosure practices
- This is intended for security researchers, developers, and penetration testers

## 🎯 Vulnerability Description

### What is CORS?
Cross-Origin Resource Sharing (CORS) is a security feature implemented by web browsers that restricts web pages from making requests to a different domain than the one serving the web page.

### The Vulnerability
The target server (`experiences.octopus.com`) incorrectly reflects the `Origin` header in the `Access-Control-Allow-Origin` response header. This allows malicious websites to:

1. Make cross-origin requests with credentials (`credentials: 'include'`)
2. Read sensitive data from authenticated user sessions
3. Potentially steal session tokens, user data, or other protected information

### Attack Vector
```javascript
fetch('https://vulnerable-site.com/api/sensitive-data', {
  method: 'GET',
  credentials: 'include'  // Sends cookies/auth headers
})
```

If the server reflects the origin, the browser allows the request and the attacker can read the response.

## 🚀 Deployment

### Option 1: Vercel (Recommended)

1. **Fork this repository** to your GitHub account
2. **Connect to Vercel:**
   - Go to [vercel.com](https://vercel.com)
   - Sign in with your GitHub account
   - Click "New Project"
   - Import your forked repository
   - Deploy with default settings

3. **Your PoC will be live at:** `https://your-project-name.vercel.app`

### Option 2: Local Development

```bash
# Clone the repository
git clone https://github.com/yourusername/bug-2-v01.git
cd bug-2-v01

# Install dependencies
npm install

# Start local server
npm run dev

# Open http://localhost:3000
```

### Option 3: Manual Hosting

Simply upload the `index.html` file to any web server that supports static hosting.

## 📁 Project Structure

```
bug-2-v01/
├── index.html          # Main PoC page with enhanced UI
├── package.json        # Node.js dependencies and scripts
├── vercel.json         # Vercel deployment configuration
└── README.md           # This file
```

## 🎨 Features

- **Modern, responsive UI** with gradient backgrounds and animations
- **Real-time vulnerability testing** with loading states
- **Detailed error handling** and user feedback
- **Mobile-friendly design** that works on all devices
- **Security headers** configured for safe hosting
- **Educational warnings** and responsible disclosure notices

## 🔧 Technical Details

### Files Created:

1. **`index.html`** - Enhanced PoC with:
   - Professional styling with CSS gradients and animations
   - Responsive design for mobile and desktop
   - Loading states and error handling
   - Educational content and warnings
   - Clean, modern interface

2. **`package.json`** - Node.js configuration with:
   - Project metadata and description
   - Development scripts for local testing
   - Serve dependency for local development
   - Repository and homepage links

3. **`vercel.json`** - Vercel deployment configuration with:
   - Static site build settings
   - Security headers (X-Frame-Options, X-XSS-Protection, etc.)
   - Routing configuration
   - Runtime settings

## 🛡️ Security Considerations

The deployment includes several security headers:
- `X-Content-Type-Options: nosniff`
- `X-Frame-Options: DENY`
- `X-XSS-Protection: 1; mode=block`
- `Referrer-Policy: strict-origin-when-cross-origin`

## 📝 Usage Instructions

1. **Deploy the PoC** using one of the methods above
2. **Open the deployed URL** in a web browser
3. **Click "Test CORS Vulnerability"** to run the test
4. **Review the results:**
   - If vulnerable: Sensitive data will be displayed
   - If patched: Error message will be shown

## 🔍 How It Works

1. The PoC makes a cross-origin request to the target endpoint
2. It includes credentials (`credentials: 'include'`) to send cookies
3. It checks if the server reflects the origin in `Access-Control-Allow-Origin`
4. If reflected, it reads and displays the response data
5. If not reflected, it shows an error message

## 📚 Educational Value

This PoC demonstrates:
- How CORS misconfigurations can be exploited
- The importance of proper CORS configuration
- How attackers can steal sensitive data
- Real-world security testing techniques

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚖️ Legal Notice

This tool is provided for educational purposes only. Users are responsible for ensuring they have proper authorization before testing any systems. The authors are not responsible for any misuse of this tool.

---

**Remember: Always use security testing tools responsibly and only on systems you own or have explicit permission to test.**
