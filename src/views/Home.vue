<template>
  <div class="home">
    <main v-if="!loading">
      Show Data
    </main>
    <main v-else class="flex flex-col align-center justify-center text-center">
      <div class="text-gray-500 text-3xl mt-10 mb-6">
        Fetching Data
      </div>

    </main>
  </div>
</template>

<script>
//import axios from 'axios'
export default {
  name: "Home",
  data(){
    return{
      state:{},
      title:'Global',
      dateDate:'',
      loading:true,
      countries:[]

    }
  },
  async mounted(){
    const data = await this.fetchingDataFromApi()
    this.dateDate=data.Date;
    this.state=data.Global;
    this.countries=data.countries;
    this.loading =false
  },
  methods:{
    async fetchingDataFromApi(){
      const res = await fetch('https://api.covid19api.com/summary')
      const data = await res.json()
      return data
    }
  }
  
};
</script>
