<style src="./style.css"></style>
<template src="./template.html"></template>

<script>
    export default {
        props: {
            type: {
                type: String,
                default: 'text'
            },
            size: String,
            form: String,
            name: String,
            disabled: Boolean,
            readonly: Boolean,
            autofocus: Boolean,
            placeholder: String,
            max: [String, Number],
            min: [String, Number],
            value: [String, Number],
            maxlength: [String, Number],
            minlength: [String, Number]
        },
        computed: {
            clazz() {
                return {
                    'ui-input--mini': this.size === 'mini',
                    'ui-input--large': this.size === 'large'
                }
            }
        },
        methods: {
            blurHandler(e) {
                this.$emit('blur', e)
            },
            focusHandler(e) {
                this.$emit('focus', e)
            },
            inputHandler(e) {
                this.$emit('input', e.target.value)
                this.$emit('change', e.target.value)
            }
        }
    }
</script>