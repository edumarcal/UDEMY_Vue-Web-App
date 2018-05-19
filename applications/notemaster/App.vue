var app = new Vue({
    el: '#app',
    data: {
        title: 'Notemaster',
        note: {
            title: '',
            text: ''            
        },
        notes: [
            {
                title: 'Visited Havai',
                text: 'I loved the beaches and delicious fresh coconuts',
                date: new Date(Date.now()).toLocaleString()
            }
        ]
    },
    methods: {
        addNote() {
            let { title, text } = this.note 
            this.notes.push({
                title,
                text,
                date: new Date(Date.now()).toLocaleString()
            })
            
            // Updated value
            this.note.title = ''
            this.note.text = ''

        },
        removeNote(index) {
            this.notes.splice(index, 1)
        },
        editNote(_note) {
            this.note.title = _note.title
            this.note.text = _note.text
            this.$refs.title.focus() // Add Focus element title
        }
    }
});