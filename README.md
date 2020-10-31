# Bulma + CSS Variables

Don't run `npm build` as that will override the current `css/bulma.css` file, which has been crafted by hand to overcome the following limitations:

PurgeCSS and therefore [rollup-plugin-vue3-ui-css-purge](https://www.npmjs.com/package/@pathscale/rollup-plugin-vue3-ui-css-purge) will do a bad job while purging unused css variables if the css do not comply with the following:

- Every css variable that depends on other variables will have be to be declared after their dependants
- Whenever commas are used to separate selectors, if one of those selectors it's body, it must go last