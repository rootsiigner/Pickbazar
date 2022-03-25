1. remove the following code from \_document.tsx:

```
if (process.env.NODE_ENV !== 'production') {
      i18n?.reloadResources(locale);
    }
```

on favour of: reloadOnPrerender = true

2. move RTL_LANGUAGES to the constants file
3. replace AppProviders with QueryProvider at \_app.tsx
4. use alias `@/*` for all our local imports to avoid `node_modules` conflicts
5. use `import type` for all our type imports.

//FIXME:

1. Logout redirection from authorized routes
2. Address Form Type Selection Issue
3. Remove Selected Address if new User is Logged In (from LocalStorage)
4. Remove Address Delete from Checkout Page and move it to Profile Page
5. Accounts pages design should improve at least a container with
6. We need to make a Paper component for the Checkout and Profile Page

//FIXME:

1.             "axios": "^0.25.0",
2.  "framer-motion": "6.2.3",
3.  "little-state-machine": "^4.2.1",
4.  "next": "12.0.10",
5.             "rc-pagination": "^3.1.14",
6.  "react-query": "^3.34.15",
7.  "swiper": "^7.4.1",
8.  "eslint-config-next": "12.0.10",
9.  "next-sitemap": "^2.1.14",

```
{
  "name": "@pick-bazar/shop",
  "version": "4.4.1",
  "private": true,
  "scripts": {
    "clean": "rimraf \"{.next,node_modules,__generated__,.cache,src/framework/graphql/**/*.d.ts}\"",
    "dev:rest": "next dev -p 3003",
    "build:rest": "next build",
    "codegen": "node -r dotenv/config $(yarn bin)/graphql-let",
    "dev:gql": "yarn codegen && next dev -p 3001",
    "build:gql": "yarn codegen && next build",
    "start": "next start",
    "lint": "next lint",
    "postbuild:rest": "next-sitemap",
    "prepare": "husky install"
  },
  "dependencies": {
    "@apollo/client": "^3.5.8",
    "@headlessui/react": "^1.4.3",
    "@hookform/resolvers": "^2.8.8",
    "@reach/portal": "^0.16.2",
    "@stripe/react-stripe-js": "^1.7.0",
    "@stripe/stripe-js": "^1.22.0",
    "apollo-upload-client": "^17.0.0",
    "axios": "^0.25.0",
    "body-scroll-lock": "^4.0.0-beta.0",
    "camelcase-keys": "^7.0.2",
    "classnames": "^2.3.1",
    "dayjs": "^1.10.7",
    "deepmerge": "^4.2.2",
    "framer-motion": "6.2.3",
    "jotai": "^1.6.0",
    "js-cookie": "^3.0.1",
    "little-state-machine": "^4.2.1",
    "lodash": "^4.17.21",
    "next": "12.0.10",
    "next-auth": "^4.2.1",
    "next-i18next": "^10.2.0",
    "next-pwa": "^5.4.4",
    "next-seo": "^5.1.0",
    "overlayscrollbars": "^1.13.1",
    "overlayscrollbars-react": "^0.2.3",
    "rc-collapse": "^3.1.2",
    "rc-rate": "^2.9.1",
    "rc-slider": "^9.7.5",
    "rc-table": "^7.22.2",
    "react": "17.0.2",
    "react-content-loader": "^6.1.0",
    "react-copy-to-clipboard": "^5.0.4",
    "react-device-detect": "^2.1.2",
    "react-dom": "17.0.2",
    "react-dropzone": "^12.0.3",
    "react-hook-form": "^7.27.0",
    "react-otp-input": "^2.4.0",
    "react-phone-input-2": "^2.15.0",
    "react-query": "^3.34.15",
    "react-scroll": "^1.8.4",
    "react-select": "^5.2.2",
    "react-sticky-box": "^0.9.3",
    "react-toastify": "^8.1.1",
    "react-use": "^17.3.2",
    "react-waypoint": "^10.1.0",
    "sharp": "^0.30.1",
    "swiper": "^7.4.1",
    "tiny-invariant": "^1.2.0",
    "yup": "^0.32.11"
  },
  "devDependencies": {
    "@graphql-codegen/cli": "^2.6.1",
    "@graphql-codegen/import-types-preset": "^2.1.10",
    "@graphql-codegen/typescript": "^2.4.3",
    "@graphql-codegen/typescript-operations": "^2.3.0",
    "@graphql-codegen/typescript-react-apollo": "^3.2.5",
    "@graphql-codegen/typescript-resolvers": "^2.5.0",
    "@tailwindcss/forms": "^0.4.0",
    "@tailwindcss/typography": "^0.5.1",
    "@types/apollo-upload-client": "^17.0.0",
    "@types/body-scroll-lock": "^3.1.0",
    "@types/html-entities": "^1.3.4",
    "@types/js-cookie": "^3.0.1",
    "@types/lodash": "^4.14.178",
    "@types/overlayscrollbars": "^1.12.1",
    "@types/react": "17.0.39",
    "@types/react-copy-to-clipboard": "^5.0.2",
    "@types/react-mailchimp-subscribe": "^2.1.1",
    "@types/react-scroll": "^1.8.3",
    "@types/react-select": "^5.0.1",
    "autoprefixer": "^10.4.2",
    "eslint": "8.9.0",
    "eslint-config-next": "12.0.10",
    "eslint-config-prettier": "^8.3.0",
    "graphql": "^16.3.0",
    "graphql-let": "^0.18.6",
    "husky": ">=6",
    "lint-staged": ">=12.3.3",
    "next-sitemap": "^2.1.14",
    "postcss": "^8.4.6",
    "prettier": "^2.5.1",
    "prettier-plugin-tailwindcss": "^0.1.7",
    "rimraf": "^3.0.2",
    "tailwindcss": "^3.0.22",
    "typescript": "4.5.5",
    "yaml-loader": "^0.6.0"
  },
  "engines": {
    "node": ">=12.20.0"
  }
}

```