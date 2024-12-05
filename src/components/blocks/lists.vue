<script setup>
import Item from './item.vue'

const props = defineProps({
    items: {
        type: Object,
        requeried: true
    }
});
</script>

<template>
    <div>
        <Item
            v-for="item in items"
            :key="item.id"
            :item="item" 
            @click="$emit('addItem', item)"
        />
    </div>
</template>

<style scoped>
.b-lists {
    width: 50%;
    padding: 1rem;
    border: #000 solid 1px;
    display: flex;
    gap: 1rem;
    margin: 2rem 0;
}

.b-client-items {
    width: auto;
    display: flex;
    gap: 1rem;
}
</style>