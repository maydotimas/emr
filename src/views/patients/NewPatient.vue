<template>
  <div class="animated fadeIn">
    <b-card>
      <b-row>
        <b-col sm="5" class="mb-3">
          <h4 id="traffic" class="card-title mb-0">New Patient</h4>
          <div class="small text-muted">New Patient Record</div>
        </b-col>
        <b-col sm="7" class="d-none d-md-block">
          <router-link to="/patients/new">
            <b-button type="button" variant="primary" class="float-right"><i class="fa fa-wheelchair"></i> New Patient</b-button>
          </router-link>
        </b-col>
      </b-row>
      <b-row>
        <b-col lg="12">
          <c-table :table-data="items" :fields="fields" caption="Patients"></c-table>
        </b-col>
      </b-row><!--/.row-->
    </b-card>
  </div>

</template>

<script>
    import {shuffleArray} from '@/shared/utils'
    import cTable from '../base/Table'

    const someData = () => shuffleArray([
        {
            username: 'Samppa Nori',
            registered: '2012/01/01',
            role: 'Member',
            address: 'Bulacan',
            status: 'Active',
            action: 'asf',
            _rowVariant: 'success',
        },
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
                    {key: 'role', label: 'Gender', sortable: true},
                    {key: 'address', label: 'Address', sortable: true},
                    {key: 'status', label: 'Status', sortable: true},
                    {key: 'action', label: 'Action', sortable: true},
                ],
            }
        }
    }
</script>
