<template>
    <div class="login">
        <div class="main-container">
            <el-button @click="resetDateFilter">Jesucristo</el-button>
            <el-button @click="clearFilter">Satanás</el-button>
            <el-table
                ref="filterTable"
                :data="tableData"
                style="width: 100%">
                <el-table-column
                prop="date"
                label="Fecha"
                sortable
                width="180"
                column-key="date"
                :filters="[{text: '2016-05-01', value: '2016-05-01'}, {text: '2016-05-02', value: '2016-05-02'}, {text: '2016-05-03', value: '2016-05-03'}, {text: '2016-05-04', value: '2016-05-04'}]"
                :filter-method="filterHandler"
                >
                </el-table-column>
                <el-table-column
                prop="name"
                label="Nombre"
                width="180">
                </el-table-column>
                <el-table-column
                prop="address"
                label="Dirección"
                :formatter="formatter">
                </el-table-column>
                <el-table-column
                prop="tag"
                label="Etiqueta"
                width="100"
                :filters="[{ text: 'Home', value: 'Home' }, { text: 'Office', value: 'Office' }]"
                :filter-method="filterTag"
                filter-placement="bottom-end">
                <template slot-scope="scope">
                    <el-tag
                    :type="scope.row.tag === 'Home' ? 'primary' : 'success'"
                    disable-transitions>{{scope.row.tag}}</el-tag>
                </template>
                </el-table-column>
            </el-table>
        </div>
    </div>
</template>
  
  
<script>
  export default {
    data() {
      return {
        tableData: [{
          date: '2016-05-03',
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles',
          tag: 'Home'
        }, {
          date: '2016-05-02',
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles',
          tag: 'Office'
        }, {
          date: '2016-05-04',
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles',
          tag: 'Home'
        }, {
          date: '2016-05-01',
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles',
          tag: 'Office'
        }]
      }
    },
    methods: {
      resetDateFilter() {
        this.$refs.filterTable.clearFilter('date');
      },
      clearFilter() {
        this.$refs.filterTable.clearFilter();
      },
      formatter(row, column) {
        return row.address;
      },
      filterTag(value, row) {
        return row.tag === value;
      },
      filterHandler(value, row, column) {
        const property = column['property'];
        return row[property] === value;
      }
    }
  }
</script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
    .login {
      margin: 0;
    }
  
    .main-container {
      margin: 0 auto;
      background-color: #ddd;
      border: 1px solid #bbb;
      min-width: 320px;
      max-width: 1200px;
      min-height: 320px;
      border-radius: 12px;
      padding: 18px 12px;
      box-shadow: 0px 2px 20px 2px rgba(102,102,102,0.7);
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
  
    .branding {
      margin: 12px auto;
    }
  
    .branding h1 {
      font-size: 1.2em;
      color: #444;
    }

    .form {
      padding: 2px 6px;
      width: 280px;
    }

    .el-date-editor.el-input {
      width: 280px !important;
    }
  
    #dateOfBirth {
      justify-self: flex-start;
    }

    .login {
      margin: 4px auto;
    }
  
    .login p {
      font-size: 14px;
    }
  
    .login a {
      color: teal;
      cursor: pointer;
    }

    .login a:hover {
      color: rgb(0, 100, 100);
      text-decoration: underline;
    }
  
  </style>