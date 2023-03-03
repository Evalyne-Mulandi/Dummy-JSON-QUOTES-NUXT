 <template>
    <main>
        <h1 style=" text-align: center; height: ;  padding:2%;  background-color: aqua; text-decoration: ; font-weight: bold;">Dummy json Quotes</h1>
        
    <ul  v-for="(quote, index) in resources[0]" :key="index">
      <li>
        {{ quote.author }} <br>
        {{ quote.quote }}
      </li>
    </ul>
  
    </main>
 </template>
 
 <script>
 export default {
    name:'resources',
    data(){
        return{
            resources:[]
        }
    },
    mounted(){
    this.fetchAllquotes()
 },

 methods:{
    async fetchAllquotes(){
        const res=await fetch("https://dummyjson.com/quotes")
        const results=await res.json()
        this.resources.push(results.quotes)
        console.log(this.resources);
    }
 }
}
 </script>
 <style>
  
 </style>