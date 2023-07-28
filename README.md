# Zendesk React + Vite

## Zendesk

This set up provide a starter point using the [Zendesk CLI](https://developer.zendesk.com/documentation/apps/getting-started/using-zcli/#app-configuration-file) as command-line tool, ditching the old ZAT.

In one terminal, cd into the `zendesk/` directory use `zcli app:server` to start the server.

In another terminal, start the server using `npm run dev`. This will start the Vite project on the port you have determined in `assets/iframe.html`

**The deafult for this template are**

```html
<script src="http://localhost:5000/@vite/client"></script>
<script src="http://localhost:5000/src/main.js"></script>
```

## Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## React

The React part of the app is found in `src/` and this is where the frontend is served.

# Building process

Because we have Vite with React and Zendesk CLI, we have effectively two distincts bundles to build out.

**Step 1**

From the root directory of the template, run
`npm run build`
This will create a dist folder with the following structure:

```
dist/
├── assets/
│   ├── index.hash.css  # Hashed CSS file
│   └── index.hash.js   # Hashed JS file
└── index.html          # HTML file
```

**Step 2**

Copy everything from the `assets/` folder to the `/assets` folder of the `/zendesk` directory.
Optional, but I would rename the `.css` and the `.js` files to something less hashy.

**Step 3**

In your `iframe.html`, make sure the path to the bundles resources are looking long the line of:

``html

<link rel="stylesheet" href="assets/style.css" />
<script src="assets/bundled-js.js"></script>

``
**Step 4**

In your `manifest.json` make sure the `ticket_sidebar` property in `location` points to `assets/iframe.html`

**Step 5**

Time to build the app with the assets included.
Navigate to the `zendesk/` and run `zcli apps:create`

If you have logged in and set up your environment correctly, the app is installed in your account and visible without running `?zcli_apps=true`
