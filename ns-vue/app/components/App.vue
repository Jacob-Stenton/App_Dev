<template lang="html">
    <TabView androidTabsPosition="bottom">
        <TabViewItem title="Home">
            <Frame id="items">
                <Items/>
            </Frame>
        </TabViewItem>

        <TabViewItem title="Browse">
            <Frame id="browse">
                <Browse/>
            </Frame>
        </TabViewItem>

        <TabViewItem title="Search">
            <Frame id="search">
                <Search/>
            </Frame>
        </TabViewItem>
    </TabView>
</template>

<script>

    import { reactive, ref, computed } from '@vue/composition-api';
    import Items from "./Items.vue";
    import Browse from "./Browse.vue";
    import Search from "./Search.vue";

    export default {
    setup(){
        const items = reactive([
        {
            name: "Item 1",
            description: "Description for Item 1"
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

        components: {
        Items,
        Browse,
        Search
        }
    }};

     
</script>

<style lang="scss">
    // Start custom common variables
    @import "@nativescript/theme/scss/variables/blue";
    // End custom common variables

    // Custom styles

</style>
