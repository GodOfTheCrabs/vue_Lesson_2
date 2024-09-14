<!-- 4.Створіть метод для фільтрації масиву об'єктів за деяким критерієм. -->

<template>
    <div class="task-border">
        <div>
            <p class="h4">Task 4.</p>
            <button type="button" class="btn btn-primary btn-massive" @click="getEmployees">Get all employees</button>
            <button type="button" class="btn btn-primary btn-massive" @click="getDeveloper">Get only developer</button>
            <button type="button" class="btn btn-primary btn-massive" @click="getAge30">Get employee where age = 25</button>
        </div>
        <ul class="list-group" v-if="showEmployees === 'All'">
            <li class="list-group-item list-group-item-info" v-for="(employee, id) in employees" :key="employee.id">
                Name: {{ employee.name }} <br> Age: {{ employee.age }} <br> Position: {{ employee.position }}
            </li>
        </ul>
        <ul class="list-group" v-if="showEmployees === 'Developer'">
            <template v-for="(employee, id) in employees" :key="employee.id">
                <li class="list-group-item list-group-item-info" v-if="showEmployees === employee.position">
                    Name: {{ employee.name }} <br> Age: {{ employee.age }} <br> Position: {{ employee.position }}
                </li>
             </template>
        </ul>
        <ul class="list-group" v-if="showEmployees === 25">
            <template v-for="(employee, id) in employees" :key="employee.id">
                <li class="list-group-item list-group-item-info" v-if="showEmployees === employee.age">
                    Name: {{ employee.name }} <br> Age: {{ employee.age }} <br> Position: {{ employee.position }}
                </li>
             </template>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'Task4',
        data() {
            return {
                employees: [
                    { id: 1, name: 'John Doe', age: 30, position: 'Developer' },
                    { id: 2, name: 'Jane Smith', age: 25, position: 'Designer' },
                    { id: 3, name: 'Sam Johnson', age: 35, position: 'Manager' },
                    { id: 4, name: 'Will Betcher', age: 25, position: 'Developer' },
                ],
                showEmployees: null,
            }
        },
        methods: {
            getEmployees() {
                this.showEmployees = 'All'
            },
            getDeveloper() {
                this.showEmployees = 'Developer'
            },
            getAge30() {
                this.showEmployees = 25
            },
        }
    }
</script>

<style scoped>


.list-group {
    margin-top: 15px;
}

</style>