<template>
    <div>
        <div>
            
            <h3 v-if="errorMSG">{{errorMSG}}</h3>
            <h3>Count: {{ count }}</h3>
            <div v-for="(entries,index) in posts" :key="entries.index">
                <h3>{{index +1}}</h3>
                <p> API: {{entries.API}}<br>Link: {{entries.Link}}<br> Category: {{entries.Category}}</p>
                <hr>
            </div>
        </div>
    
    </div>
    </template>
    
    <script>
    import axios from 'axios'
    export default {
        name: 'Post-list',
        data() {
            return {
                posts: [],
                count: 0,
                errorMSG: ''
            };
        },
        mounted() {
            this.getPosts();
          },
        methods: {
            getPosts() {
                axios
                    .get('https://api.publicapis.org/entries')
                    .then((response) => {
                        console.log(response.data)
                        this.count = response.data.count
                        this.posts = response.data.entries
                    })
                    .catch((error) => {
                        console.log(error)
                        this.errorMSG = 'Error retrieving data'
                    })
            },
          
          }
        }
    
    
    </script>
      
      <style scoped />