<!-- <template>
    <div class="mt-5">
        <form @submit="submitForm" class="px-4 my-10 max-w-3xl mx-auto space-y-3 drop-shadow-md" onsubmit="" action=""
            method="post">
            <h1 class="text-3xl font-semibold">Personal Details - CRUD Operations</h1>
            <hr class="bg-black">
            <div class="flex space-x-4">
                <div class="w-1/2">
                    <label for="Name">First Name:</label>
                    <input v-model="user.firstName"
                        class="border border-gray-400 block px-4 py-1 w-full rounded focus:outline-none focus:border-teal-500"
                        type="text" name="firstname" id="firstname">
                </div>
                <div class="w-1/2">
                    <label for="Name">Last Name:</label>
                    <input v-model="user.lastName"
                        class="border border-gray-400 block px-4 py-1 w-full rounded focus:outline-none focus:border-teal-500"
                        type="text" name="lastname" id="lastname">
                </div>
            </div>

            <div class="flex space-x-4">
                <div class="w-1/2">
                    <label for="Email">Email:</label>
                    <input v-model="user.email"
                        class="border border-gray-400 block px-4 py-1 w-full rounded focus:outline-none focus:border-teal-500"
                        type="email" name="email" id="email">
                </div>
                <div class="w-1/2">
                    <label for="Contact">Contact:</label>
                    <input v-model="user.contact"
                        class="border border-gray-400 block px-4 py-1 w-full rounded focus:outline-none focus:border-teal-500"
                        type="text" name="contact" id="contact">
                </div>
            </div>

            <div class="form_action_button space-x-2">
                <button class="border border-gray-400 px-4 py-2 max-w-xs rounded bg-teal-600 text-white" type="submit"
                    value="Submit">Submit</button>
                <button
                    class="border border-gray-400 px-4 py-2 max-w-xs rounded text-teal-600 hover:bg-red-600 hover:text-white"
                    type="reset">Reset</button>
            </div>
        </form>
        <p v-for="per in allUser" :key="per">Details : {{ per.firstName + ' ' + per.lastName + ' ' + per.email + ' ' +
                per.contact
        }}</p>
    </div>
</template>

<script >
export default {
    data() {
        return {
            allUser: [],
            user: {
                firstName: "",
                lastName: "",
                email: "",
                contact: "",
            },
        };

    },
    methods: {
        submitForm(event) {
            event.preventDefault();
            this.allUser.push(this.user);
            this.user = { firstName: '', lastName: '', email: '', contact: '' };
            console.log(this.allUser);

        }
    }

}
// var users=[];
// const formData = reactive({
//     // firstName: "",
//     // lastName: "",
//     // email: "",
//     // contact: "",

//     // details: computed (() => {
//     //     console.log("bgh" , formData.firstName)
//     //     return  formData.firstName + ' ' + formData.lastName + ' ' + formData.email + ' ' + formData.contact
//     // })

// });
//   console.log( users.push(formData))

// document.write(formData.firstName);
// users.push(this.)


</script> -->
<template>
    <div class="mt-5">
        <form @submit="submitForm" class="px-4 my-10 max-w-3xl mx-auto space-y-3 drop-shadow-md"
            method="post">
            <h1 class="text-3xl font-semibold">Personal Details - CRUD Operations</h1>
            <hr class="bg-black">
            <div class="flex space-x-4">
                <div class="w-1/2">
                    <label for="Name">First Name:</label>
                    <input v-model="user.firstName"
                        class="border border-gray-400 block px-4 py-1 w-full rounded focus:outline-none focus:border-teal-500"
                        type="text" name="firstname" id="firstname">
                </div>
                <div class="w-1/2">
                    <label for="Name">Last Name:</label>
                    <input v-model="user.lastName"
                        class="border border-gray-400 block px-4 py-1 w-full rounded focus:outline-none focus:border-teal-500"
                        type="text" name="lastname" id="lastname">
                </div>
            </div>

            <div class="flex space-x-4">
                <div class="w-1/2">
                    <label for="Email">Email:</label>
                    <input v-model="user.email"
                        class="border border-gray-400 block px-4 py-1 w-full rounded focus:outline-none focus:border-teal-500"
                        type="email" name="email" id="email">
                </div>
                <div class="w-1/2">
                    <label for="Contact">Contact:</label>
                    <input v-model="user.contact"
                        class="border border-gray-400 block px-4 py-1 w-full rounded focus:outline-none focus:border-teal-500"
                        type="text" name="contact" id="contact">
                </div>
            </div>

            <div class="form_action_button space-x-2">
                <button class="border border-gray-400 px-4 py-2 max-w-xs rounded bg-teal-600 text-white" type="submit"
                    value="Submit">Submit</button>
                <button
                    class="border border-gray-400 px-4 py-2 max-w-xs rounded text-teal-600 hover:bg-red-600 hover:text-white"
                    type="reset">Reset</button>
            </div>
        </form>
      
        <table class="border border-black p-x-4">
            <tr>
                <td>First Name</td>
                <td>Last Name</td>
                <td>Email</td>
                <td>Contacts</td>
            </tr>
           
            <tr v-for="(per,index) in users"  v-bind:index="index" :key="per">
                <td>{{ per.firstName }}</td>
                <td>{{ per.lastName }}</td>
                <td>{{ per.email }}</td>
                <td>{{ per.contact }}</td>
                <td><button @click="editData(index)"
                        class="border border-gray-400 px-2 py-1 max-w-xs rounded bg-teal-600 text-white" type="submit"
                        value="Submit">Update</button></td>
                <td><button @click="deleteData(index)"
                        class="border border-gray-400 px-2 py-1 max-w-xs rounded bg-teal-600 text-white" type="submit"
                        value="Submit">Delete</button></td>
            </tr>
        </table>
    </div>
</template>

<script>
export default {
    data() {
        return {
            users: [],
            user: {
                isEdit:true,
                editIndex:-1,
                // error:[],
                Name: '',
                Place: '',
                Email: '',
                Password: '',
                Company: ''
            }
        }
    },
    methods: {
        submitForm(event) {
            event.preventDefault();
            if (this.isEdit == true) {
                this.users[this.editIndex] = this.user;
                this.isEdit = false;
                this.editIndex = -1;
            } else {
                this.users.push(this.user);
            }
            this.user = {
                firstName: "",
                lastName: "",
                email: "",
                contact: "",
            }
            console.log(this.users)
        },
        deleteData(index) {
            if (confirm('You Want To Delete The Data ?'))
                this.users.splice(index, 1);
        },
        editData(index) {
            console.log("users = ",this.users[index].firstName)
            this.user.firstName = this.users[index].firstName;
            this.user.lastName = this.users[index].lastName;
            this.user.email = this.users[index].email;
            this.user.contact = this.users[index].contact;
            this.isEdit = true;
            this.editIndex = index;
        },
    }
}
</script>


<style>
table,
tr,
td {
    border: 1px black solid;
}
</style>