<template>
<v-container>
  <v-layout>
    <div class="outerDiv">
  <h1>Recital Registration</h1>
  
  <br>
  
  <form class="form" name="Recital Submission" method="POST" netlify>
    <p>
      <label class="label">Which Recital?</label>
        <br>
        <select class="select" name="Recital">
        <option value="select">- Select One -</option>
        <option value="12/02/18 Monthly Student Recital">12/02/18 Monthly Student Recital</option>
        <option value="02/10/19 Teen Recital">02/10/19 Teen Recital</option>
        <option value="03/10/19 Monthly Student Recital">03/10/19 Monthly Student Recital</option>
        <option value="06/02/19 Spring Festival">06/02/19 Spring Festival</option>
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
      <label class="label">Instrumentation of Piece No. 1 (Include all performers' names)</label>
      <br>
      <input class="inputStyle" type="text" name="instrumentation1" />
    </p>
    <p>
      <label class="label">Instrumentation of Piece No. 2 (Include all performers' names)</label>
      <br>
      <input class="inputStyle" type="text" name="instrumentation2" />
    </p>
    <p>
      <v-btn class="submitBtn" type="submit">Submit</v-btn>
    </p>
    <br>
    <br>
  </form>
  </div>

  </v-layout>
  </v-container>
</template>

<script>

</script>

<style lang="scss" scoped>

.outerDiv {
  margin-top: 4.5rem;
}

.form {
  width: 32rem;
  margin-top: 2rem;
}

.label {
  font-size: 1.1rem;
}

.select {
  border-radius: 100px;
  outline-color: white;
  outline: 2px;
  background-color: rgb(122, 119, 119);
  padding-left: 1rem;
  width: 70%;
}

.inputStyle {
  border: 2px !important;
  border-color: white;
  outline: 1px !important;
  outline-color: white;
  background-color: rgb(122, 119, 119);
  border-radius: 100px;
  padding-left: 1rem;
  width: 70%;
  transition: all .2s;

  &:focus {
    outline: 1px;
    outline-color: white;
    background-color: white;
    color: black;
    padding-left: 1rem;
    width: 80%;
  }
}

.submitBtn {
  margin-top: .8rem;
}

</style>
