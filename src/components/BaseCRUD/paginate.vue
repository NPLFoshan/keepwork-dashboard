<template>
  <div class="content-container pagination-container">
    <el-pagination background @size-change="handleSizeChange" @current-change="handleCurrentChange" :current-page="listQuery['x-page']" :page-sizes="[10,20,30,50]" :page-size="listQuery['x-per-page']" layout="total, sizes, prev, pager, next, jumper" :total="total">
    </el-pagination>
  </div>
</template>

<script>
export default {
  name: 'CRUDPaginate',
  props: {
    listQuery: {
      type: Object,
      required: true
    },
    total: {
      type: Number,
      default: 0
    }
  },
  methods: {
    handleSizeChange(val) {
      return this.$emit('handleSizeChange', val)
    },
    handleCurrentChange(val) {
      return this.$emit('handleCurrentChange', val)
    }
  }
}
</script>
