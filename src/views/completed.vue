<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
      </v-col>

      <v-col
          class="mb-6"
          cols="12"
      >
        <v-row justify="center">

          <div class="app">
            <v-card outline width="650">
              <v-card-title>todo-list(Completed)</v-card-title>
              <v-card-text>
                <v-text-field
                    outlined
                    tile
                    v-model="message"
                    label="ここに書き込む"
                >
                </v-text-field>

              </v-card-text>
              <v-card-actions>

                <v-btn outlined rounded color="primary" v-on:click="add">追加<v-icon>mdi-plus</v-icon></v-btn>

                <v-layout justify-end>
                  <v-btn outlined rounded justify="right" color="error" v-on:click="delll2">全消去<v-icon>mdi-trash-can-outline</v-icon></v-btn>
                </v-layout>

              </v-card-actions>

              <v-divider></v-divider>

              <v-col
                  class="mb-5"
                  cols="12"
              >
                <v-row justify="center">
                  <div>
                    <ol>
                      <li v-for="(todo,index) in todos" :key = "todo">
                        <input type="checkbox" v-on:click="check(index)"> {{todo}}<v-btn outlined color="defalt" v-on:click="delpin(index)"><v-icon>mdi-backspace</v-icon></v-btn>
                      </li>
                    </ol>
                  </div>
                </v-row>
              </v-col>

            </v-card>
          </div>


        </v-row>
      </v-col>

    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'HelloWorld',

  data: () => ({
    message: "",
    todos: []
  }),
  watch:{
    $route(){

    }
  },
  routes: [
    {path:'/',props: true},
    {path:'/About',props: true}
  ],
  methods: {
    add: function(){
      this.todos.push(this.message)
    },
    delll2: function(){
      this.todos.splice(0,this.todos.length)
    },
    delpin: function(index){
      this.todos.splice(index,1)
    },
    check: function (index){
      this.todos.splice(index,1)
    }
  }
}
</script>

