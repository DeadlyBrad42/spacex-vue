<template>
	<div class="toolbox">
		<div>
			<div v-on:click="reloadList()" class="refresh">
				<a>Refresh</a>
			</div>
		</div>

		<div class="checkbox">
			<input type="checkbox" id="landed" v-model="options.landed" />
			<label for="landed">Land success</label>
		</div>
		<div class="checkbox">
			<input type="checkbox" id="reused" v-model="options.reused" />
			<label for="reused">Reused</label>
		</div>
		<div class="checkbox">
			<input type="checkbox" id="reddit" v-model="options.attachment" />
			<label for="reddit">With Reddit</label>
		</div>


	</div>
</template>

<script>
module.exports = {
	props: {
		options: {
			validator: function (data) {
				return data.hasOwnProperty('landed')
					&& data.hasOwnProperty('reused')
					&& data.hasOwnProperty('attachment');
			}
		}
	},
	data: function () {
		return {
			landed: this.options.landed,
			reused: this.options.reused,
			attachment: this.options.attachment,
		};
	},
	methods: {
		reloadList() {
			this.$emit('reload-data');
		}
	},
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
			cursor: pointer;
		}

		.checkbox {
			text-transform: uppercase;
			margin: 0 0 0 1rem;

			// Hide standard checkbox input
			input[type="checkbox"] {
				display: none;
			}

			// Utilize label for styling custom checkbox
			input[type="checkbox"] + label {
				display: flex;
				align-items: center;
				cursor: pointer;

				&::before {
					border: 1px solid #FFFFFF;
					border-radius: 4px;
					content: '';
					display: inline-block;
					width: 1rem;
					height: 1rem;
					padding: 0.15rem;
					margin: 0.5rem;
				}
			}

			// Show checkmark
			input[type="checkbox"]:checked + label::before {
				background-image: url('../../assets/images/checkmark.svg');
				background-origin: content-box;
				background-size: 1rem 1rem;
				background-repeat: no-repeat;
			}
		}
	}
</style>
