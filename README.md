# Astro Storefront

This is a simple Astro project to showcase how easily the Moonbase embedded storefront is added to Astro websites.

The main change is done in [./src/layouts/Layout.astro](./src/layouts/Layout.astro), where we've added the Moonbase script as an inline script.
Be sure to add the `is:inline` to avoid Astro processing these scripts, they should always be run fully client-side.
If using a `ClientRouter`, it's important to change the event listener to `astro:page-load` attribute to run the setup on each page load, not just the inital one.

```html
<script is:inline type="module" src="https://assets.moonbase.sh/storefront/moonbase.js"></script>
<script is:inline type="text/javascript">
    document.addEventListener('astro:page-load', () => {
        // TODO: Replace this with the URL of your Moonbase account
        Moonbase.setup('https://demo.moonbase.sh')
    })
</script>
```

Then, to add interactivity, we've added buttons and pricing information as render attributes on certain elements.

Read more about the Moonbase embedded storefront on https://moonbase.sh/docs/storefronts/embedded.
