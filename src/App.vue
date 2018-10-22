<template>
	<div id="app" class="page-wrapper">
		<div class="content">
			<h1>SpaceX Launches</h1>

			<div class="launches">
				<toolbox>
				</toolbox>

				<launch-manifest
					v-bind:launches="filteredLaunches"
				></launch-manifest>
			</div>

		</div>
	</div>
</template>

<script>
import toolbox from './components/toolbox/toolbox.vue';
import launchManifest from './components/launch-manifest/launch-manifest.vue';

export default {
	components: {
		launchManifest,
		toolbox,
	},
	data: function() {
		return {
			launchApi: 'https://api.spacexdata.com/v2/launches',
			filterOptions: {
				landed: true,
				reused: false,
				attachment: false,
			},
			launches: [],
		};
	},
	created: function() {
		this.loadData();
	},
	methods: {
		loadData: function() {
			fetch(this.launchApi).then(response => {
				response.json().then(json => {
					this.launches = json;
				});
			});
		}
	},
	computed: {
		filteredLaunches: function () {
			let filteredLaunches = new Array();

			for (const launch of this.launches) {
				// Sortable options
				let landedSucessfully = launch.launch_success;
				let wasReused = launch.reuse.capsule
						|| launch.reuse.core
						|| launch.reuse.fairings
						|| launch.reuse.side_core1
						|| launch.reuse.side_core2;
				let isReddit = false;

				let launchDate = new Date(launch.launch_date_utc);

				if (
					(!this.filterOptions.landed || (this.filterOptions.landed && landedSucessfully))
					&& (!this.filterOptions.reused || (this.filterOptions.reused && wasReused))
					&& (!this.filterOptions.attachment || (this.filterOptions.attachment && isReddit))
				) {
					filteredLaunches.push({
						badgeUrl: launch.links.mission_patch_small || '../../assets/images/placeholder.png',
						rocketName: launch.rocket.rocket_name,
						rocketType: launch.rocket.rocket_type,
						date: `${launchDate.getMonth()}/${launchDate.getDate()}/${launchDate.getFullYear()}`,
						details: launch.details,
						id: launch.flight_number,

						landedSucessfully: landedSucessfully,
						wasReused: wasReused
					});
				}
			}

			return filteredLaunches;
		}
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
