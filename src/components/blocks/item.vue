<script setup>
import { useItemsStore } from '@/stores/items';

defineProps({
    item: Object,
    required: true
});
</script>

<template>
    <div class="item">
        {{ item.name }}
    </div>
</template>

<style scoped>
.item {
    display: block;
    padding: .5rem;
    border: #000 solid 1px;
    height: fit-content;
    cursor: pointer;
}
</style>
