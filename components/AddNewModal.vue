<template>
	<div @click.self="closeModal" class="addNewArea">
		<div class="inputArea">
			<div>
				<label for="titleInput">タイトル</label>
				<input v-model="title" type="text" id="titleInput">
			</div>
			<div>
				<label for="priorityType">優先度</label>
				<select v-model="priority" id="priorityType">
					<option v-for="(priority, index) in priorityTypes" :key="index" :value="priority.priorityType">{{ priority.value }}</option>
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
import { mapGetters } from 'vuex'
export default {
	data() {
		return {
			priorityTypes: priorityTypes,
			priority: 1,
		}
	},
	methods: {
		closeModal() {
			this.$emit('closeModal');
		}
	},
	computed: {
		...mapGetters({
			newTodo: 'newTodo'
		}),
		title: {
			get() {
				return this.newTodo.title
			},
			set(value) {
				this.$store.dispatch('setTitle', value)
			}
		},
		priority: {
			get() {
				return ''
			},
			set(value) {
				console.log(value)
			}
		}
	}
}
</script>

<style>

</style>