<template>
<div class="grid md:grid-cols-3 lg:grid-cols-6 gap-4">
    <div class="shadow-md bg-indigo-200 p-10 text-center rounded">
        <h3 class=" text-indigo-900 font-bold mb-4">NewConfirmed</h3>
        <div class="text-2xl mb-4">
            <span class="font-bold">New:</span>
            {{numberWithCommas(state.NewConfirmed)}}
        </div>
    </div>
    <div class="shadow-md bg-indigo-300 p-10 text-center rounded">
        <h3 class=" text-blue-900 font-bold mb-4">TotalConfirmed</h3>
        <div class="text-2xl mb-4">
            <span class="font-bold">Total:</span>
            {{numberWithCommas(state.TotalConfirmed)}}
        </div>
    </div>
    <div class="shadow-md bg-indigo-200 p-10 text-center rounded">
        <h3 class="text-blue-900 font-bold mb-4">NewDeaths</h3>
        <div class="text-2xl mb-4">
            <span class="font-bold">Death:</span>
            {{numberWithCommas(state.NewDeaths)}}
        </div>
    </div>
    <div class="shadow-md bg-indigo-300 p-10 text-center rounded">
        <h3 class=" text-blue-900 font-bold mb-4">TotalDeaths</h3>
        <div class="text-2xl mb-4">
            <span class="font-bold">Death:</span>
            {{numberWithCommas(state.TotalDeaths)}}
        </div>
    </div>
    <div class="shadow-md bg-indigo-200 p-10 text-center rounded">
        <h3 class=" text-blue-900 font-bold mb-4">NewRecovered</h3>
        <div class="text-2xl mb-4">
            <span class="font-bold">Recover:</span>
            {{numberWithCommas(state.NewRecovered)}}
        </div>
    </div>
    <div class="shadow-md bg-indigo-300 p-10 text-center rounded">
        <h3 class=" text-blue-900 font-bold mb-4">TotalRecovered</h3>
        <div class="text-2xl mb-4">
            <span class="font-bold">Recover:</span>
            {{numberWithCommas(state.TotalRecovered)}}
        </div>
    </div>
</div>
</template>

<script>
export default {
    name:'DataBoxes',
    props:["state"],
    methods:{
        numberWithCommas(x){
            return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',');
        }
    }

}
</script>

<style>

</style>