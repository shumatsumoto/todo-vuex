<template>
	<div @click.self="closeModal" class="addNewArea">
		<div class="inputArea">
			<div>
				<label for="titleInput">タイトル</label>
				<input type="text" id="titleInput">
			</div>
			<div>
				<label for="priorityType">優先度</label>
				<select id="priorityType">
					<option value="">低</option>
					<option value="">中</option>
					<option value="">高</option>
				</select>
			</div>
			<div class="btnWrapper">
				<button>更新</button>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	methods: {
		closeModal() {
			this.$emit('closeModal');
		}
	}
}
</script>

<style>

</style>