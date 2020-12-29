<template>
  <b-modal :active.sync="check" has-modal-card>
  <div class="modal-card" style="width: 100">
        <header class="modal-card-head">
            <p class="modal-card-title">Weather details of {{data.name}}</p>
        </header>
        <section class="modal-card-body">
            <span><b>Temperature : </b> {{`${(data.main.temp - 273.15).toFixed(2)}&#176; C`}}</span><hr>
            <span><b>Humidity : </b> {{`${(data.main.humidity - 273.15).toFixed(2)}`}}</span><hr>
            <span><b>Description : </b> {{data.weather[0].description}}</span>
        </section>
        <footer class="modal-card-foot">
            <button class="button" type="button" @click="$emit('close')">Close</button>
        </footer>
    </div>
  </b-modal>
</template>

<script>
export default {
    props : {
        check : Boolean,
        data : Object
    }
}
</script>

<style>

</style>