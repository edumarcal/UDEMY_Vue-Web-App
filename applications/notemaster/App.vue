var app = new Vue({
  el: "#app",
  data: {
    title: "Notemaster",
    note: {
      title: "",
      text: "",
      collor: ""
    },
    notes: [
      {
        title: "Visited Havai",
        text: "I loved the beaches and delicious fresh coconuts",
        date: new Date(Date.now()).toLocaleString()
      }
    ],
    collors: [
      "bg-primary",
      "bg-secondary",
      "bg-success",
      "bg-danger",
      "bg-warning",
      "bg-info",
      "bg-light",
      "bg-dark",
      "bg-white"
    ]
  },
  methods: {
    addNote() {
      let { title, text, collor } = this.note;
      this.notes.push({
        title,
        text,
        collor,
        textColor: this.changeFgColor(collor),
        date: new Date(Date.now()).toLocaleString()
      });

      // Updated values
      this.note.title = "";
      this.note.text = "";
      this.note.collor = "";
      this.$refs.collor.className = "form-control";
    },
    removeNote(index, event) {
      this.notes.splice(index, 1);
      event.stopPropagation();
    },
    editNote(_note) {
      this.note.title = _note.title;
      this.note.text = _note.text;
      this.note.collor = _note.collor;
      this.$refs.collor.className = "form-control " + _note.collor;
      this.$refs.title.focus(); // Add Focus element title
    },
    changeBgCollor(_collor) {
      this.note.collor = _collor;
      this.$refs.collor.className = "form-control " + _collor;
    },
    changeFgColor(collor) {
      switch (collor) {
        case this.collors[0]:
        case this.collors[1]:
        case this.collors[2]:
        case this.collors[4]:
        case this.collors[6]:
        case this.collors[8]:
          return "text-white";
        default:
          return "text-dark";
      }
    }
  }
});
