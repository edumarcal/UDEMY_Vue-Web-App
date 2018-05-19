var app = new Vue({
    el: '#app',
    data: {
        secretNum: Math.floor(Math.random() * 100) + 1
    },
    methods: {
        reveal() {
            alert(`Here's the secret number: ${this.secretNum}`)
        }
    }
});