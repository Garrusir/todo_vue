<template>
     
     

  <div class="row1">
    <div>
     <input type="text" v-model="item">
   <!--   {{item}} -->
    <input type="submit" value="Add task" @click="add()">
    </div>
    <div class="row">
    

    <div class="col-3">
      <h3>Backlog</h3>
      <draggable class="list-group" :list="list2" group="people" @change="log">
        <div
          class="list-group-item"
          v-for="(element, index) in list2"
          :key="element.name"
        >
          {{ element.name }} {{ index }}
          <a href="#" v-on:click="remove(index, list2)">Удалить</a>
        </div>
      </draggable>
    </div>

<div class="col-3">
      <h3>In progress</h3>
      <draggable class="list-group" :list="list1" group="people" @change="log">
        <div
          class="list-group-item"
          v-for="(element, index) in list1"
          :key="element.name"
        >
          {{ element.name }} {{ index }}
          <a href="#" v-on:click="remove(index, list1)">Удалить</a>
          <div class="start_data">{{element.start_data}}</div>
        </div>
      </draggable>
    </div>

    <div class="col-3">
      <h3>Done</h3>
      <draggable class="list-group" :list="list3" group="people" @change="log">
        <div
          class="list-group-item"
          v-for="(element, index) in list3"
          :key="element.name"
        >
          {{ element.name }} {{ index }}
          <a href="#" v-on:click="remove(index, list3)">Удалить</a>
          <div class="start_data">{{element.start_data}}</div>
          <div class="finish_data">{{element.finish_data}}</div>
        </div>
      </draggable>
    </div>

<!--     <rawDisplayer class="col-3" :value="list1" title="List 1" />

    <rawDisplayer class="col-3" :value="list2" title="List 2" />
    <rawDisplayer class="col-3" :value="list3" title="List 3" /> -->
  </div>
</div>
</template>
<script>
import draggable from 'vuedraggable'
export default {
  name: "test",
  display: "Two Lists",
  order: 1,
  components: {
    draggable
  },
  data() {
    return {
      item: "",
      list1: [
        { name: "Задача", id: 1, start_data: 0, finish_data: 0 },
        
      ],
      list2: [
        { name: "Еще одна задача", id: 2, start_data: 0, finish_data: 0 },
       
      ],
      list3: [
        { name: "Еще задача", id: 3, start_data: 0, finish_data: 0 },
        
      ]
    };
  },
  methods: {
    add: function(){
      console.log(this.item);
      let today = new Date();
      this.list1.push({
        name: this.item,
        start_data: today.getHours() + ":" + today.getMinutes() + ":" + today.getSeconds()
      });
    },
    remove: function(index, list){
        console.log(index);
            console.log(list);
            list.splice(index,1);
    },
    // add: function() {
    //   this.list.push({ name: "Juan" });
    // },
    // replace: function() {
    //   this.list = [{ name: "Edgard" }];
    // },
    // clone: function(el) {
    //   return {
    //     name: el.name + " cloned"
    //   };
    // },
    log: function(evt) {
      window.console.log(evt);
    }
  }
};
</script>

<style>
  .row {
    display: flex;
    flex-flow: row wrap;
    justify-content: space-around;
    margin: 20px;
  }
  .col-3 {
    min-width: 300px;
    padding: 10px 10px;
    margin: 20px;
    background-color: #f7f7f7;
    box-shadow: 0px 2px 2px 0 rgba(0,0,0, .15);
  }
  .list-group-item {

    padding: 10px 15px;
    margin: 5px 0;
    cursor: pointer;
    background-color: #d2d2d2;
    box-shadow: 0px 2px 2px 0 rgba(0,0,0, .15);

  }
</style>