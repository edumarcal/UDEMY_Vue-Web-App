var app = new Vue({
    el: '#app',
    data: {
        text: ''
    },
    computed: {
        lowerText() {
            return this.text.toLowerCase()
        }
    }
});