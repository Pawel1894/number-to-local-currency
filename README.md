# Format number to local currency

Single function  that allows a number to be formatted to a currency with the sign of the user's local currency.

### Installing

using npm:

```bash
$ npm install number-to-local-currency
```

using pnpm:

```bash
$ pnpm install number-to-local-currency
```

using CDN:

```html
<script src="https://www.unpkg.com/number-to-local-currency@0.0.1/dist/index.js"></script>
```

If you are not using CDN, you can import the library using `import` or `require` approach:

```js
import { format } from "number-to-local-currency";
```

or

```js
const format = require("number-to-local-currency");
```

## Examples

Simple usage:

```js
format(993.43); // when user is in USA - formatting number to US currency with US formatting  output: $ 999.43
format(993.43); // when user is in Poland - formatting number to Polish currency with US formatting  output: PLN 999.43
```

When changing default formatting type, all format types must be compatible with JavaScript's Intl:

```js
format(993.43, "fr"); // formatting number to polish currency with french formatting  output: 993,43 PLN
```

## How it works

1. Get user's timezone using moment-timezone guess function
2. Get user's country code using countries-and-timezones
3. Format number with JavaScript native Intl object
4. Returns formatted number

## Function params

- `value` – Number you want to format
- `numberFormat` – Select format type compatible with JavaScript Intl - default value is en-US
- `fallbackCountryCurrency` – In case something goes wrong and JavaScript isn't able to identify the user's country, you can set fallback country - default is US

## Credits

This function works using the following three libraries: [moment-timezone](https://www.npmjs.com/package/moment-timezone) & [country-to-currency](https://www.npmjs.com/package/country-to-currency) & [countries-and-timezones](https://www.npmjs.com/package/countries-and-timezones)

## License

MIT
