<template>
    <section>
        <ul>
            <li :key="dish['id']" v-for="dish in dishes">
                {{ dish.name }}
            </li>
            <br>
            <li :key="(user['id']) + 100" v-for="user in users">
                {{ user.name }}
            </li>
            <br>
            <li :key="(category['id']) + 200" v-for="category in categories">
                {{ category.cuisine }}
            </li>
            <br>
            <li :key="(allergen['id']) + 300" v-for="allergen in allergens">
                {{ allergen.name }}
            </li>
            <br>
            <li :key="(order['id']) + 400" v-for="order in orders">
                {{ order.name_user }}
            </li>
            <br>
            <li :key="(dishOrder['id']) + 500" v-for="dishOrder in dishOrders">
                {{ dishOrder.dish_id }}
                {{ dishOrder.order_id }}
            </li>
            <br>
            <li :key="(allergenDish['id']) + 600" v-for="allergenDish in allergenDishes">
                {{ allergenDish.allergen_id }}
                {{ allergenDish.dish_id }}
            </li>
            <br>
            <li :key="(categoryUser['id']) + 700" v-for="categoryUser in categoryUsers">
                {{ categoryUser.category_id }}
                {{ categoryUser.user_id }}
            </li>
        </ul>
    </section>
</template>

<script>
export default {
    name: "Api",
    data() {
        return {
            url: "http://127.0.0.1:8000/api/",
            flag: false,
            dishes: [],
            users: [],
            categories: [],
            allergens: [],
            orders: [],
            dishOrders: [],
            allergenDishes: [],
            categoryUsers: [],
            categoryUsers: [],
            api_token:
                "bbzRf42NwlCuPIdwL7AiHgXskzLa69GB61Tn8QA7VZ1woSustPL1NfelqeHpfolpwhwX6lR1OolmJf3k",
        };
    },
    created() {
        this.getDishes();
        this.getUsers();
        this.getCategories();
        this.getAllergens();
        this.getOrders();
        this.getDishOrders();
        this.getAllergenDishes();
        this.getCategoryUsers();
    },
    methods: {
        getDishes(){
            const bodyParameters = {
                key: "value",
            };

            const config = {
                headers: { Authorization: `Bearer ${this.api_token}` },
            };
            axios
                .get(this.url + 'dishes' , bodyParameters, config)
                .then((resp)=>{
                    this.dishes = resp.data.results
                })
                .catch();
        },
        getUsers(){
            const bodyParameters = {
                key: "value",
            };

            const config = {
                headers: { Authorization: `Bearer ${this.api_token}` },
            };
            axios
                .get(this.url + 'users', bodyParameters, config)
                .then((resp)=>{
                    this.users = resp.data.results
                })
                .catch();
        },
        getCategories(){
            const bodyParameters = {
                key: "value",
            };

            const config = {
                headers: { Authorization: `Bearer ${this.api_token}` },
            };
            axios
                .get(this.url + 'categories', bodyParameters, config)
                .then((resp)=>{
                    this.categories = resp.data.results
                })
                .catch();
        },
        getAllergens(){
            const bodyParameters = {
                key: "value",
            };

            const config = {
                headers: { Authorization: `Bearer ${this.api_token}` },
            };
            axios
                .get(this.url + 'allergens', bodyParameters, config)
                .then((resp)=>{
                    this.allergens = resp.data.results
                })
                .catch();
        },
        getOrders(){
            const bodyParameters = {
                key: "value",
            };

            const config = {
                headers: { Authorization: `Bearer ${this.api_token}` },
            };
            axios
                .get(this.url + 'orders', bodyParameters, config)
                .then((resp)=>{
                    this.orders = resp.data.results
                })
                .catch();
        },
        getDishOrders(){
            const bodyParameters = {
                key: "value",
            };

            const config = {
                headers: { Authorization: `Bearer ${this.api_token}` },
            };
            axios
                .get(this.url + 'dishOrders', bodyParameters, config)
                .then((resp)=>{
                    this.dishOrders = resp.data.results
                })
                .catch();
        },
        getAllergenDishes(){
            const bodyParameters = {
                key: "value",
            };

            const config = {
                headers: { Authorization: `Bearer ${this.api_token}` },
            };
            axios
                .get(this.url + 'allergenDishes', bodyParameters, config)
                .then((resp)=>{
                    this.allergenDishes = resp.data.results
                })
                .catch();
        },
        getCategoryUsers(){
            const bodyParameters = {
                key: "value",
            };

            const config = {
                headers: { Authorization: `Bearer ${this.api_token}` },
            };
            axios
                .get(this.url + 'categoryUsers', bodyParameters, config)
                .then((resp)=>{
                    this.categoryUsers = resp.data.results
                })
                .catch();
        },
    },
};
</script>
