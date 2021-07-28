<template>
<div class="grid md:grid-cols-2 gap-4">
    <!--Box1 -->
        <div class="shadow-md bg-blue-100 p-10 text-center rounded">
              <div class="text-2xl mb-4">
        <h3 class="text-3xl text-blue-900 font-bold md-4"><i class="fas fa-virus"></i> Cases
        </h3>
        </div>
        <div class="text-2xl mb-4">
            <span class="font-bold">New:</span>
            {{ numberWithCommas(stats.NewConfirmed)}}
            </div>
            <div class="text-2xl mb-4">
             <span class="font-bold">Total:</span>
            {{ numberWithCommas(stats.TotalConfirmed) }}
        </div>
    </div>
        <!--Box2-->
        <div class="shadow-md bg-red-100 p-10 text-center rounded">
              <div class="text-2xl mb-4">
        <h3 class="text-3xl text-blue-900 font-bold md-4"><i class="fas fa-skull-crossbones"></i> Deaths
        </h3>
        </div>
        <div class="text-2xl mb-4">
            <span class="font-bold">New:</span>
            {{ numberWithCommas(stats.NewDeaths)}}
            </div>
            <div class="text-2xl mb-4">
             <span class="font-bold">Total:</span>
            {{ numberWithCommas(stats.TotalDeaths) }}
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: 'DataBoxes',
    props: ['stats'],
    methods:{
        numberWithCommas(x){
      return x.toString()
          .replace(/\B(?=(\d{3})+(?!\d))/g, ',');
        }
    }
}
</script>

<style>

</style>