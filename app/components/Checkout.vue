<template>
    <Page>
        <StackLayout>
            <Label class="h2 text-center" text="Shopping Cart" />
            <Label class="h2 text-center" text="(Tap a product to remove it)" />
            <!-- displaying cart -->
                <ListView for="product in cart" @itemTap='onItemTap'>
                    <v-template>
                        <StackLayout>
                            <Label :text="product.Activity" />
                            <Label :text="`Price: ${product.Price}`" />
                            <Label :text="`Inventory: ${product.Availability}`" />
                        </StackLayout>
                    </v-template>
                </ListView>

            <TextField hint='Name' v-model='name'/>
            <TextField hint='Phone number' v-model='phoneNr'/>
            <Button @tap='submitOrder' text='Submit Order'/>
        </StackLayout>
    </Page>
</template>


<script>
export default {
    props: ['cart'],
    methods: {
        onItemTap(event) {
        this.$emit("removeProduct", event.item);
        },
        submitOrder() {
            // if textfields are empty
            if((this.name || this.phoneNr) === "" || (this.name || this.phoneNr) === "undefined") {
                alert("Please fill in the form")
            }
            else {
                alert('An order is placed by ' + this.name)
            }
            
}
    },
    data() {
	    return {
	    };
    }
}
</script>

<style>
</style>