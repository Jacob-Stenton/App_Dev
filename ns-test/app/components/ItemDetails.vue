<template>
    <Page>
        <ActionBar>
            <NavigationButton @tap="$navigateBack()" android.systemIcon="ic_menu_back"/>
            <Label :text="item.name"></Label>
        </ActionBar>

        <ScrollView orientation="vertical" scrollBarIndicatorVisible="false">
            <StackLayout orientation="vertical">
                <Image :src="item.image_src" stretch="none" />
                <TextView :text="item.description" editable="false" />
                <Label text="Ingridients"   
                style="font-size: 20px" />
                <Label v-for="ingr in item.ingredients" :key="item.name" :text="ingr" />
                <Label text="Instructions"   
                style="font-size: 20px" />
                <TextView :text="item.instructions" editable="false" />
                <!-- description 
                Ingredient label
                ingredients vfor
                intructions-->
            </StackLayout>
        </ScrollView>
    </Page>
</template>

<script>
import { ListView, ScrollView, StackLayout } from '@nativescript/core';

export default {
    props: ['item'],
    setup(props){
    }
};
</script>

<style scoped lang="scss">
    // Start custom common variables
    @import "@nativescript/theme/scss/variables/blue";
    // End custom common variables

    // Custom styles

</style>
