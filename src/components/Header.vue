<template>
	<header>
		<input type="text" name="todoInput" v-model="todoValue" placeholder="What's the plan, Batman?" />
		<button class="submit" v-on:click="createTodo">+</button>
	</header>
</template>

<script>
	export default {
		name: "Header",
		data: function () {
			return {
				todoValue: ""
			}
		},
		methods: {
			createTodo: function () {
				this.$emit('createTodo', this.todoValue);
				this.todoValue = "";
			}
		}
	}
</script>

<style lang="scss" scoped>
	header {
		display: flex;
		
		input {
			flex: 1;
			height: 50px;
			box-sizing: border-box;
			text-indent: 15px;

			font-size: 20px;
		}

		.submit {
			width: 50px;
			height: 50px;

			color: #171717;
			font-size: 28px;
			line-height: 1;
			font-weight: 700;

			background-color: #FFCE00;
			border: none;
			outline: none;

			cursor: pointer;

			&:hover {
				background-color: lighten($color: #FFCE00, $amount: 10);
			}
			&:active {
				background-color: darken($color: #FFCE00, $amount: 5);
			}
		}
	}
</style>


