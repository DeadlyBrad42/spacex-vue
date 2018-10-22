<template>
	<div class="checkbox">
		<input type="checkbox" v-model="checked" v-bind:id="id" />
		<label v-bind:for="id">
			<slot></slot>
		</label>
	</div>
</template>

<script>
module.exports = {
	props: {
		checked: {
			type: Boolean,
			required: true,
		},
		id: {
			type: String,
			required: true,
		}
	}
}
</script>

<style scoped lang="less">
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
</style>
