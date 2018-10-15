<template>
  <div>
    <v-data-table
    :headers="headers"
    :items="teachers"
    :pagination.sync="pagination"
    :rows-per-page-items="rows"
    class="elevation-2 calendar-text"
    :loading="false"
    >    
      <template slot="items" slot-scope="props">
        <td class="text-xs-left table-text">{{ props.item.date }}</td>
        <td class="text-xs-left table-text">{{ props.item.time }}</td>
        <td class="text-xs-left table-text">{{ props.item.activity }}</td>
        <td class="table-text">{{ props.item.location }}</td>
        <td class="table-text">{{ props.item.chair }}</td>        
      </template>
    </v-data-table>    
  </div>
</template>



<script>
import axios from 'axios'
// require('dotenv').config();

export default {
  data () {
    return {
      teachers: [],
      headers: [
        { text: 'Date', value: 'date', align: 'left', class: 'calendar-text' },
        { text: 'Time', value: 'time', align: 'left', class: 'calendar-text' },
        { text: 'Activity', value: 'activity', class: 'calendar-text' },
        { text: 'Location', value: 'location', class: 'calendar-text' },
        { text: 'Chair', value: 'chair', class: 'calendar-text' }
      ],
      toggleOrder () {
        this.pagination.ascending = !this.pagination.ascending
      },
      rows: [ { text: 'All', value: -1 }, 5, 10, 20],
      pagination: {
        sortBy: 'count'
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
        .get(`https://sheets.googleapis.com/v4/spreadsheets/1SIfFSp_1In8V_NmIGjVtry-7478OJosu91J_toQT7gs/values/Sheet2?valueRenderOption=FORMATTED_VALUE&key=${process.env.TEACHERS_KEY}`)
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

  .calendar-text {
    font-size: 1rem !important;
    font-family: Roboto;
    margin: 2rem;
    margin-top: 5rem;
  }
  .table-text {
    font-size: 1rem !important;
    font-family: Roboto;
  }
</style>