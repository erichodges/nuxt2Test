<template>
  <v-container class="heading">
    <h1>Highly Qualified and Experienced Music Teachers in Marin</h1>
    <br>
    <p>
      MTAC Marin is one of more than 67 self-governing branches that are affiliated with the Music Teachers' Association of California. We are a local professional organization of highly qualified and experienced music teachers. We live in your neighborhood and we are dedicated to excellence in our teaching and to fostering a life-long love of music in our students. 
    </p>
    <p>
      We offer lessons to students of all ages in piano, organ, harpsichord, violin, viola, cello, flute, clarinet, saxophone, voice, conducting, music theory, composition, harp and accordion.
    </p>
    <p>
      We sponsor the Certificate of Merit® (CM), an evaluation program that was originally created and developed by the Music Teachers' Association of California in 1933. The program provides a standard of curriculum that requires students to strive for focused musical excellence in performance, technique, ear training, sight reading/singing and music theory. Outstanding young musicians are given the opportunity to appear on State Convention programs.
    </p>
    <p>
      Our yearly musical events and programs include:
    </p>
      <ul>
        <li>Monthly Student Recitals</li>
        <li>Teen Recital</li>
        <li>Adult Recital</li>
        <li>CM Honors Recital</li>
        <li>Spring Festival</li>
        <li>Composers Today & Improvisation Celebration</li>
        <li>Margaret B. Davis Memorial Piano Competition</li>
        <li>VOCE Competition and Young Artists Composers Guild</li>    
      </ul>
      <br>
          <h2>Certificate of Merit</h2>
      <br>
      <p>
        We sponsor the music study program, Certificate of Merit® (CM), an evaluation program that was originally created and developed by the Music Teachers' Association of California in 1933. The program provides a standard of curriculum that requires students to strive for focused musical excellence in performance, technique, ear training, sight reading/singing, and music theory. Outstanding young musicians are given the opportunity to appear on State Convention programs.
      </p>
      <br>
      <h2>Margaret Bean Davis Memorial Piano Competition</h2>
      <br>
      <p>
        Our performance competition is named in honor of Margaret Bean Davis, a wonderful musician and composer who was also a long-time supporter of music in Marin County.   Each year talented young pianists compete before three distinguished pianists in six levels:  Intermediate A, B, C and D and Advanced A and B.  The winners then perform at an annual Winners' Recital in the late spring.
      </p>

      <p>
        If you are a teacher who is interested in joining MTAC, please contact our Membership Secretary, Katherine Butler, at mtacmarinmembership [at] gmail.com
      </p> 
      <br>
      <h3>Branch Officers</h3>
      <h4>President: &nbsp; {{officers.fields.branchOfficersPresident}}</h4>
      <h4>Vice President: &nbsp; {{officers.fields.vicePresident}}</h4>
      <h4>Recording Secretary: &nbsp; {{officers.fields.recordingSecretary}}</h4>
      <h4>Membership Secretary: &nbsp; {{officers.fields.membershipSecretary}}</h4>
      <h4>Treasurer:  &nbsp; {{officers.fields.treasurer}}</h4>
      
      <br>
      <h3>Board of Directors</h3>
      <h4>{{BOD.fields.one}}</h4>
      <h4>{{BOD.fields.two}}</h4>
      <h4>{{BOD.fields.three}}</h4>
      <h4>{{BOD.fields.four}}</h4>
      <br>
      <h3>Program Chairs</h3>
      <h4>Adult Recital: <br> {{chairs.fields.adultRecital}}</h4><br>
      <h4>Branch Directory: <br> {{chairs.fields.branchDirectory}}</h4><br>
      <h4>Honors Recital: <br> {{chairs.fields.honorsRecital}}</h4><br>
      <h4>Librarian/Historian: <br> {{chairs.fields.librarianhistorian}}</h4><br>
      <h4>Certificate of Merit: <br> {{chairs.fields.certificateOfMerit}}</h4><br>
      <h4>Composers Today/Improvisation: <br> {{chairs.fields.composersTodayImprovisation}}</h4><br>
      <h4>Margaret B. Davis Memorial Music Competition: <br> {{chairs.fields.mbdMemorialMusicCompetition}}</h4><br>
      <h4>Monthly Student Recitals: <br> {{chairs.fields.studentRecitals}}</h4><br>
      <h4>Scholarship: <br> {{chairs.fields.scholarshipChair}}</h4><br>
      <h4>Spring festival: <br> {{chairs.fields.springFestival}}</h4><br>
      <h4>Teen Recital: <br> {{chairs.fields.teenRecital}}</h4><br>
      <h4>VOCE: <br> {{chairs.fields.voce}}</h4><br>
      <br>

      <h3>MTAC Mission Statement</h3>
      <p>
        {{mission.fields.missionStatement}}
      </p>
      <br>

      <h3>MTAC Vision Statement (Accepted in 2009)</h3>
      <p>
        {{vision.fields.visionStatement}}
      </p>
      <br>

      <h3>MTAC State Office</h3>
      <p>
        {{office.fields.info}}
      </p>



  </v-container>
</template>

<script>
  import {createClient} from '~/plugins/contentful.js'
  
  const client = createClient()

  export default {
  // make use of your env variables 
    asyncData ({env}) {
      return Promise.all([
        client.getEntries({    
         content_type: 'boardOfDirectors'
        }),
        client.getEntries({    
         content_type: 'branchOfficers'
        }),
        client.getEntries({    
         content_type: 'programChairs'
        }),
        client.getEntries({    
         content_type: 'missionStatement'
        }),
        client.getEntries({    
         content_type: 'visionStatement'
        }),
        client.getEntries({    
         content_type: 'stateOfficeInfo'
        })
      ]).then(([entries, officers, chairs, mission, vision, office]) => {
        // return data that should be available
        // in the template
        return {
         //access the items object of your JSON response
          BOD: entries.items[0],
          officers: officers.items[0],
          chairs: chairs.items[0],
          mission: mission.items[0],
          vision: vision.items[0],
          office: office.items[0],
        }
        
      }).catch(console.error)
    }
  }
</script>

<style lang="scss">

  .heading {
    margin-top: 4rem;
  }

 
</style>