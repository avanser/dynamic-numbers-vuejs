# Getting Started with AVANSER Dynamic Numbers Vue.JS

This repository holds a simple Vue.JS App built to provide guidelines and examples on how AVANSER's Dynamic Numbers can help you provide online call tracking in your Reactive Applications.

## Licence

Refer to our [licence](LICENSE.md)

## Getting started

This example has been built using `npm init vue@latest .` command.\
For any details on how Vue.JS works please refer to the project documentation.\
You can learn more following the links below:

- [VSCode](https://code.visualstudio.com/)
- [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur)
- [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).
- [Vite Configuration Reference](https://vitejs.dev/config/)
- [Official Vue.JS Documentation](https://vuejs.org/guide/introduction.html)

In order to use this test you need to:

- Configure Dynamic Numbers in the AVANSER Customer Portal
- Copy cnf.json.sample to cnf.json
- Edit cnf.json with appropriate values. Contact our support team if information is required on:
  - What host to use
  - What your clientId is
  - What the trackingCode associated with your configuration is

## Using this project

After configuring `cnf.json` ensure Node dependencies are installed using npm or yarn.

```bash
cd dynamic-numbers-vuejs
npm i
```

In the project directory, you can run:

### `npm run dev`

This will start the app in the development mode.\
Open [http://localhost:5173](http://localhost:5173) to view it in your browser.

The page will reload when you make changes.\
Any lint errors can be viewed in the console.

### Deployment

This code base is intended as an example and should not be, ***under any circumstances***, used in a production environment.

## AVANSER Dynamic Numbers

Check out our [Knowledge Base](https://avanser.zohodesk.com/portal/en/kb/support/client-portal-4/settings/call-trackingP)!

- [Dynamic Number Insertion](https://avanser.zohodesk.com/portal/en/kb/articles/dynamic-numbers-insertion)
- [Troubleshooting (Basic)](https://avanser.zohodesk.com/portal/en/kb/articles/dynamic-number-insertion-troubleshooting-basic)
- [Troubleshooting (Advanced)](https://avanser.zohodesk.com/portal/en/kb/articles/dynamic-number-insertion-troubleshooting-advanced)
- [Testing your website](https://avanser.zohodesk.com/portal/en/kb/articles/dynamic-numbers-testing-your-website)
