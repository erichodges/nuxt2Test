<template>
<v-container>
  <v-layout>    
  <v-form ref="form" class="form" v-model="valid" lazy-validation action="" name="Recital" method="post" netlify>
    <input type="hidden" name="form-name" value="Recital" />
    <v-select
      name="recitalItems"
      v-model="select"
      :items="recital"
      label="Which Recital?"
      required
    ></v-select>
    <v-text-field
      name="teacher name"
      v-model="teacherName"
      :rules="nameRules"
      :counter="30"
      label="Teacher Name"
      
    ></v-text-field>
    <v-text-field
      v-model="studentName"
      :rules="nameRules"
      :counter="30"
      label="Student Name"
      
    ></v-text-field>
    <v-text-field
      v-model="age"
      :rules="nameRules"
      :counter="10"
      label="Student Age"
      
    ></v-text-field>
    <v-text-field
      v-model="level"
      :rules="nameRules"
      :counter="20"
      label="Student Level"
      
    ></v-text-field>
    <v-text-field
      v-model="piece_1"
      :rules="nameRules"
      :counter="30"
      label="Piece No. 1 (Include composer)"
      required
    ></v-text-field>
    <v-text-field
      v-model="piece_2"
      :rules="nameRules"
      :counter="30"
      label="Piece No. 2 (Include composer)"
      required
    ></v-text-field>
    <v-text-field
      v-model="length"
      :rules="nameRules"
      :counter="20"
      label="Total Length (Both Pieces)"
      required
    ></v-text-field>
    <v-select
      v-model="selectPiece_1"
      :items="itemsSelectPiece_1"
      label="Is the first piece a piano duet?"      
    ></v-select>
    <v-text-field
      v-model="accompanist_1"
      :counter="30"
      label="If so, please list the accompanist"
      required
    ></v-text-field>
    <v-select
      v-model="selectPiece_2"
      :items="itemsSelectPiece_2"
      label="Is the second piece a piano duet?"
    ></v-select>
    <v-text-field
      v-model="accompanist_2"
      :counter="30"
      label="If so, please list the accompanist"
      required
    ></v-text-field>
    <v-text-field
      v-model="instrument"
      :counter="30"
      label="If student is not a pianist, list the instrument"      
    ></v-text-field>
    <v-text-field
      v-model="instrumentation_1"
      :rules="nameRules"
      :counter="100"
      label="Instrumentation of Piece No. 1 (Include all performers' names"
      required
    ></v-text-field>
    <v-text-field
      v-model="instrumentation_2"
      :rules="nameRules"
      :counter="100"
      label="Instrumentation of Piece No. 2 (Include all performers' names"
      required
    ></v-text-field>
    <br>
    <v-btn type="submit" value="send"
      :disabled="!valid"
      @click="submit"
    >
      Submit
    </v-btn>
    <v-btn @click="clear">Reset</v-btn>
  </v-form>
  </v-layout>
  </v-container>
</template>

<script>
  import axios from 'axios'

  export default {
    data: () => ({
      valid: true,
      recital: null,
      items: [
        'November 11 - Monthly Student Recital - Deadline: Nov. 6',
        'February 10 - Teen Recial - Ceadline: Feb. 3',
        'March 10 - Monthly Student Recital - Deadline: Mar. 3',
        'April 15 - Adult Recital - Deadline: Apr. 10',
        'Date TBA - Composition & Improvisation Celbration - Deadline: TBA',
        'June 3 - Spring Festival - Deadline: May 26'
      ],
      teacherName: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => (v && v.length <= 30) || 'Name must be less than 30 characters'
      ],
      studentName: '',
      age: '',
      level: '',
      piece_1: '',
      piece_2: '',
      length: '',
      itemsSelectPiece_1: null,
      items: [
        'Yes',
        'No'
      ],
      accompanist_1: '',
      itemsSelectPiece_2: null,
      items: [
        'Yes',
        'No'
      ],
      accompanist_2: '',
      instrument: '',
      instrumentation_1: '',
      instrumentation_2: ''
    }),

    methods: {
      submit () {
        if (this.$refs.form.validate()) {
          // Native form submission is not yet supported
          axios.post('/api/submit', {
            recital: this.recital,
            teacherName: this.teacherName,
            studentName: this.studentName,
            age: this.age,
            level: this.level,
            piece_1: this.piece_1,
            piece_2: this.piece_2,
            length: this.length,
            itemsSelectPiece_1: this.itemsSelectPiece_1,
            accompanist_1: this.accompanist_1,
            itemsSelectPiece_2: this.itemsSelectPiece_2,
            accompanist_2: this.accompanist_2,
            instrument: this.instrument,
            instrumentation_1: this.instrumentation_1,
            instrumentation_2: this.instrumentation_2
          })
        }
      },
      clear () {
        this.$refs.form.reset()
      }
    }
  }
</script>

<style>
.form {
  width: 32rem;
  margin-top: 6.5rem;
}
</style>
