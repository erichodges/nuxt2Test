<template>
  <v-container class="scholar-header">
    <div class="scholarDiv">
    <h1>Discovery Scholarship</h1>
    <br>
    <figure class="ds1">
      <img width="230px" src="/images/scholarship/ds1.jpg" alt="">
    </figure>
    <p>
      In 1984 the Marin branch of the Music Teachers’ Association of California (MTAC) founded the Discovery scholarship program for the purpose of providing private music lessons to children from low-income families.  Please click the button above to download a copy of the current application form in English or Spanish.
    </p>
    <figure class="ds2">
      <img height="230px" src="/images/scholarship/ds2.jpg" alt="">
    </figure>
    <br>
    <br>
    <br>
    <p>
      Lessons are offered in piano, strings, winds and voice. As long as financial need guidelines are met and the student progresses satisfactorily, the Scholarship is guaranteed to continue through senior year in high school.
    </p>
    <figure class="ds3">
      <img height="230px" src="/images/scholarship/ds3.jpg" alt="">
    </figure>
    <p>
      Graduates of Discovery have attended colleges such as Harvard, Duke, George Washington, Columbia, Northwestern, Columbia, Wharton School of Business and Berkeley.  Post-college, our students have gone on to careers as inventors, business owners, entrepreneurs, classroom instructors, private teachers, professional musicians and film composers, among others.
    </p>
    <figure class="ds4">
      <img height="230px" src="/images/scholarship/ds4.jpg" alt="">
    </figure>
    <p>
      Discovery is financed by individual bequests, grants from local non-profits and by many local Marin county residents who believe that music can open doorways into a world not generally available to low-income students.
    </p>
    <!-- <figure class="ds5">
      <img height="230px" src="/images/scholarship/ds5.jpg" alt="">
    </figure> -->
  </div>
    <div class="appsDiv">
      <br>

      <h3>Application Download Links</h3>
      <br>
      <v-icon>cloud_download</v-icon>&nbsp;
      <a class="link" href="https://drive.google.com/uc?export=download&id=1YxW-Sy4LAB_8ms9Zvf9CGup5Krljgz01">2018-19 Discovery Application</a>
      <br>
      <v-icon>cloud_download</v-icon>&nbsp;
      <a class="link" href="https://drive.google.com/uc?export=download&id=1KWvce8apyOZ0vVdqHM-8PATJTigLt0_G">Aplicación de descubrimiento 2018-19</a>
    </div>
  </v-container>
</template>


<script>
export default {};
</script>

<style lang="scss">
.scholar-header {
  margin-top: 4rem;
  height: 100vh;
}

.scholarDiv {
  overflow: hidden;
}

.ds1 {
  float: right;
  margin-left: 0.5rem;
  margin-top: 0;
  margin-bottom: 0;
}
.ds2 {
  float: left;
  margin: 0.5rem;
  margin-left: 0;
  margin-top: 0;
}
.ds3 {
  float: right;
  margin-right: 0;
  margin-left: 0.5rem;
}
.ds4 {
  float: left;
  margin: 0.5rem;
  margin-left: 0;
}
.ds5 {
  float: left;
  margin: 0.5rem;
  margin-left: 2rem;
}

.appsDiv {
  clear: both;
}
.dlLinks {
  background-color: blue;
}

.link {
  text-decoration: none !important;
  color: white;
  margin-left: 0;
}
</style>
