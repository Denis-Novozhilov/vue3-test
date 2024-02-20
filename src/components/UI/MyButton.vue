<template>
    <button class="btn">
        <slot></slot>
    </button>
</template>

<script>
    export default {
        name: 'my-button'
    }
</script>

<style scoped>
.btn {
    width: fit-content;
	margin-right: 20px;
    padding: 0 10px;
	height: 30px;
	align-self: end;
	background: none;
	border: 1px solid teal;
	color: teal;
	border-radius: 6px;
}
</style>