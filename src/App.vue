<template>
    <section>
        <h2>My Friends</h2>
        <ul>
            <friend-contact></friend-contact>
        </ul>
    </section>
</template>

<script>
    export default {
        data(){
            return {
                friends: [
                    {
                        id: 1,
                        name: 'Pablo Quevedo',
                        phone: '645 123685',
                        email: 'pablo@quevedo.com'
                    },
                    {
                        id: 2,
                        name: 'Laura Flor',
                        phone: '645 854369',
                        email: 'laura@flowers.com'
                    },
                    {
                        id: 3,
                        name: 'Señor Q',
                        phone: '645 854369',
                        email: 'señor@q.com'
                    }
                ]
            }
        },
    };
</script>
