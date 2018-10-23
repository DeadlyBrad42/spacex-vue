<template>
	<li>
		<span class="cell-data">
			<img v-bind:src="launchData.badgeUrl" />
		</span>
		<span class="cell-label">{{ launchData.rocketName }}</span>
		<span class="cell-label">{{ launchData.rocketType }}</span>
		<span class="cell-label">{{ launchData.date }}</span>
		<span class="cell-desc">{{ launchData.details }}</span>
		<span class="cell-data">{{ launchData.id }}</span>
		<span class="cell-data">
			<a v-if="launchData.article" @click="openLink(launchData.article)">Open Link</a>
		</span>
	</li>
</template>

<script>
module.exports = {
	props: {
		launchData: {
			validator: function (data) {
				return data.badgeUrl
					&& data.rocketName
					&& data.rocketType
					&& data.date
					&& data.id;
			}
		}
	},
	methods: {
		openLink: function(href) {
			window.open(href, '_blank');
		},
	},
}
</script>

<style src="./launch-manifest-common.less" scoped lang="less"></style>
<style scoped lang="less">
	li {
		display: flex;
		justify-content: space-between;
		align-items: center;
		color: #444444;
		background-color: rgba(255, 255, 255, 0.85);
		padding: 0.25rem 0;
		margin: 0.5rem 0;
		border: 1px solid #FFFFFF;
		border-radius: 0.5rem 0.5rem;

		.cell-data {
			img {
				max-width: 85px;
				padding: 0.65rem;
				box-sizing: border-box;
			}

			a {
				color: #13A2E8;
				display: inline-block;
				width: 2rem;
				height: 2rem;
				background-image: url('../../assets/images/link.svg');
				background-size: 2rem 2rem;
				background-repeat: no-repeat;
				text-indent: 100%;
				white-space: nowrap;
				overflow: hidden;
				cursor: pointer;
			}
		}
	}
</style>
