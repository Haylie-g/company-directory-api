<script setup>
import { faker } from '@faker-js/faker'
// const firstname = faker.person.firstName()
// const lastname = faker.person.lastName()
// const fullname = faker.person.fullName({ firstname: firstname, lastname: lastname })
// const job_title = faker.person.jobTitle()
// const bio = faker.lorem.lines(2)
// const username = faker.internet.userName({ firstname: firstname, lastname: lastname }).toLowerCase()


const props = defineProps({
  employee: {
    type: Object,
    required: true,
    default: () => {
      return {
        _id: "65f1b471c1d4a06a0786c3bc",
        userName: "jperez",
        firstName: "Joseph",
        lastName: "Perez",
        title: "Computer Science Wizard",
        quote: "You shall not pass!!",
        _v: 0,


      }
    },
  },
})
</script>

<template>
  <!-- {{ fullname }}<br /> -->
  <RouterLink :to="{name: 'CardDetails', params: {id: props.employee._id}}">
    <div class="border border-gray-400 rounded-lg shadow bg-gray-200 h-full"></div>
    <div>
        <img :src="faker.image.urlLoremFlickr({width: 640, height: 480, category:'cat'})" class="rounded-t-xl w-full h-48 object-cover" />
        <div class="p-4">
           <p class="mb-2 text-2xl font-bold">{{ props.employee.firstName }}  {{ props.employee.lastName }}</p>
            <p class="mb-3 font-normal text-gray-700">{{ props.employee.title }}</p>
            <p class="mb-3 font-normal text-gray-700">{{ props.employee.quote }}</p> 
        </div>
    </div>
    </RouterLink>
</template>