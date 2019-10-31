<template>
    <div id="app">
        <Importer v-for="(people, index) in fNames" :key="index" :id="index" :name="people" v-model="checkedNames" />
        <br>
        <span>Checked names: {{ checkedNames }}</span>
    </div>
</template>
<script>
    export default {
        name: 'app',
        data() {
            return {
                fNames: ['jack', 'John', 'Mike', 'Schmit'],
                checkedNames: []
            }
        },
        components: {
            Importer: () => import('./components/Importer.vue')
        }
    }
</script>