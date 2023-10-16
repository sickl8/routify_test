<script lang="ts" context="module">
    import { InternalReflector, Router, createRouter } from '@roxi/routify';
    import routes from '../.routify/routes.default.js';
    import './app.css';

	export const router = createRouter({ routes });
	const urlRewrite = {
		toInternal: (url: string) => {
			console.log({url})
			return `#${url}`;
		},
		toExternal: (url: string) => {
			console.log({url})
			return url.replace(/^.*#/, "");
		}
	}
</script>

<Router {router} {urlRewrite} urlReflector={InternalReflector}/>
