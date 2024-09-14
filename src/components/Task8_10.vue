<!-- 8.Створіть computed property для фільтрації списку об'єктів.

    (9.Створіть computed property, яке комбінує дані відповіді від HTTP запиту та з рекативною змінною.) - не понял как сделать это задание

    10.Створіть кілька computed properties, які залежать одне від одного. -->

<template>
    <div class="task-border">
        <p class="h4">Task 8-10</p>
        <p class="h4">Search employee by position</p>
        <input type="text" class="form-control" placeholder="Search" v-model="searchQuery">
        <ul class="list-group">
            <li class="list-group-item list-group-item-info" v-for="(employee, id) in sortedEmployeesByAge" :key="employee.id">
                Name: {{ employee.name }} <br> Age: {{ employee.age }} <br> Position: {{ employee.position }}
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'Task8',
        data() {
            return {
                employees: [
                    { id: 1, name: 'John Doe', age: 30, position: 'Developer' },
                    { id: 2, name: 'Jane Smith', age: 25, position: 'Designer' },
                    { id: 3, name: 'Sam Johnson', age: 35, position: 'Manager' },
                    { id: 4, name: 'Will Betcher', age: 25, position: 'Developer' },
                    { id: 5, name: 'Steve Overbeck', age: 40, position: 'Manager' },
                ],
                searchQuery: ''
            }
        },
        computed: {
            filteredEmployees() {
                return this.employees.filter(employee => {
                    return employee.position.toLowerCase().includes(this.searchQuery.toLowerCase())
                })
            },
            sortedEmployeesByAge() {
                return this.filteredEmployees.sort((a, b) => a.age - b.age)
            }
        }
    }
</script>

<style lang="css" scoped>
    input {
        margin-bottom: 10px;
    }
</style>