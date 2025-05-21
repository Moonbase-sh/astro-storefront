# Astro Storefront

This is a simple Astro project to showcase how easily the Moonbase embedded storefront is added to Astro websites.

The main change is done in [./src/layouts/Layout.astro](./src/layouts/Layout.astro), where we've added the Moonbase script as an inline script:

```html
<script is:inline type="module" src="https://assets.moonbase.sh/storefront/moonbase.js"></script>
<script is:inline type="text/javascript">
    document.addEventListener('DOMContentLoaded', () => {
        // TODO: Replace this with the URL of your Moonbase account
        Moonbase.setup('https://demo.moonbase.sh')
    })
</script>
```

Be sure to add the `is:inline` to avoid processing these scripts.

Then, to add interactivity, we've added buttons and pricing information as render attributes on certain elements.

Read more about the Moonbase embedded storefront on https://moonbase.sh/docs/storefronts/embedded.
