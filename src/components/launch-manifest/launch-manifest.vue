<template>
	<div class="manifest">
		<launch-manifest-header></launch-manifest-header>

		<ul>
			<launch-manifest-row
				v-bind:launchData="{ badgeUrl: 'Falcon', rocketName: 'Falcon', rocketType: 'Merlin A',  launchDate: '03/25/2005', details: 'Engine failure at 33 seconds and less of vehicle', id: 1 }"
			></launch-manifest-row>
			<launch-manifest-row
				v-bind:launchData="{ badgeUrl: 'Falcon', rocketName: 'Falcon', rocketType: 'Merlin A',  launchDate: '03/25/2005', details: 'Engine failure at 33 seconds and less of vehicle', id: 1 }"
			></launch-manifest-row>
			<launch-manifest-row
				v-bind:launchData="{ badgeUrl: 'Falcon', rocketName: 'Falcon', rocketType: 'Merlin A',  launchDate: '03/25/2005', details: 'Engine failure at 33 seconds and less of vehicle', id: 1 }"
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
	}
}
</script>

<style src="./launch-manifest-common.less" scoped lang="less"></style>
<style scoped lang="less">
	.manifest ul {
		padding: 0;
		margin: 0;
	}
</style>
