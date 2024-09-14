<!-- 7.Створіть обчислювальну властивість для виведення даних, обчислених на основі інших реактивних даних. -->

<template>
    <div class="task-border">
        <p class="h4">Task 7.</p>
        <p> {{ result }}</p>
        <div class="form-task7">
            <input type="text" class="form-control" placeholder="Input Text" v-model="lastname">
            <input type="text" class="form-control" placeholder="Input Text" v-model="firstname">
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Task7',
        data() {
            return {
                firstname: 'Maxim',
                lastname: 'Pryimak'
            }
        },
        computed: {
            result() {
                return this.lastname + ' ' + this.firstname
            }
        }
    }
</script>

<style lang="css" scoped>
    .form-task7{
        display: flex;
        gap: 15px;
    }
    .form-control {
        border-color: #76fad2;
    }

</style>