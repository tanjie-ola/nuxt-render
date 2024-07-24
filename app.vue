<script setup lang="jsx">
import {Tag as ATag} from '@arco-design/web-vue'
import { reactive } from 'vue'
import Render from './Render.vue'
const originColumns = [
  {
    title: 'Name',
    dataIndex: 'name',
    width: 200,
    render({ record }) {
      return h(ATag, {}, record.name)
    },
  },
  {
    title: 'Salary',
    dataIndex: 'salary',
    // slotName: 'salary',

    width: 200,
  },
  {
    title: 'Address',
    dataIndex: 'address',
    width: 200,
  },
  {
    title: 'Email',
    dataIndex: 'email',
    width: 200,
    render({ record }) {
      return <a-tag>{record.email}</a-tag>
    },
  },
]

const data = reactive([
  {
    key: '1',
    name: 'Jane Doe',
    salary: 23000,
    address: '32 Park Road, London',
    email: 'jane.doe@example.com',
  },
  {
    key: '2',
    name: 'Alisa Ross',
    salary: 25000,
    address: '35 Park Road, London',
    email: 'alisa.ross@example.com',
  },
  {
    key: '3',
    name: 'Kevin Sandra',
    salary: 22000,
    address: '31 Park Road, London',
    email: 'kevin.sandra@example.com',
  },
  {
    key: '4',
    name: 'Ed Hellen',
    salary: 17000,
    address: '42 Park Road, London',
    email: 'ed.hellen@example.com',
  },
  {
    key: '5',
    name: 'William Smith',
    salary: 27000,
    address: '62 Park Road, London',
    email: 'william.smith@example.com',
  },
])

const item={
    title: 'Email',
    dataIndex: 'email',
    width: 200,
    render({ record }) {
      return <a-tag>{record.email}</a-tag>
    },
  }
  const form={
    key: '5',
    name: 'William Smith',
    salary: 27000,
    address: '62 Park Road, London',
    email: 'william.smith@example.com',
  }
</script>

<template>

  <a-table :columns="originColumns" :data="data" />
  <Render :item="item" :form="form"></Render>
</template>
