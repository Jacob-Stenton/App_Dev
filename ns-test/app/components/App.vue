<template lang="html">
    <TabView androidTabsPosition="bottom">
        <TabViewItem title="Home">
            <Frame id="items">
                <Items :items="items" @addItem="addItem" />
            </Frame>
        </TabViewItem>

        <TabViewItem title="Browse">
            <Frame id="browse">
                <Browse/>
            </Frame>
        </TabViewItem>

        <TabViewItem title="Search">
            <Frame id="search">
                <Search :items="items"/>
            </Frame>
        </TabViewItem>
    </TabView>
</template>

<script>
import {reactive, ref, computed} from "@vue/composition-api";
import Items from "./Items.vue";
import Browse from "./Browse.vue";
import Search from "./Search.vue";

export default {
    components: {
        Items,
        Browse,
        Search
    },
    setup(){
        const items = reactive([
            {
                name: "Pancake",
                image_src: "~/Images/PancakeMain.jpg",
                description: "Easy, American-style, fluffy pancakes are great for feeding a crowd at breakfast or brunch. Top with something sweet like fruit, jam or syrup, or rashers of crispy bacon.",
                ingredients: ["200g self-raising flour", "1 ½ tsp baking powder", "1 tbsp golden caster sugar", "3 large eggs", "25g melted butter, plus extra for cooking", "200ml milk","vegetable oil, for cooking"],
                instructions: "STEP 1 \n\n Mix 200g self-raising flour, 1 ½ tsp baking powder, 1 tbsp golden caster sugar and a pinch of salt together in a large bowl. \n\n STEP 2 \n\n Create a well in the centre with the back of your spoon then add 3 large eggs, 25g melted butter and 200ml milk. \n\n STEP 3 \n\n Whisk together either with a balloon whisk or electric hand beaters until smooth then pour into a jug. \n\n STEP 4 \n\n Heat a small knob of butter and 1 tsp of oil in a large, non-stick frying pan over a medium heat. When the butter looks frothy, pour in rounds of the batter, approximately 8cm wide. Make sure you don’t put the pancakes too close together as they will spread during cooking. Cook the pancakes on one side for about 1-2 mins or until lots of tiny bubbles start to appear and pop on the surface. Flip the pancakes over and cook for a further minute on the other side. Repeat until all the batter is used up. \n\n STEP 5 \n\n Serve your pancakes stacked up on a plate with a drizzle of maple syrup and any of your favourite toppings."
            
            },
            {
                name: "Item 2",
                description: "Description for Item 2"
            },
            {
                name: "Item 3",
                description: "Description for Item 3"
            },
            {
                name: "Item 4",
                description: "Description for Item 4"
            },
            {
                name: "Item 5",
                description: "Description for Item 5"
            },
            {
                name: "Item 6",
                description: "Description for Item 6"
            },
            {
                name: "Item 7",
                description: "Description for Item 7"
            },
            {
                name: "Item 8",
                description: "Description for Item 8"
            },
            {
                name: "Item 9",
                description: "Description for Item 9"
            },
            {
                name: "Item 10",
                description: "Description for Item 10"
            }
        ]);

        // Add item to array received from child event
        const addItem = (item) => {
            items.push(item);
        };

        return {
            items,
            addItem
        };
    }
};
</script>

<style lang="scss">
    // Start custom common variables
    @import "@nativescript/theme/scss/variables/blue";
    // End custom common variables

    // Custom styles

</style>
