## Getting Started with Gemini 2.0 on Linux and MacOS 💻

This guide provides instructions for setting up the Gemini 2.0 web console on Linux and MacOS, including solutions to common issues.

### Prerequisites ✅

* **Node.js and npm:** Ensure you have supported versions installed. Use `node -v` and `npm -v` to check.
* **Gemini AI Key:**  Obtain your API key from [https://aistudio.google.com/apikey](https://aistudio.google.com/apikey). 🗝️
* **Google Chrome:**  Recommended for optimal performance. 🌐

### Installing Node.js and npm on Linux (e.g Ubuntu) 🐧

You can install Node.js and npm on Ubuntu using the following methods:

**Using apt:**

1. Update package lists: `sudo apt update` 🔄
2. Install Node.js and npm: `sudo apt install nodejs npm`

### Installing Node.js and npm on MacOS 🍎

If necessary, install Node.js and npm using one of these methods:

**Official Installer:**

1. Download the macOS installer from [https://nodejs.org](https://nodejs.org). ⬇️
2. Run the installer.
3. Verify installation with `node -v` and `npm -v`. ✅

**nvm:**

1. Install Node.js: `nvm install 22` (restart your terminal if needed). 🔄
2. Verify versions: `node -v` and `npm -v`. ✅

**Homebrew:**

1. Install Node.js: `brew install node@22`. 🍺
2. Verify versions: `node -v` and `npm -v`. ✅


### Setting Up the Gemini Web Console 🕹️

1. **Clone the repository:**
   ```bash
   git clone https://github.com/google-gemini/multimodal-live-api-web-console.git
   cd multimodal-live-api-web-console
   ```

2. **Update environment variables:**
   * In the `.env` file, add your API key:
     ```
     # create your own API KEY at https://aistudio.google.com/apikey
     REACT_APP_GEMINI_API_KEY='<YOUR_GEMINI_API_KEY>'
     ```

3. **Update `package.json`:**
   * Add this `content_security_policy` to prevent errors:
     ```json
     "content_security_policy": {
       "extension_pages": "script-src 'self'; object-src 'self';",
       "sandbox": "sandbox allow-scripts allow-forms allow-popups allow-modals; script-src 'self' 'unsafe-inline' 'unsafe-eval'; child-src 'self';"
     }
     ```

4. **Install dependencies:**
   ```bash
   npm install
   npm audit --force
   ```

5. **Start the app:**
   ```bash
   npm start
   ```

6. **Access the console:** Open `localhost:3000` in your browser. 💻

You can now use the Gemini 2.0 API web console. See the documentation for examples and further information: [https://github.com/google-gemini/multimodal-live-api-web-console](https://github.com/google-gemini/multimodal-live-api-web-console)
