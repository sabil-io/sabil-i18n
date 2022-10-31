# sabil-i18n

This is the official internationalization repository for [Sabil](https://sabil.io).

## Supported languages:

- English (default)
- Arabic (ar)
- Turkish (tr)

## Usage

1. Download the language of your choice from the list of languages in this repo.
2. Import the language and pass it as the `language` parameter to the `attach` function in the [`sabil-js`](https://www.npmjs.com/package/sabil-js) library.
3. If you need RTL, set `rtl` to true in the `attach` parameters.

#### Example

Here's an example for localizing to Arabic:

```js
import arabic from "./ar.js";

await Sabil.attach({
  client_id: `clientId.value`,
  user: `user.value`,
  language: arabic,
  rtl: true,
});
```

## Adding a supported language

We welcome any new language support for the Sabil community. To add a new language, please create a PR with a single js file that exports a default object with the following keys:

```js
export default {
  limit_exceeded_title: "",
  limit_exceeded_subtitle: "",
  current: "",
  os: "",
  last_active: "",
  actions: "",
  logout: "",
  status: "",
  attached: "",
};
```

### Pluralization

It's important to get pluralization correct. Sabil libraries support pluralization automatically. Please ensure you enter any pluralization in the following format:

- "text {n} for single | text {n} for two | text {n} for many"
- You can add as many separators `|` as needed for proper pluralization
- **Important** there must be a space before and after the `|` character
