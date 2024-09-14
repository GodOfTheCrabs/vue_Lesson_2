<!-- 5.Використайте метод для обробки події кліку, який змінює стан інших компонентів.(В файле App.vue есть метод changeMessage) -->

<template>
    <div>
        <p class="h4">Task 5.</p>
        <p class="h4">{{ result }}</p>
    </div>
</template>

<script>
    export default {
        name: 'Task5',
        props: {
            result: {
                type: String,
                required: true
            }
        },
        data() {
            return {
                
            }
        }
    }
</script>

<style lang="css" scoped>
    div {
        margin-top: 15px;
    }
</style>