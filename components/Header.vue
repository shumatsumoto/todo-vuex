<template>
	<div id="header">
		<div class="appNameWrapper">
			<span>Todo App</span>
		</div>
		<div @click="isShowModal = true" class="addNew">
			<span>新規作成</span>
		</div>
		<AddNewModal @closeModal="isShowModal = false" v-if="isShowModal" />
	</div>
</template>

<script>
export default {
	data() {
		return {
			isShowModal: false,
		}
	}

}
</script>

<style>

</style>