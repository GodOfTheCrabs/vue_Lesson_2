<!-- 3.Створіть метод, який приймає подію і використовує ії для зміни даних інстанса. -->

<template>
    <div class="form task-border w-300">
        <form>
            <div class="form-group">
                <p class="h4">Task 3.</p>
                <label for="formGroupExampleInput">{{ text }}</label>
                <input type="text" class="form-control" id="formGroupExampleInput" placeholder="Input Text" :value="text" @input="changeForm">
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        name: 'Task3',
        data() {
            return {
                text: 'Test',
            }
        },
        methods: {
            changeForm(event) {
                this.text = event.target.value
            },
        }
    }
</script>

<style scoped>

.form-control {
    border-color: #76fad2;
}

</style>