var app = new Vue({
    el: '#app',
    data: {
      colors: [
          {
            text: 'red',
            primary: true
        }, {
          text: 'blue',
          primary: false  
        }, {
            text: 'green',
            primary: true
        }, {
            text: 'yellow',
            primary: true
        }, {
            text: 'orange',
            primary: false
        }]
      /*colors: ['red', 'blue', 'green', 'yellow', 'orange']*/
    }
});