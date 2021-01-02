<template>
    <li>
        <h2> {{ friend.name }} </h2>
        <button @click="toogleDetails"> Show details </button>
        <ul v-if="detailsVisibility">
            <li><strong>Phone:</strong> {{ friend.phone }} </li>
            <li><strong>Email:</strong> {{ friend.email }} </li>
        </ul>
    </li>
</template>

<script>
    export default {
        data() {
            return {
                detailsVisibility: false,
                friend: {
                        id: 1,
                        name: 'Pablo Quevedo',
                        phone: '645 123685',
                        email: 'pablo@quevedo.com'
                },
            };
        },
        methods: {
            toogleDetails(){
                this.detailsVisibility = !this.detailsVisibility;
            }
        }
    };
</script>