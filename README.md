# Social Media Client

**Forked:** [NoroffFEU Project](https://github.com/NoroffFEU/social-media-client)  
**GitHub:** [Repo](https://github.com/siljeangelvik/social-media-client-angelvik/tree/workflow)  
**Course Assignment:** [Workflow](https://noroff-content.gitlab.io/feu/workflow/ca.html)  
**GitHub Pages:** [Live Domain](https://siljeangelvik.github.io/social-media-client-angelvik/)

![Deploy to pages](https://github.com/siljeangelvik/social-media-client-angelvik/actions/workflows/pages.yml/badge.svg)  
[![Netlify Status](https://api.netlify.com/api/v1/badges/8351bb72-cb2f-4acd-9641-31a9d3ca7da8/deploy-status)](https://app.netlify.com/sites/social-media-client-ca-angelvik/deploys)

---

## Challenges

### Vite

Feedback when running commands:  
`npm run dev`  
`npm run build`

![build-vite.png](./issues/img/build-vite.png)

#### Trying to fix issue:

**SOLVED:** removed `"type": "module"` from package.json.  
`npm run build` = successful

![remove-module-from-packageJSON.png](./issues/img/remove-module-from-packageJSON.png)

Additional Feedback:  
script src=./node_modules/bootstrap/dist/js/bootstrap.bundle.min.js  
in index cannot be bundled without type=module attribute

script src=./src/js/index.js  
in index cannot be bundled without type=module attribute

**SOLVED:** adding type=module to script-link in html.

### Cypress

![running-cypress.png](./issues/img/running-cypress.png)

#### Trying to fix issue:

Installing npm package:  
[cypress-localstorage-commands](https://www.npmjs.com/package/cypress-localstorage-commands)

#### Running Cypress again:

#### Cypress works, but throwing errors:

**400:** api/v1/social/auth/login  
**404:** src/js/storage/index  
**404:** dist/css/index.css

![after-install-cypress-localstorage-commands.png](./issues/img/after-install-cypress-localstorage-commands.png)

#### Running Cypress again:

#### Trying to fix issue:

**400:** api/v1/social/auth/login  
**404:** src/js/storage/index  
~~**404:** dist/css/index.css~~ **SOLVED**

`npm run cypress `![cypress-400-notFound.png](./issues/img/cypress-400-notFound.png)

at login (webpack:///./src/js/api/auth/login.js:20:8)
at async Context.eval (webpack:///./cypress/support/commands.js:4:2)

### Scripts

`npm run deploy`  
./dist/css/index.css doesn't exist at build time, it will remain unchanged to be resolved at runtime

![struggle-with-localstorage.png](./issues/img/struggle-with-localstorage.png)

### GitHub Actions

deprecated npm packages:  
[source-map-url](https://github.com/lydell/source-map-url#deprecated)

![deprecated-packages](./issues/img/deprecated-packages.png)

---

## Issues:

2 out of 3 cypress tests pass.

---

## Resources:

- [Workflow Status Badges](https://docs.github.com/en/actions/monitoring-and-troubleshooting-workflows/adding-a-workflow-status-badge)
- [Cypress Docs](https://docs.cypress.io/guides/overview/why-cypress)
- [Prettier Pre-Commit Hook](https://prettier.io/docs/en/precommit.html)
- [npm commands](https://docs.npmjs.com/cli/v7/commands)
- [ESLint JavaScript](https://eslint.org/docs/latest/developer-guide/working-with-rules)
- [Simple SASS Compiler Setup](https://sprucecss.com/blog/the-simplest-sass-compile-setup)
- [Vite Docs Guide](https://vitejs.dev/guide/)
- [Git Docs WebHook](https://docs.github.com/en/get-started/customizing-your-github-workflow/exploring-integrations/about-webhooks)
- [Asbjørn GitHub Repo](https://github.com/Thundeee/social-media-client/tree/workflow)
- [Cypress Login Tests](https://www.dolthub.com/blog/2020-10-23-cypress-login-tests/)

### Tools

**Bundler:** Vite
**Formatter:** Prettier  
**Linting:** ESLint  
**Unit Tester:** Jest / Cypress  
**E2E Tester:** Cypress
