<!-- 1.Створіть реактивний об'єкт і виведіть його властивості в шаблон. Змініть властивість об'єкта і спостерігайте за змінами в DOM.

     2.Створіть метод, який буде викликатися при кліку на кнопку і змінювати деякі дані в інстансі -->
<template>
    <div class="task-border w-300">
        <div class="row-center">
            <p class="h4 text-center">Task 1-2.</p>
            <div>
                <div class="text-center">{{counter}}</div>
            </div>
        </div>
        <div class="row-center">
            <div class="action-block">
                <button class="btn btn-success btn-counter" @click="increment">+</button>
                <button class="btn btn-danger btn-counter" @click="decrement">-</button>
            </div>
        </div> 
    </div>
</template>

<script>
    export default {
        name: 'Task',
        data() {
            return {
                counter: 0,
                message: 'This message from new component'
            }
        },
        methods: {
            increment() {
                this.counter++
            },
            decrement() {
                this.counter--
            },
            changeMessage() {
                this.message = "This message was changed by method changeMessage"
            }
        }
    }
</script>

<style lang="css" scoped>


</style>