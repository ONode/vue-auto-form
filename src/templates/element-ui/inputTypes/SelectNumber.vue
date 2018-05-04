<template>
    <el-select
            :name="name"
            :disabled="disabled"
            :placeholder="input.placeholder"
            v-model="currentValue"
            @change="onChange">
        <el-option v-for="(item,k) in input.values"
                   :key="item.value + '.' + k"
                   :value="item.value"
                   :label="item.label"/>
    </el-select>
</template>

<script>
    export default {
        props: {
            value: {},
            name: String,
            input: Object,
            disabled: Boolean
        },
        data () {
            return {
                currentValue: this.input.defaultValue
            }
        },
        methods: {
            onChange (value) {
                this.$emit ('change', value)
            }
        }
    }
</script>

<style scoped>
    .el-select {
        display: block !important;
    }
</style>
