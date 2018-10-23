<template>
	<div class="header">
		<span class="cell-data">Badge</span>
		<span class="cell-label">Rocket Name</span>
		<span class="cell-label">Rocket Type</span>
		<span class="cell-label">Launch Date</span>
		<span class="cell-desc">Details</span>
		<span class="cell-data">ID</span>
		<span class="cell-data">Article</span>
	</div>
</template>

<style src="./launch-manifest-common.less" scoped lang="less"></style>
<style scoped lang="less">
	.header {
		display: flex;
		justify-content: space-between;
		color: #043D67;
		font-weight: bold;
		background-image: linear-gradient(#A1BACF, #FFFFFF);
		padding: 1rem 0;
	}
</style>
