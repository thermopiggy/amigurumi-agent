# Amigurumi Shop

This project provides a simple Node.js web application that showcases a catalogue of handmade amigurumi toys and allows visitors to add items to a cart and send an order via WhatsApp. The application is intentionally lightweight and contains no external dependencies, making it easy to deploy on free hosting services.

## Features

* **Home page** – A friendly hero section introduces your brand with a colourful banner and call‑to‑action button.
* **Product catalogue** – Items are grouped into three categories (animals, people and fantasy). Each product displays an image, name, description and price, and can be added to the shopping cart.
* **Shopping cart** – The cart page lists all selected items with quantities, line totals and a remove button. A WhatsApp button automatically composes a message summarising the order so it can be sent to you.
* **Multilingual support (BG/EN)** – All interface text, including product names and descriptions, can be displayed in Bulgarian or English. A language dropdown in the navigation bar lets visitors switch languages.
* **Responsive design** – Built with Bootstrap 5, the pages adapt gracefully to mobile, tablet and desktop screens.
* **JSON‑based data** – Product details are loaded from `data/products.json`, making it easy to extend or modify the catalogue.
* **No external dependencies** – The server uses Node.js’ built‑in `http` module. There is no need to install Express or any other packages.

## Local setup

1. **Install Node.js** – Make sure you have Node.js installed (version 14 or later is recommended).
2. **Clone or copy the repository** – Place the contents of this folder on your machine. All source files live in a single directory ready for GitHub deployment.
3. **Customise the WhatsApp number (optional)** – By default the order button sends messages to a placeholder number. Set an environment variable when starting the server to use your real number:

   ```bash
   WHATSAPP_NUMBER=359XXXXXXXXX node server.js
   ```

   The number must be in international format without the `+` sign.

4. **Run the server** – From within the `amigurumi-shop` directory run:

   ```bash
   node server.js
   ```

   The server will start on port 3000. Open your browser and navigate to `http://localhost:3000`.

5. **Edit your products (optional)** – Modify `data/products.json` to add, remove or edit products. Each entry should specify an `id`, `category`, `image`, `price`, `name` (with `bg` and `en` fields) and `description` (also with `bg` and `en` fields). Store your images in `public/images` and reference them in the `image` field.

6. **Deploy** – Because there are no additional dependencies, the project can be pushed to GitHub and deployed on platforms such as [Heroku](https://www.heroku.com/), [Render](https://render.com/), [Railway](https://railway.app/) or [Vercel](https://vercel.com/) using their Node.js build packs. Set the `PORT` environment variable if required by your hosting provider.

## Folder structure

```
amigurumi-shop/
├── data/
│   └── products.json      – product catalogue in JSON format
├── locales/
│   ├── bg.json            – Bulgarian UI strings
│   └── en.json            – English UI strings
├── public/
│   ├── css/
│   │   └── styles.css      – custom styles
│   └── images/
│       ├── pastel-yarn.png
│       ├── pink-yarn.png
│       ├── fantasy-yarn.png
│       └── hero-background.png
├── server.js              – minimal HTTP server with routing and session handling
└── README.md              – this file
```

Feel free to replace the placeholder images with real photos of your handmade toys. The generated yarn textures are there only as decorative stand‑ins.