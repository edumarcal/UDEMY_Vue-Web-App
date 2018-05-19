var app = new Vue({
    el: '#app',
    data: {
        count: 0
    },
    methods: {
/*
        alertTime() {
            alert(`The time is ${Date.now().toLocaleString()}`)
        }
*/
        increment() {
            this.count++
        }
    },
/*
    created() {
        this.alertTime()
    },
    mounted() {
        this.alertTime()
    }
*/
    updated() {
        console.log('this.count ' + this.count)
    }
});