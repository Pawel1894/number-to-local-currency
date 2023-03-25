<h1 align="center">
        Format number to local currency
</h1>

<p align="center">Single function enabling you to format number to currency with user's local currency sign.</p>

### Installing

using npm:

```bash
$ npm install axios
```

using pnpm:

```bash
$ pnpm install axios
```

using CDN

```html
<script src="https://www.unpkg.com/number-to-local-currency@0.0.1/dist/index.js"></script>
```

If you are not using CDN, you can import the library using `import` or `require` approach:

```js
import { format } from "number-to-local-currency";
```

or

```js
const format = require("number-to-local-currency")
```

## Examples

Simple usage

```js
  format(993.43) // when user is in USA - formatting number to US currency with US formatting  output: $ 999.43
  format(993.43) // when user is in Poland - formatting number to Polish currency with US formatting  output: PLN 999.43
```

When changing default formatting type, all formats type must be compatible with javascript's Intl

```js
  format(993.43, "fr") // formatting number to polish currency with french formatting  output: 993,43 PLN  
```

## How it works

1. Get user's timezone using moment-timezone guess function
2. Get user's country code using countries-and-timezones
3. Format number with javascript native Intl object
4. Returns formatted number

## Function params

- ```value``` - Number you want to format
- ```numberFormat``` - Select format type compatible with javascript Intl - default value is en-US
- ```fallbackCountryCurrency``` - In case something goes wrong and javascript isn't able to identify the user's country, you can set fallback country - default is US

## Credits 

This function work using the following three libraries: [moment-timezone](https://www.npmjs.com/package/moment-timezone) & [country-to-currency](https://www.npmjs.com/package/country-to-currency) & [countries-and-timezones](https://www.npmjs.com/package/countries-and-timezones)

## License

[MIT](LICENSE)
