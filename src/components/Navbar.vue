<template>
  <b-navbar type="is-primary">
        <template slot="start">
            <b-navbar-item  href="#">
                Weather App
            </b-navbar-item>
        </template>
    </b-navbar>
</template>

<script>
export default {
  name: 'Navbar',
  props: {
    msg: String
  }
}
</script>

