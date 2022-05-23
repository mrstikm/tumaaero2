/* eslint-disable vue/require-prop-types */
/* eslint-disable vue/require-default-prop */
<template>
    <header class="main-header">
        <a href="/">
            <img src="/img/tumaaero-logo.jpg" alt="TůmaAerospace s.r.o.">
        </a>
        <h1>Přítomní pracovníci</h1>
        <span class="timer">{{timestamp}}</span>
    </header>
</template>

<script>
export default {
    data() {
        return {
            timestamp: '',
        }
    },
    created() {
        setInterval(this.getNow, 1000)
    },
    methods: {
        getNow() {
            const today = new Date()
            const date = today.getDate() + '.' +(today.getMonth()+1)+ '.' + today.getFullYear()
            const time = today.getHours() + ":" + (today.getMinutes() < 10 ? '0' + today.getMinutes() : today.getMinutes()) + ":" + (today.getSeconds() < 10 ? '0' + today.getSeconds() : today.getSeconds())
            const dateTime = date +' '+ time
            this.timestamp = dateTime
        },
    },
}
</script>

<style lang="scss" scoped>
.main-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1rem;
  border-radius: 10px;
  background-color: rgba(#FFF, .7);
  box-shadow: 15px 15px 35px rgba(#FFF, .2);
  .timer {
    min-width: 150px;
    text-align: right;
  }
}
h1 {
    font-size: 1.5rem;
}

</style>