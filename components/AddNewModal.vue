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
					<option v-for="(priority, index) in priorityTypes" :key="index" :value="priorityType">{{ priority.value }}</option>
				</select>
			</div>
			<div class="btnWrapper">
				<button>更新</button>
			</div>
		</div>
	</div>
</template>

<script>
import { priorityTypes } from '../plugins/utils.js'
export default {
	data() {
		return {
			priorityTypes: priorityTypes,
		}
	},
	methods: {
		closeModal() {
			this.$emit('closeModal');
		}
	}
}
</script>

<style>

</style>