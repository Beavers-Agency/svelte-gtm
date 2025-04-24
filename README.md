# 🧩 svelte-gtm

**Lightweight Svelte components for easy integration with Google Tag Manager (GTM)** — including GTM script injection and SPA page view tracking out of the box.

---

## 🚀 Installation

```bash
yarn add --dev svelte-gtm
# or
npm install --save-dev svelte-gtm
```

## Usage
### ① Inject the GTM script
Use the GTMDataLayer component in your layout (e.g., +layout.svelte) and replace GTM-XXXXXXX by your ID:

```svelte
<script>
  import GTM from 'svelte-gtm/GTM.svelte';
</script>

<GTM gtmID="GTM-XXXXXXX" />
```
✅ This will inject the gtm.js script into <head> and the <noscript> iframe fallback into <body>.

### ② Track page views in SPA
Use the GTMDataLayer component in your layout (e.g., +layout.svelte):

```svelte
<script>
  import GTMDataLayer from 'svelte-gtm/GTMDataLayer.svelte';
</script>

<GTMDataLayer />
```
✅ It pushes a page view event to dataLayer on route changes.

## 📊 Events automatically pushed

Each page view triggers:
```json
{
  event: 'beavers_page_view',
  page_path: '/your/current/path',
  page_title: 'Document Title'
}
```
You can customize this component to match your own data structure.

## 🧪 Example
In your layout (e.g., +layout.svelte):
```svelte
<script>
  import GTM from 'svelte-gtm/GTM.svelte';
  import GTMDataLayer from 'svelte-gtm/GTMDataLayer.svelte';
</script>

<GTM gtmID="GTM-XXXXXXX" />
<GTMDataLayer />
```

## ✅ Compatibility
- Requires Svelte ^5.0.0
- No external dependencies
- Written in TypeScript, shipped as raw .svelte files

## 📄 License

MIT — Made with ❤️ by Beavers
