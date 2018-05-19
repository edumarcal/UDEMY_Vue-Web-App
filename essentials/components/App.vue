var counter = Vue.component('counter', {
    template: `
        <div>
            <p>Count: {{this.count}}</p>
            <button class="vue-btn" @click="increments">Increments by {{this.addNumber}}</button>
            <button class="vue-btn-warning" @click="decrements">Decrements</button>
        </div>
    `,
    props: {
        addNumber:{
            type: Number,
            default: 1
        }
    },
    data () {
        return {
            count: 0
        }
    },
    methods: {
        increments() {
            this.count += this.addNumber
        },
        decrements() {
            this.count--
        }
    }
});

var app = new Vue({
    el: '#app',
    component: {
        counter
    }
});