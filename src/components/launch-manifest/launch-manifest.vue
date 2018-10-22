<template>
	<div class="manifest">
		<launch-manifest-header></launch-manifest-header>
		<ul>
			<launch-manifest-row
				v-for="launch in launches"
				v-bind:key="launch.id"
				v-bind:launchData="launch"
			></launch-manifest-row>
		</ul>
	</div>
</template>

<script>
import launchManifestHeader from './launch-manifest-header.vue';
import launchManifestRow from './launch-manifest-row.vue';

export default {
	components: {
		launchManifestHeader,
		launchManifestRow,
	},
	props: {
		launches: Array
	},
}
</script>

<style src="./launch-manifest-common.less" scoped lang="less"></style>
<style scoped lang="less">
	.manifest ul {
		padding: 0;
		margin: 0;
	}
</style>
