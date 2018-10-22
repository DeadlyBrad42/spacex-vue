<template>
	<div class="toolbox">
		<div>
			<div class="refresh">
				<a href="#">Refresh</a>
			</div>
		</div>

		<app-checkbox id="landed" :checked="false">
			Land Success
		</app-checkbox>

		<app-checkbox id="reused" :checked="false">
			Reused
		</app-checkbox>

		<app-checkbox id="attachment" :checked="false">
			With Reddit
		</app-checkbox>
	</div>
</template>

<script>
module.exports = {
}
</script>

<style scoped lang="less">
	.toolbox {
		display: flex;
		align-items: center;
		color: #FFFFFF;
		background-color: rgba(255, 255, 255, 0.15);
		padding: 1rem;
		border: 1px solid #FFFFFF;
		border-radius: 0.5rem 0.5rem 0 0;

		& > div {
			margin-left: 0.5rem;

			&:first-child {
				flex-grow: 2;
				margin-left: 0;
			}
		}

		.refresh {
			color: #FFFFFF;
			display: inline-block;
			width: 1.5rem;
			height: 1.5rem;
			background-image: url('../../assets/images/refresh.svg');
			background-origin: content-box;
			background-size: 1.5rem 1.5rem;
			background-repeat: no-repeat;
			padding: 0.125rem;
			border: 1px solid #FFFFFF;
			border-radius: 50%;
			text-indent: 100%;
			white-space: nowrap;
			overflow: hidden;
		}
	}
</style>
