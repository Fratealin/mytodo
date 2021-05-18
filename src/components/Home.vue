<template>
  <div class="hello">
    <h1>{{ msg }}</h1>


Name: <input v-model="name"/>
   Task: <input v-model="task"/>
   Urgent (y/n): <input v-model="urgency"/>
   How long it will take: <input v-model="duration"/>
      Location: <input v-model="location"/>

      <button v-on:click="addTask()">Submit</button>
      <button v-on:click="addToList()">Add to list</button>
   <p>{{ name }} {{ task }}</p>
   <p>{{tasks}}</p>
   <table>
   <thead>
        <tr>
            <th>Name</th>
            <th>Task</th>
            <th>Time</th>
            <th>Urgency</th>
            <th>Location</th>
        </tr>
    </thead>
<tbody>
  <tr v-for="line in tasks" :key="line" >
      <td v-for="column in line" :key="column" >{{ column }}
      </td>
    </tr>
</tbody>
</table>

Search:<br>
How long do you have: <input v-model="searchd"/><button v-on:click="searchDuration(searchd)">Search</button>
Where are you: <input v-model="searchl"/><button v-on:click="searchLocation()">Search</button>
<p>{{searchResults}}</p> 

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return {
      name: "Enter name",
      task: "Enter task",
      duration: 15,
      urgency: "n",
      location: "kitchen",
      tasks: [],
      searchResults: []
    }
  },
  methods:{
    addTask: function(){
      this.tasks.push([this.name, this.task, this.duration, this.urgency, this.location]);
    },
    searchDuration(text){
      //var searchResults = [];
      for(var i=0; i <self.tasks.length; i++){
        //if(text<=self.tasks[i][2]){
         // searchResults.push(i);
        //}
        text;
        this.searchResults.push(i);

      }
      //this.searchResults = searchResults;
      //this.searchResults = ["hi"];
    },
    addToList: function(){
      this.$set(this.tasks,1, [this.name, this.task, this.duration, this.urgency, this.location])
            this.$set(this.tasks,2, [this.name, this.task, this.duration, this.urgency, this.location])

    }



  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
table {
  margin: auto;
  width: 25%;
}
</style>
