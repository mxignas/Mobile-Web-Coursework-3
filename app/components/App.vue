<template>
    <Page>
        <ActionBar title="Lesson shop"/>
        <Label Text="Lesson shop" class="h2"/>

        <TabView androidTabsPosition="bottom" androidSelectedTabHighlightColor="aqua" class="bottom">
            <TabViewItem title="Lesson List">
                <LessonList @AddProduct="addToCart" /> <!-- using the component -->
            </TabViewItem>
            <TabViewItem title="Checkout">
                <Checkout :cart='cart' @removeProduct='removeFromCart'/>
            </TabViewItem>
        </TabView>


    </Page>
</template>

<script>
    import Checkout from "./Checkout.vue";
    import LessonList from "./LessonList.vue";

    export default {
        name: "App",
        components: {
            Checkout,
            LessonList
        },
        data () {
            return {
                cart: [],
            };
        },
        methods: {
            addToCart(product) {
                // if product availability is more than zero
                if(product.Availability > 0) {
                    // everytime we add to cart, availability goes -1
                    product.Availability = product.Availability - 1;
                    this.cart.push(product)
                    alert("Added to cart: " + product.Activity +" " + product.Availability)
                }
                else {
                    alert("No more available spaces")
                }
                
            },
            removeFromCart(product) {
                for (let i= 0; i < this.cart.length; i++) {
                    if(this.cart[i] == product) this.cart.splice(i, 1)
                    alert(product.Activity + " has been removed from the cart")
                }
            }
        }
    };
</script>

<style>
</style>