<template>
  <div>
    <div id="toolbar">
      <el-button @click="refreshOptions">
        refreshOptions
      </el-button>
    </div>
    <element-table
      ref="table"
      :columns="columns"
      :options="options"
    />
  </div>
</template>

<script>
export default {
  data () {
    return {
      columns: [
        [
          {
            title: 'ID',
            field: 'id'
          },
          {
            title: 'Item Name',
            field: 'name'
          },
          {
            title: 'Item Price',
            field: 'price'
          }
        ]
      ],
      options: {
        toolbar: '#toolbar',
        height: 460,
        url: 'json/data1.json'
      }
    }
  },
  methods: {
    refreshOptions () {
      this.$refs.table.refreshOptions({
        showColumns: true,
        search: true,
        showRefresh: true,
        url: 'json/data1.json'
      })
    }
  }
}
</script>
