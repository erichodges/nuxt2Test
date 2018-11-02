<template>
  <main>
    <v-container class="teacher-header">
    <div>
      <h1 class="teacher-header">Music Teacher Directory</h1>
      <p>
        The following teachers have met the education requirements and are approved members of the Marin Branch of the Music Teachers' Association of California. 
      </p>
      <p>
        We offer lessons to students of all ages in piano, organ, harpsichord, violin, viola, cello, flute, clarinet, saxophone, voice, conducting, music theory, composition, harp and accordion.
      </p>
    </div>
    </v-container>
    <div>    
      <v-data-table
      :headers="headers"
      :items="teachers"
      :pagination.sync="pagination"
      :rows-per-page-items="rows"
      class="elevation-2 heading-text"
      :loading="false"    
      >    
        <template slot="items" slot-scope="props">
          <td style="font-size:1rem" class="text-xs-left table-text">{{ props.item.instrument }}</td>
          <td class="text-xs-left table-text">{{ props.item.city }}</td>
          <td class="text-xs-left table-text">{{ props.item.travel }}</td>
          <td class="text-xs-left table-text">{{ props.item.firstName }}</td>
          <td class="text-xs-left table-text">{{ props.item.lastName }}</td>                        
          <td class="text-xs-left table-text">{{ props.item.phone }}</td>
          <td class="text-xs-left table-text">{{ props.item.email }}</td>
        </template>
      </v-data-table>
    </div>
    <div>
      <v-container>
      
      <h3>
        If you need to search for a teacher elsewhere in California, use the button below to search the MTAC database: 
      </h3>
      <br>
        <a href="http://www.mtac.org/about-us/find-a-teacher/">
          <v-btn>MTAC Teachers</v-btn>
        </a>
        <br>
        <br>
        <br>
      </v-container>
    </div>
  </main>
</template>



<script>
import axios from 'axios'

export default {
  data () {
    return {
      teachers: [],
      headers: [
        { text: 'Instrument', value: 'instrument', align: 'left', class: 'heading-text' },
        { text: 'City', value: 'city', align: 'left', class: 'heading-text' },
        { text: 'Will Travel?', value: 'travel', class: 'heading-text'  },
        { text: 'First Name', value: 'firstName', class: 'heading-text' },
        { text: 'Last Name', value: 'lastName', class: 'heading-text' },
        { text: 'Phone', value: 'phone', class: 'heading-text phone', width: '147' },
        { text: 'email', value: 'email', class: 'heading-text' }
      ],
      rows: [ { text: 'All', value: -1 }, 5, 10, 20],
      pagination: {
        sortBy: 'city'
      }
    }
  },
  components: {
  },
  mounted () {
    this.getData()
  },
  methods: {
    onConvert (data) {
      let keys = data[0]
      let values = data.slice(1)
      let object = {}
      let objects = values.map(array => {
        object = {}

        keys.forEach((key, i) => object[key] = array[i]) // eslint-disable-line

        return object
      })
      this.teachers = objects
    },
    getData () {
      return axios
        .get(`https://sheets.googleapis.com/v4/spreadsheets/1IGposbdT8R8j6UdmGtAFgI_39LZL8UWOIIpnsyC23mM/values/Sheet1?valueRenderOption=FORMATTED_VALUE&key=${process.env.TEACHERS_KEY}`)
        .then(response => {
          this.onConvert(response.data.values)
        })
    },
      nextSort () {
        let index = this.headers.findIndex(h => h.value === this.pagination.sortBy)
        index = (index + 1) % this.headers.length
        index = index === 0 ? index + 1 : index
        this.pagination.sortBy = this.headers[index].value
      }
  }
}
</script>

<style lang="scss">

.teacher-header {
  margin-top: 2rem;
}

.phone {
  padding-left: 45px !important;
  padding-right: 45px !important;
}

.heading-text {
  font-size: 1rem !important;
  font-family: Roboto;
  margin: 2rem;
  margin-top: 1rem;
}

.table-text {
  font-size: 1rem !important;
  font-family: Roboto;    
}
</style>