<template>
    <input
        :value="valueX"
        @input="updateInput"
        class="input"
        type="text"
    >
</template>

<script>
    export default {
        name: 'my-input',
        props: {
            // modelValue: [String, Number]
            valueX: [String, Number]
        },
        methods: {
            updateInput(event) {
                // this.$emit('update:modelValue', event.target.value)
                this.$emit('update:valueX', event.target.value)
            }
        }
    }
</script>

<style scoped>
.input {
	border: 2px solid teal;
	padding: 10px 15px;
	margin: 0 20px 20px 20px;
}
</style>