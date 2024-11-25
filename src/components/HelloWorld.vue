<template>
  <el-tree style="max-width: 600px" :data="data" :props="defaultProps" @node-click="handleNodeClick" />
</template>

<script lang="ts" setup>
import { inject,computed } from 'vue'
interface Tree {
  label: string
  children?: Tree[]
}

defineProps<{ msg: string }>()

const pData = inject<{name:Tree[]}>('pData') || {name:[]}

console.log(pData)
const handleNodeClick = (data: Tree) => {
  console.log(data)
}
const data = computed(()=> [
{
    label: 'Level one 1',
    children: pData.name,
  },
  {
    label: 'Level one 2',
    children: [
      {
        label: 'Level two 2-1',
        children: [
          {
            label: 'Level three 2-1-1',
          },
        ],
      },
      {
        label: 'Level two 2-2',
        children: [
          {
            label: 'Level three 2-2-1',
          },
        ],
      },
    ],
  },
  {
    label: 'Level one 3',
    children: [
      {
        label: 'Level two 3-1',
        children: [
          {
            label: 'Level three 3-1-1',
          },
        ],
      },
      {
        label: 'Level two 3-2',
        children: [
          {
            label: 'Level three 3-2-1',
          },
        ],
      },
    ],
  },
])


const defaultProps = {
  children: 'children',
  label: 'label',
}
</script>



<style scoped>
.read-the-docs {
  color: #888;
}
</style>
