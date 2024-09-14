<!-- 6.Створіть метод, який буде перевіряти введені дані у формі на відповідність деяким правилам. -->

<template>
    <div class="task-border">
        <form>
            <div class="form-group">
                <p class="h4">Task 6.</p>
                <p class="h4">Create new password</p>
                <input type="password" class="form-control w-50" placeholder="Input Text" :value="password" @input="changePassword">
                <button type="button" class="btn btn-primary btn-massive" @click="checkLengthPassword">Check password length</button>
                <p class="h4 text-success" v-if="passwordError">Password of the required length </p>
                <p class="h4 text-danger" v-else>Password must be 8 characters long</p>
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        name: 'Task6',
        data() {
            return {
                password: '',
                passwordError: false,
            }
        },
        methods: {
            checkLengthPassword() {
                if( this.password.length > 8) {
                    this.passwordError = true
                } 
                else {
                    this.passwordError = false
                }
            },
            changePassword(event) {
                this.password = event.target.value
                console.log(this.password.length)
            },
        }
    }
</script>

<style lang="css" scoped>
    div {
        margin-top: 15px;
    }
    button {
        margin: 25px 0;
    }
    .form-control {
        border-color: #76fad2;
    }

</style>