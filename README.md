# Bug Test - Hosting Options

This directory contains a proof-of-concept HTML page for testing a specific bug on a target site.

## Files

- `bug-test.html` - The main test page containing the JavaScript code

## Quick Hosting Options

### Option 1: GitHub Pages (Free)
1. Create a new GitHub repository
2. Upload `bug-test.html` to the repository
3. Enable GitHub Pages in repository settings
4. Access via: `https://yourusername.github.io/repository-name/bug-test.html`

### Option 2: Netlify (Free)
1. Go to [netlify.com](https://netlify.com)
2. Drag and drop the `bug-test.html` file
3. Get instant hosting with a random subdomain
4. Custom domain available (optional)

### Option 3: Vercel (Free)
1. Go to [vercel.com](https://vercel.com)
2. Import the file or connect to GitHub
3. Deploy instantly with a custom subdomain

### Option 4: Local Development Server
```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000

# Node.js (if you have http-server installed)
npx http-server -p 8000
```
Then visit: `http://localhost:8000/bug-test.html`

### Option 5: Simple File Hosting
- **jsfiddle.net** - Paste the HTML content directly
- **codepen.io** - Create a new pen with the HTML
- **repl.it** - Upload and run as a web project

## Usage Instructions

1. Host the `bug-test.html` file on any of the above platforms
2. Open the hosted URL in a browser
3. Click "Run Bug Test" to execute the JavaScript code
4. Check the console and on-page results for the test output
5. The test will make a GET request to the target endpoint with credentials included

## Security Note

⚠️ **This is for authorized testing only.** Ensure you have proper permission before testing on any target site.

## Test Details

The test script:
- Makes a GET request to `https://nvio.mx/rQwvpWNw6lD4UMsr/Z9XJNOkbFG8xaEqg?ci=poctest`
- Includes credentials in the request
- Logs the response status and body
- Displays results both in the browser console and on the page

## Troubleshooting

- If you see CORS errors, the target site may not allow cross-origin requests
- Check browser console for additional error details
- Ensure you're testing from an HTTPS domain for security reasons
