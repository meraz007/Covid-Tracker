<template>
  <div class="home">
    <main v-if="!loading">
      <DateAndTime :text="title" :dataDate="dataDate"/>
      <DataBoxes :state="state" />
      <CountrySelect :countries="countries" />
    </main>
    <main v-else class="flex flex-col align-center justify-center text-center">
      <div class="text-gray-500 text-3xl mt-10 mb-6">
        Fetching Data
      </div>

    </main>
  </div>
</template>

<script>
import DateAndTime from '../components/DateAndTime.vue'
import DataBoxes from '../components/dataBoxes.vue'
import CountrySelect from '../components/CountrySelect.vue'
export default {
  name: "Home",
  components:{
    DateAndTime,
    DataBoxes,
    CountrySelect
  },
  data(){
    return{
      state:{},
      title:'Global',
      dataDate:'',
      loading:true,
      countries:[]

    }
  },
  async mounted(){
    const data = await this.fetchingDataFromApi()
    this.dataDate=data.Date;
    this.state=data.Global;
    this.countries=data.Countries;
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
