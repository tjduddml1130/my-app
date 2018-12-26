<template>
<div>
    <div class="node" :style="{'margin-left': `${depth * 20}px`}" @click="modelclicked">
        <span v-if="haschildren" class="type">{{expanded ? '&#9660;':'&#9658;'}}</span>
        {{model.name}}
    </div>
    <TreeTemp v-if="expanded" v-for="children in model.children" :key="children.name" :model="children" :depth="depth + 1"></TreeTemp>
</div>
</template>

<script>
export default {
    name: 'TreeTemp',
    props: {
        model: Object,
        depth:{
            type: Number,
            default: 0
        }
    },
    data (){
        return {
            expanded: false
        }
    },
    methods: {
        modelclicked(){
            this.expanded = ! this.expanded;
        }
    },
    computed: {
        haschildren() {
            return this.model.children;
        }
    }
}
</script>

<style scoped>
.node {
    text-align: left
}
</style>
