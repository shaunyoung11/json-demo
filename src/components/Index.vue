<template>
  <div class="index">
    <v-data-table
      :headers="headers"
      :items="students.info"
      :items-per-page="5"
    ></v-data-table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      students: {
        title: '简单的学生管理系统',
        info: [
          { name: 'aaa', age: 99, phone: '1234567' },
          { name: 'bbb', age: 18, phone: '1235678' },
          { name: 'ccc', age: 20, phone: '1245678' },
          { name: 'ddd', age: 10, phone: '234678' },
          { name: 'eee', age: 74, phone: '1234568' },
          { name: 'fff', age: 18, phone: '12345678' },
          { name: 'ggg', age: 58, phone: '1234678' },
          { name: 'hhh', age: 30, phone: '1235678' }
        ]
      },
      headers: [
        {
          text: 'Name',
          value: 'name'
        },
        {
          text: 'Age',
          value: 'age'
        },
        {
          text: 'Phone',
          value: 'phone'
        }
      ]
    }
  }
}
</script>

<style></style>
