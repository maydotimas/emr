<template>
  <div class="animated fadeIn">

    <b-row>
      <b-col lg="12">
        <c-table :table-data="items" :fields="fields" caption="<i class='fa fa-align-justify'></i> Patients"></c-table>
      </b-col>
    </b-row><!--/.row-->

  </div>

</template>

<script>
import { shuffleArray } from '@/shared/utils'
import cTable from '../base/Table'

const someData = () => shuffleArray([
  {username: 'Samppa Nori', registered: '2012/01/01', role: 'Member', address: 'Bulacan', status: 'Active',action:'asf',  _rowVariant: 'success', },
])

export default {
  name: 'tables',
  components: {cTable},
  data: () => {
    return {
      items: someData,
      itemsArray: someData(),
      fields: [
        {key: 'username', label: 'Name', sortable: true},
        {key: 'registered', label: 'Age', sortable: true},
        {key: 'role',label: 'Gender', sortable: true},
        {key: 'address', label: 'Address', sortable: true},
        {key: 'status', label: 'Status', sortable: true},
        {key: 'action', label: 'Action', sortable: true},
      ],
    }
  }
}
</script>
