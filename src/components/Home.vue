<template>
    <div class="login">
        <div class="main-container">
          <div class="table-container">
            <el-table
                ref="filterTable"
                :data="tableData"
                style="width: 100%">
                <el-table-column
                prop="date"
                label="Date"
                sortable
                width="180"
                column-key="date"
                :filters="[{text: '0000-05-01', value: '0000-05-01'}, {text: '0000-05-02', value: '0000-05-02'}, {text: '0000-05-03', value: '0000-05-03'}, {text: '0000-05-04', value: '0000-05-04'}]"
                :filter-method="filterHandler"
                >
                </el-table-column>
                <el-table-column
                prop="user"
                label="User"
                width="150">
                </el-table-column>
                <el-table-column
                prop="post"
                label="Post"
                >
                </el-table-column>
                <el-table-column
                prop="tag"
                label="Tag"
                width="120"
                :filters="[{ text: 'Philosophy', value: 'Philosophy' }, { text: 'Religion', value: 'Religion' }]"
                :filter-method="filterTag"
                filter-placement="bottom-end">
                <template slot-scope="scope">
                    <el-tag
                    :type="scope.row.tag === 'Philosophy' ? 'primary' : 'success'"
                    disable-transitions>{{scope.row.tag}}</el-tag>
                </template>
                </el-table-column>
                <el-table-column
                  fixed="right"
                  label="Show more"
                  width="120"
                >
                <el-button @click="centerDialogVisible = true">+</el-button>
                <el-dialog
                  title="Warning"
                  :visible.sync="centerDialogVisible"
                  width="30%"
                  center>
                  <span>It should be noted that the content will not be aligned in center by default</span>
                  <span slot="footer" class="dialog-footer">
                    <el-button @click="centerDialogVisible = false">Cancel</el-button>
                    <el-button type="primary" @click="centerDialogVisible = false">Confirm</el-button>
                  </span>
                </el-dialog>
                </el-table-column>
            </el-table>
            <div class="buttons-container">
              <el-button type="primary" @click="resetDateFilter">Reset date filter</el-button>
              <el-button type="danger" @click="clearFilter">Clear filter</el-button>
            </div>
          </div>
        </div>
    </div>
</template>
  
  
<script>
  export default {
    data() {
      return {
        tableData: [{
          date: '0000-05-03',
          user: 'Cicero',
          post: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
          tag: 'Philosophy'
        }, {
          date: '0000-05-02',
          user: 'Jesus',
          post: 'Tu es Petrus. Et super hanc petram ædificabo ecclesiam meam. Et portæ inferi non prævalebunt adversus eam. Et tibi dabo claves regni cælorum.',
          tag: 'Religion'
        }, {
          date: '0000-05-04',
          user: 'Cicero',
          post: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
          tag: 'Philosophy'
        }, {
          date: '0000-05-01',
          user: 'Jesus',
          post: 'Tu es Petrus. Et super hanc petram ædificabo ecclesiam meam. Et portæ inferi non prævalebunt adversus eam. Et tibi dabo claves regni cælorum.',
          tag: 'Religion'
        }],
        centerDialogVisible: false
      }
    },
    methods: {
      resetDateFilter() {
        this.$refs.filterTable.clearFilter('date');
      },
      clearFilter() {
        this.$refs.filterTable.clearFilter();
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
      min-height: 180px;
      border-radius: 12px;
      padding: 64px 12px 24px;
      box-shadow: 0px 2px 20px 2px rgba(102,102,102,0.7);
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
  
    .table-container {
      min-width: 1100px;
    }
  
    .buttons-container {
      margin-top: 24px;
    }
    
  
  </style>