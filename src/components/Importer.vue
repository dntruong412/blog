<template>
    <div>
        <input type="checkbox" :id="id" :value="name" @change="change">
        <label :for="id">{{name}}</label>
    </div>
</template>
<script>
    export default {
        name: 'Importer',
        props: ['id', 'name'],
        model: {
            event: 'change'
        },
        methods: {
            change($event) {
                let currentValue = this.$attrs.value;
                let elementValue = $event.target.value;

                if ($event.target.checked) {
                    currentValue.push(elementValue);
                } else {
                    currentValue.splice(currentValue.indexOf(elementValue), 1);
                }

                this.$emit('change', currentValue);
            }
        }
    }
</script>