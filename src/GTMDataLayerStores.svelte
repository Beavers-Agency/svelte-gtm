<script lang="ts">
	import { navigating, page } from '$app/stores';

	let lastPageViewPath = '';

	$effect(() => {
		const currentPath = page.url.pathname + page.url.search;

		if (!navigating.to && currentPath !== lastPageViewPath) {
			lastPageViewPath = currentPath;

			window.dataLayer = window.dataLayer || [];
			window.dataLayer.push({
				event: 'beavers_page_view',
				page_path: currentPath,
				page_title: document.title
			});
		}
	});
</script>
