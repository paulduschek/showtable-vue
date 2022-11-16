<template>
<div v-if="error">
    <h2>Error: {{ error }}</h2>
</div>
<div v-if="loading">
  <h2>Loading data...</h2>
</div>
<h2>Posts</h2>
<table id = "userdata">
  <thead>
    <tr>
      <th>UserID</th>
      <th>Index</th>
      <th>Title</th>
      <th>Body</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="item,index in data">
      <!--<td v-if = "!((item.id-1) % 10)">{{ item.userId }}</td>-->
      <td v-if="(index - 1) >= 0 && data[index - 1].userId != item.userId">
              {{ item.userId }}
      </td>
      <td v-else-if="index - 1 < 0">
              {{ item.userId }}
      </td>
      <td v-else> </td>
      <td>{{ item.id }} </td>
      <td>{{ item.title}}</td>
      <td>{{ item.body}}</td>
    </tr>
  </tbody>
</table>
</template>

<script>
import {useFetch} from '../composeables/UseFetch.js';

export default {
  setup(){
    const{data, error, loading} = useFetch("https://jsonplaceholder.typicode.com/posts", 
    {}
  );

  return {
      data,
      error,
      loading,
    };
  },
}
</script>

<style scoped>
span {
  display: inline-block;
  width: 200px;
}
ul {
  list-style-type: square;
}

#userdata{
  font-family: Arial, Helvetica, sans-serif;
  border-collapse: collapse;
  width: 100%;
  empty-cells: show;
}
#userdata td, #customers th {
  border: 1px solid #ddd;
  padding: 8px;
}

#userdata tr:nth-child(even){background-color: #f2f2f2;}

#userdata tr:hover {background-color: #ddd;}

#userdata th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: left;
  background-color: #04AA6D;
  color: white;
}
</style>