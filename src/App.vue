<template>
	<div id="app" class="page-wrapper">
		<div class="content">
			<h1>SpaceX Launches</h1>

			<div class="launches">
				<toolbox>
				</toolbox>

				<launch-manifest>
				</launch-manifest>
			</div>

		</div>
	</div>
</template>

<script>
import toolbox from './components/toolbox/toolbox.vue';
import launchManifest from './components/launch-manifest/launch-manifest.vue';

export default {
	name: 'App',
	components: {
		launchManifest,
		toolbox,
	}
}
</script>

<style lang="less">
	@font-face {
		font-family: 'Geomanist';
		src: url('assets/fonts/geomanist-regular-webfont.eot');
		src: url('assets/fonts/geomanist-regular-webfont.eot') format('embedded-opentype'),
		     url('assets/fonts/geomanist-regular-webfont.woff2') format('woff2'),
		     url('assets/fonts/geomanist-regular-webfont.woff') format('woff'),
		     url('assets/fonts/geomanist-regular-webfont.ttf') format('truetype'),
		     url('assets/fonts/geomanist-regular-webfont.svg') format('svg');
	}

	body {
		font-family: 'Geomanist', 'Arial', 'Calibri', sans-serif;
		background-image: url('assets/images/background.jpg');
		background-size: cover;
	}

	.content {
		width: 960px;
		margin: 0 auto;
	}

	.content > h1 {
		text-align: center;
		color: #EFEFEF;
		font-size: 3rem;
		font-weight: normal;
		text-shadow: 2px 2px 4px black;
	}
</style>
