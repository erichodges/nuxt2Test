<template>
  <v-container class="media-contianer">
    <div class="gallery">

      <figure class="gallery__item gallery__item--1"><img src="/images/media/1.jpg" alt="gallery Image 1" class="gallery__img"></figure>
      <figure class="gallery__item gallery__item--2"><img src="/images/media/2.jpg" alt="gallery Image 2" class="gallery__img"></figure>
      <figure class="gallery__item gallery__item--3"><img src="/images/media/3.jpg" alt="gallery Image 3" class="gallery__img"></figure>
      <figure class="gallery__item gallery__item--4"><img src="/images/media/4.jpg" alt="gallery Image 4" class="gallery__img"></figure>
      <figure class="gallery__item gallery__item--5"><img src="/images/media/5.jpg" alt="gallery Image 5" class="gallery__img"></figure>
      <figure class="gallery__item gallery__item--6"><img src="/images/media/6.jpg" alt="gallery Image 6" class="gallery__img"></figure>
      <figure class="gallery__item gallery__item--7"><img src="/images/media/7.jpg" alt="gallery Image 7" class="gallery__img"></figure>
      <figure class="gallery__item gallery__item--8"><img src="/images/media/8.jpg" alt="gallery Image 8" class="gallery__img"></figure>
      <figure class="gallery__item gallery__item--9"><img src="/images/media/9.jpg" alt="gallery Image 9" class="gallery__img"></figure>
      <figure class="gallery__item gallery__item--10"><img src="/images/media/10.jpg" alt="gallery Image 10" class="gallery__img"></figure>
      <figure class="gallery__item gallery__item--11"><img src="/images/media/11.jpg" alt="gallery Image 11" class="gallery__img"></figure>
      <figure class="gallery__item gallery__item--12"><img src="/images/media/12.jpg" alt="gallery Image 12" class="gallery__img"></figure>
      <figure class="gallery__item gallery__item--13"><img src="/images/media/13.jpg" alt="gallery Image 13" class="gallery__img"></figure>  

    </div>
    <br>
    <br>
    <br>
    <br>
  </v-container>
</template>

<script>
export default {
  
}
</script>

<style lang="scss">

.media-contianer {
  margin-top: 5rem;
}

.gallery {
  
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250, 1fr));
  // grid-template-rows: repeat(250px 150px);
  grid-gap: 1rem;
  // padding: 1.5rem;

  

  &__img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    // display: block;
  }

}


</style>
