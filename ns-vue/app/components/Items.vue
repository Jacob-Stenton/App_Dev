<template>
    <Page>
        <ActionBar>
            <Label text="Home"></Label>
            <ActionItem @tap="addItem"
              ios.systemIcon="4" ios.position="right"
              android.systemIcon="btn_plus" android.position="actionBar" 
            />

            <ActionItem @tap="removeItem"
              ios.systemIcon="5" ios.position="left"
              android.systemIcon="btn_minus" android.position="actionBar" 
            />
        </ActionBar>

        <ListView for="item in items" @itemTap="onItemTap">
            <v-template>
                <StackLayout orientation="horizontal">
                    <Label :text="item.name" textWrap="true"></Label>
                </StackLayout>
            </v-template>
        </ListView>
    </Page>
</template>

<script>
import Vue from 'nativescript-vue';
import { reactive, ref, computed } from '@vue/composition-api';
import ItemDetails from "./ItemDetails";

export default {
  setup(){

    const onItemTap = (args) => {
      Vue.navigateTo(ItemDetails, {
        frame: 'items',
        props: {item: items[args.index]},
        animated: true,
        transition: {
          name: "slide",
          duration: 200,
          curve: "ease"
        }
      });
    };

    const addItem = () => {
      items.push({
        name: `Item ${items.length + 1}`,
        description: `Description of for Item ${items.length + 1}`
      });
    };

    const removeItem = () => {
      items.pop();
    };

    return {
      items,
      onItemTap,
      addItem,
      removeItem
    };
  }
};
</script>

<style scoped lang="scss">
    // Start custom common variables
    @import "@nativescript/theme/scss/variables/blue";
    // End custom common variables

    // Custom styles

</style>
