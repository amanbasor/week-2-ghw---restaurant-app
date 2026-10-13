Local Menu Translator

An offline-first, privacy-focused web application designed to translate physical and digital restaurant menus using vision-capable Large Language Models (LLMs) hosted locally via LM Studio.

Built as a lightweight, single-file client-side application, it processes menu images or raw text and generates structured JSON translations complete with dish names, appetizing descriptions, and exact price extractions.

Key Features

Vision & Multimodal Translation: Snap or upload a photo of a physical menu or paste raw menu text for instant translation.

100% Local & Private: Powered by your locally running LLMs (such as Google Gemma Vision models) via LM Studio. No media or API keys leave your machine.

Responsive App-Style UI: Mobile-first, single-page UI built with modern CSS variables, fluid glassmorphic cards, responsive touch gestures, and light/dark theme accents.

Printable & Exportable: Formats output into structured, categorized menu cards with one-click clipboard copying and clean print-optimized layout styling (@media print).

Multilingual Support: Seamlessly translates into English, Hindi, Spanish, French, German, Italian, Japanese, Korean, Chinese, Arabic, and more.

Zero Build Setup: Pure Vanilla JavaScript, HTML5, and CSS. No node_modules, build tools, or bundlers required.

Architecture & Tech Stack

Frontend: HTML5, CSS3 (Flexbox/Grid, Custom Properties, Media Queries), Vanilla JavaScript (ES6+)

Typography & Icons: Google Fonts (Poppins), Material Symbols Outlined

Local Inference Engine: LM Studio (OpenAI-compatible local server endpoint at http://localhost:1234/v1)

Client-side Processing: HTML5 createImageBitmap and Canvas API for image scaling and quality optimization before local model ingestion.

Prerequisites

Before running the app, ensure you have:

LM Studio installed on your desktop.

A vision-capable model loaded in LM Studio (e.g., Gemma 2, Llama 3.2 Vision, or similar multimodal models).

LM Studio's Local Inference Server running with CORS enabled (http://localhost:1234).

Quick Start

Clone the Repository:

git clone https://github.com/amanbasor/restaurant-app.git
cd restaurant-app


Launch Google Studio Server:

Open LM Studio and download a vision-capable model.

Go to the Local Server tab (<->).

Select your loaded model.(Gemma)

Enable Cross-Origin Resource Sharing (CORS) in server settings.

Click Start Server (default port: 1234).

Run the Application:

Open menu_app.html directly in any web browser (Chrome, Safari, Firefox, Edge).

Or serve it using a simple HTTP server:

python3 -m http.server 8000


Open http://localhost:8000/menu_app.html in your browser.

Usage Guide

Get Started: Click the arrow button on the splash screen to enter the app.

Select Language: Choose your target translation language from the top bar dropdown.

Input Menu Data:

Photo Tab: Click or drag-and-drop an image of a menu. The app automatically scales the image client-side to ensure optimal model performance.

Text Tab: Paste plain text extracted from a digital menu.

Translate: Click Translate. The client sends an OpenAI-compatible JSON payload to your local LM Studio instance and renders the structured output into categorized dish cards.

Export & Print:

Click the Copy icon in the header to save plain text translations to your clipboard.

Click the Print icon in the bottom navigation bar for a clean, print-ready document view.

Authentication & API Key Settings

If your local LM Studio instance or reverse proxy requires an API key:

Tap the menu icon in the top bar or swipe right from the left edge on touch devices.

Enter your API key into the slide-out input field. The key will be stored securely in your browser's local storage.

Layout & CSS Highlights

Single-File Component Architecture: Contains UI components, state management, API abstraction, and layout code within one self-contained file.

Auto Image Shrinking: Implements a client-side utility (shrink()) using createImageBitmap and HTML5  to downscale high-resolution photos to 1400px max dimensions at 85% JPEG quality before transmitting to the local model.

Print Stylesheets: @media print rules automatically hide headers, control bars, and background framing, providing clean output suitable for physical printing.

Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request if you want to add new feature enhancements, UI refinements, or prompt optimizations.

Fork the project

Create your feature branch (git checkout -b feature/AmazingFeature)

Commit your changes (git commit -m 'Add some AmazingFeature')

Push to the branch (git push origin feature/AmazingFeature)

Open a Pull Request

License

Distributed under the MIT License. See LICENSE for more information.
