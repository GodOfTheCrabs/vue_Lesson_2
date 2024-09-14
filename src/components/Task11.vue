<!-- 11.Використовуйте watcher для відстеження змін у реактивному об’єкті та виведення повідомлення про це.

    12.Використовуйте watcher для відстеження змін однієї властивості у реактивному об’єкті та виведення повідомлення про це.

    13.(Використовуйте watcher для відправлення API запитів при зміні реактивних даних.) - также не понял как мне это сделать

    14.Створіть watcher, який реагує на зміни в computed property.

    15.Використовуйте deep опцію для відстеження властивостей внутрішніх об’єктів.

    16.Використовуйте опцію immediate для виклику watcher при ініціалізації компонента. -->

<template>
    <div class="task-border">
        <p class="h4">Task 11-16</p>
        <p class="h4"> {{ result }}</p>
        <div class="form-task7">
            <input type="text" class="form-control" placeholder="Input Text" v-model="firstname">
        </div>
        <div>
            <p class="h4">Name: {{ someObj.name  }} Age: {{ someObj.age  }}</p>
            <button type="button" class="btn btn-primary btn-massive" @click="handler">Change obj age</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Task11',
        data() {
            return {
                firstname: 'Maxim',
                someObj: {
                    name: 'John',
                    age: 25
                }
            }
        },
        computed: {
            result() {
                return this.firstname
            }
        },
        methods: {
            handler() {
                this.someObj.age = 30
            }
        },
        watch: {
            firstname(newValue, oldValue) {
                console.log(newValue, oldValue)
            },
            'someObj.age'(newValue, oldValue) {
                console.log(newValue, oldValue)
            },
            "someObj": {
                handler(newValue, oldValue) {
                console.log(newValue, oldValue)
            },
                deep: true,
                immediate: true
            },
            result(newValue, oldValue) {
                console.log(newValue, oldValue)
            }
        }
    }
</script>

<style lang="css" scoped>

</style>