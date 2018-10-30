<template>
<v-container>
  <v-layout>
  <!-- <h3 class="form">This form is under construction and should be ready relatively soon</h3> -->
  <br>
  
  <form class="form" name="contact" method="POST" netlify>
    <p>
      <label class="label">Which Recital?</label>
        <br>
        <select class="select" name="Recital">
        <option value="select">- Select One -</option>
        <option value="Recital1">November 11 - Monthly Student Recital - Deadline: Nov. 6</option>
        <option value="Recital2">February 10 - Teen Recial - Ceadline: Feb. 3</option>
        <option value="Recital3">March 10 - Monthly Student Recital - Deadline: Mar. 3</option>
        <option value="Recital4">April 15 - Adult Recital - Deadline: Apr. 10</option>
        <option value="Recital5">Date TBA - Composition & Improvisation Celbration - Deadline: TBA</option>
        <option value="Recital6">June 3 - Spring Festival - Deadline: May 26</option>
      </select>
    </p>
    <p>
      <label class="label">Teacher Name</label>
      <br>
      <input class="inputStyle" type="text" name="teacherName" />
    </p>
    <p>
      <label class="label">Student Name</label>
      <br>
      <input class="inputStyle" type="text" name="studentName" />
    </p>
    <p>
      <label class="label">Student Age</label>
      <br>
      <input class="inputStyle" type="text" name="age" />
    </p>
    <p>
      <label class="label">Student Level</label>
      <br>
      <input class="inputStyle" type="text" name="level" />
    </p>
    <p>
      <label class="label">Piece No. 1 (Include composer)</label>
      <br>
      <input class="inputStyle" type="text" name="piece1" />
    </p>
    <p>
      <label class="label">Piece No. 2 (Include composer)</label>
      <br>
      <input class="inputStyle" type="text" name="piece2" />
    </p>
    <p>
      <label class="label">Performance Length (Both Pieces)</label>
      <br>
      <input  class="inputStyle" type="text" name="length" />
    </p>
    <p>
      <label class="label">Is the first piece a piano duet?</label>
      <br>
      <select class="select" name="duet1" outline>
        <option value="select">- Select One -</option>
        <option value="Yes">Yes</option>
        <option value="No">No</option>
      </select>
    </p>
    <p>
      <label class="label">If so, please list the accompanist</label>
      <br>
      <input class="inputStyle" type="text" name="accompanist1" />
    </p>
    <p>
      <label class="label">Is the second piece a piano duet?</label>
      <br>
      <select class="select" name="duet1" outline>
        <option value="select">- Select One -</option>
        <option value="Yes">Yes</option>
        <option value="No">No</option>
      </select>
    </p>
    <p>
      <label class="label">If so, please list the accompanist</label>
      <br>
      <input class="inputStyle" type="text" name="accompanist2" />
    </p>
    <p>
      <label class="label">If student is not a pianist, list the instrument</label>
      <br>
      <input class="inputStyle" type="text" name="instrument" />
    </p>
    <p>
      <label class="label">Instrumentation of Piece No. 1 (Include all performers' names"</label>
      <br>
      <input class="inputStyle" type="text" name="instrumentation1" />
    </p>
    <p>
      <label class="label">Instrumentation of Piece No. 2 (Include all performers' names"</label>
      <br>
      <input class="inputStyle" type="text" name="instrumentation2" />
    </p>
    <p>
      <v-btn type="submit">Submit</v-btn>
    </p>
  </form>


  </v-layout>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      recitals: ['1', '2', '3']
    })
  }
</script>

<style lang="scss" scoped>
.form {
  width: 32rem;
  margin-top: 6.5rem;
}

.label {
  font-size: 1.1rem;
}

.select {
  outline-color: white;
  outline: 2px;
  background-color: rgb(122, 119, 119);
  padding-left: 1rem;

}

.inputStyle {
  border: 2px !important;
  border-color: white;
  outline: 1px !important;
  outline-color: white;
  background-color: rgb(122, 119, 119);
  border-radius: 100px;
  padding-left: 1rem;
  width: 60%;
  transition: all .2s;

  &:focus {
    outline: 1px;
    outline-color: white;
    background-color: white;
    color: black;
    padding-left: 1rem;
    width: 70%;
  }
}

</style>
