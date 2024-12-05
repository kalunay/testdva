<script setup>
import Item from './item.vue'

const props = defineProps({
    items: {
        type: Object,
        requeried: true
    },
});
</script>

<template>
    <div class="b-client-items">
        <Item
            v-for="item in items"
            :key="item.id"
            :item="item" 
            @click="addToList(item)"
        />
    </div>
</template>

<style scoped>
.b-client-items {
    width: auto;
    padding: 1rem;
    border: #000 solid 1px;
    display: flex;
    gap: 1rem;
}
.b-selected {
    display: block;
    margin-top: 2rem;
}
</style>