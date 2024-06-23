<template>
    <dir class="root">
        <p>Єба, це працює</p>
        <p>Введіть ім'я користувача</p>
        <input type="text" @input="selectedUsers = $event.target.value"/>
        <div>
            <div>Кількість користувачів {{ users.length }} </div>
            <div>Кількість співпадінь {{ arrOfNames.length }} </div>
        </div>
        <ul>
            <li
            v-for="(people, index) in arrOfNames"
            :key="index">{{people}}</li>
        </ul>
    </dir>
</template>

<script>
export default {
    name: 'firstComponent',
    data(){     
        return{
            users: ['Vadim', 'Vikrotia', 'Vlad', 'Nata', 'Andryw', 'Vadim Atamanyuk'],
            selectedUsers: ''
        }
    },
    computed: {
        arrOfNames(){
            return this.users.filter(name => name.toLowerCase().includes(this.selectedUsers.toLowerCase()))
        }
    }      
}
</script>