<template>
	<li>
		<span class="cell-data">
			<img src="../../assets/images/placeholder.png" />
		</span>
		<span class="cell-label">{{ launchData.rocketName }}</span>
		<span class="cell-label">{{ launchData.rocketType }}</span>
		<span class="cell-label">{{ launchData.launchDate }}</span>
		<span class="cell-desc">{{ launchData.details }}</span>
		<span class="cell-data">{{ launchData.id }}</span>
		<span class="cell-data">
			<a href="#">Open Link</a>
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
					&& data.launchDate
					&& data.details
					&& data.id;
			}
		}
	}
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
		/* padding: 1rem; */
		margin: 0.5rem 0;
		border: 1px solid #FFFFFF;
		border-radius: 0.5rem 0.5rem;

		.cell-data {
			img {
				max-width: 85px;
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
			}
		}
	}
</style>
