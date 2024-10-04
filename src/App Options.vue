<script>
export default{
  data(){
    return {
      name: 'John Doe',
      status: 'active',
      task: ['Task One', 'Task Two', 'Task Three'],
      link: 'https://vuejs.org'
    }
  },
  methods: {
    toggleStatus(){
      if(this.status === 'active'){
        this.status = 'pending'
      } else if(this.status === 'pending'){
        this.status = 'inactive'
      } else {
        this.status = 'active'
      }
    }
  }
}
</script>

<template>
  <h1>{{name}}</h1>
  <p v-if="status === 'active'">User is Active</p>
  <p v-else-if="status === 'pending'">User is Pending</p>
  <p v-else>User is Inactive</p>

  <h3>Tasks: </h3>
  <ul>
    <li v-for="task in task" :key="task">{{task}}</li>
  </ul>
  <!-- <a v-bind:href="link">Click for more info</a> -->
  <a :href="link">Click for more info</a>
  <br/>
  <button @click="toggleStatus">Change status</button>
</template>