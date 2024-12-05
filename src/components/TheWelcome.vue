<script setup>
import { useItemsStore } from './../stores/items';
import Lists from './blocks/lists.vue';
import Item from '@/components/blocks/item.vue';

const itemsStore = useItemsStore();

const addToList = (item) => {
    itemsStore.addToClientItems(item);
}

const changeSelectItem = (item) => {
  itemsStore.changeSelectItem(item);
}

</script>

<template>
  <div class="container --justfy">
    <div 
      v-if="itemsStore.getClientItems.length > 0"
      class="b-client"
    >
      <Lists :items="itemsStore.getClientItems" class="b-client-items" />
      <div>selected {{ itemsStore.getClientItems.length }}/6</div>
    </div>
    <div>
      <Item 
        v-if="itemsStore.getSelectItem?.name"
        :item="itemsStore.getSelectItem" class="item-big" 
      />
    </div>
  </div>
  <div class="container --h100">
    <Lists :items="itemsStore.getItemsLeft" @add-item="addToList" class="b-lists" />
    <Lists :items="itemsStore.getItemsRight" @add-item="changeSelectItem" class="b-lists" />
  </div>
</template>
