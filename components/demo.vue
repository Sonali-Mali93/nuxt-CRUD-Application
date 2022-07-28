<template>
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


</script>