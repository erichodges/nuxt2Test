<template>
<v-container>
  <v-layout>
  <!-- <h3 class="form">This form is under construction and should be ready relatively soon</h3> -->
  <br>
  
  <form class="form" name="contact" method="POST" netlify>
    <p>
      <label>Your Name: <input type="text" name="name" /></label>   
    </p>
    <p>
      <label>Your Email: <input type="email" name="email" /></label>
    </p>
    <p>
      <label for="">Recital</label>
      <v-select
        :items="recitals"
        label="Please Select"
        outline
      >
      </v-select>
      <br>

      <label>Your Role:</label>
      <select name="role">
        <option value="leader">Leader</option>
        <option value="follower">Follower</option>
      </select>
    </p>
    <p>
      <label>Message: <textarea name="message"></textarea></label>
    </p>
    <p>
      <v-btn type="submit">Send</v-btn>
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
  margin-top: 4.5rem;
}



</style>
