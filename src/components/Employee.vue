<template>
    <div v-if="logged">
        <table>
        <thead>
          <tr>
              <th>Id</th>
              <th>First Name</th>
              <th>Last Name</th>
              <th>Office</th>
              <th>Created at</th>
              <th>Updated at</th>
          </tr>
        </thead>

        <tbody v-for="emp in employee">
          <tr>
            <td>{{ emp.id }}</td>
            <td>{{ emp.firstName }}</td>
            <td>{{ emp.lastName }}</td>
            <td>{{ emp.office }}</td>
            <td>{{ emp.createdAt }}</td>
            <td>{{ emp.updatedAt }}</td>
          </tr>
        </tbody>
      </table>
    </div>
    <div v-else>
        <h1>You're not logged.</h1>
    </div>
</template>

<script>
  
  export default {
    computed : {
        logged : function(){ return this.$store.getters.logged},
        employee : function(){ return this.$store.getters.employee}
    },
    created() {
        this.$store.dispatch('employee')
    }
  }
</script>
