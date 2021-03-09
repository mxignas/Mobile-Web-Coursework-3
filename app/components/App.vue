<template lang="html">
<Page>
    <Label Text="Lesson shop" class="h2"/>

    <BottomNavigation selectedIndex="0">
        <TabStrip class="bottom_navigation">
            <TabStripItem class="navigation__item">
                <Label text="LessonList"></Label>
                <!-- <ProductList @addProduct="addToCart" /> -->
            </TabStripItem>
            <TabStripItem class="navigation__item">
                <Label text="Checkout"></Label>
            </TabStripItem>
        </TabStrip>

        <TabContentItem>
            <Frame id="LessonList">
                <LessonList />
            </Frame>
        </TabContentItem>

        <TabContentItem>
            <Frame id="Checkout">
                <Checkout />
            </Frame>
        </TabContentItem>

    </BottomNavigation>
</Page>
</template>

<script>
    import Checkout from "./Checkout.vue";
    import LessonList from "./LessonList.vue";

    export default {
        data () {
            return {
                components: {
                    Checkout,
                    LessonList
                },
                methods: {
                    addToCart(product) {
                        this.cart.push(product)
                        alert("Added to cart: " + product.Title)
                    }
                }
            }
        }
        
    };
</script>

<style>
</style>