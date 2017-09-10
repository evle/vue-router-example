<template>
    <div class="weather">
        <p>城市: {{city}}</p>
        <p>天气: {{condition}}</p>
        <p>温度: {{temperature}}度</p>
    </div>
</template>

<script>

import axios from 'axios'

export default {
    name: 'Weather',
    data() {
        return {
            weather: {},
            city: {},
            temperature: {},
            condition: {}
        }
    },

    created() {
        this.fetchData()
    },

    watch: {
        '$route': 'fetchData'
    },

    methods: {
        fetchData() {
            axios.get('https://weixin.jirengu.com/weather/now?cityid=' + this.$route.params.id)
                .then((resp) => {
                    this.weather = resp.data.weather[0]
                    this.city = this.weather.city_name
                    this.temperature = this.weather.now.temperature
                    this.condition = this.weather.now.text

                    console.log(resp)
                })
                .catch((err) => {
                    console.log(err)
                })
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
