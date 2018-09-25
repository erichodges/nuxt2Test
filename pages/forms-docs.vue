<template>
<v-container>
  <v-layout>
  <v-form ref="form" class="form" v-model="valid" lazy-validation>
    <v-select
      v-model="select"
      :items="itemsRecital"
      :rules="[v => !!v || 'Item is required']"
      label="Which Recital?"
      required
    ></v-select>
    <v-text-field
      v-model="name"
      :rules="nameRules"
      :counter="10"
      label="Teacher Name"
      required
    ></v-text-field>
    <v-text-field
      v-model="name"
      :rules="nameRules"
      :counter="10"
      label="Student Name"
      required
    ></v-text-field>
    <v-text-field
      v-model="name"
      :rules="nameRules"
      :counter="10"
      label="Student Age"
      required
    ></v-text-field>
    <v-text-field
      v-model="name"
      :rules="nameRules"
      :counter="10"
      label="Student Level"
      required
    ></v-text-field>
    <v-text-field
      v-model="name"
      :rules="nameRules"
      :counter="10"
      label="Piece No. 1 (Include composer)"
      required
    ></v-text-field>
    <v-text-field
      v-model="name"
      :rules="nameRules"
      :counter="10"
      label="Piece No. 2 (Include composer)"
      required
    ></v-text-field>
    <v-text-field
      v-model="name"
      :rules="nameRules"
      :counter="10"
      label="Total Length (Both Pieces)"
      required
    ></v-text-field>
    <v-select
      v-model="select"
      :items="itemsP1"
      label="Is the first piece a piano duet?"      
    ></v-select>
    <v-text-field
      v-model="name"
      :rules="nameRules"
      :counter="10"
      label="If so, please list the accompanist"
      required
    ></v-text-field>
    <v-select
      v-model="select"
      :items="itemsP2"
      label="Is the second piece a piano duet?"
    ></v-select>
    <v-text-field
      v-model="name"
      :rules="nameRules"
      :counter="10"
      label="If so, please list the accompanist"
      required
    ></v-text-field>
    <v-text-field
      v-model="name"
      :rules="nameRules"
      :counter="10"
      label="If student is not a pianist, list the instrument"      
    ></v-text-field>
    <v-text-field
      v-model="name"
      :rules="nameRules"
      :counter="10"
      label="Instrumentation of Piece No. 1 (Include all performers' names"
      required
    ></v-text-field>
    <v-text-field
      v-model="name"
      :rules="nameRules"
      :counter="10"
      label="Instrumentation of Piece No. 2 (Include all performers' names"
      required
    ></v-text-field>
    <br>
    <v-btn
      :disabled="!valid"
      @click="submit"
    >
      submit
    </v-btn>
    <v-btn @click="clear">clear</v-btn>
  </v-form>
  </v-layout>
  </v-container>
</template>

<script>
  import axios from 'axios'

  export default {
    data: () => ({
      valid: true,
      name: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => (v && v.length <= 10) || 'Name must be less than 10 characters'
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid'
      ],
      select: null,
      itemsRecital: [
        'November 11 - Monthly Student Recital - Deadline: Nov. 6',
        'February 10 - Teen Recial - Ceadline: Feb. 3',
        'March 10 - Monthly Student Recital - Deadline: Mar. 3',
        'April 15 - Adult Recital - Deadline: Apr. 10',
        'Date TBA - Composition & Improvisation Celbration - Deadline: TBA',
        'June 3 - Spring Festival - Deadline: May 26'
      ],
      itemsP1: [
        'Yes',
        'No'
      ],
      itemsP2: [
        'Yes',
        'No'
      ],
      items: [
        'Item 1',
        'Item 2',
        'Item 3',
        'Item 4'
      ]
    }),

    methods: {
      submit () {
        if (this.$refs.form.validate()) {
          // Native form submission is not yet supported
          axios.post('/api/submit', {
            name: this.name,
            email: this.email,
            select: this.select,
            checkbox: this.checkbox
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
  margin-top: 3rem;
}
</style>
