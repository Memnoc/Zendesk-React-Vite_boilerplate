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
