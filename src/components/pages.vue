<template>
    <section>
      Pages
    </section>
</template>
<script>
export default {
    name: 'pages',

    data() {
        return {
            show: true
        }
    },
    props: {
        components: {
            type: Array,
            default: null
        }
    },
    methods: {
        slotToComponents(slot) {
            return this.$store.state.components.filter(c => slot.findIndex(item => item.id === c.info.id) !== -1)
        },
        click(id) {
            let el = document.getElementById(id)
            el.click()
        }
    }
}
</script>
<style lang="css" scoped>
a {
    cursor: pointer;
}

section {
    margin-left: 20px;
}
</style>
