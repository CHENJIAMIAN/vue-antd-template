<template>
  <div>
    <a-table :columns="columns" :dataSource="data" rowKey="key" :rowClassName="rowClassName">
      <a-table rowKey="key" :pagination="false"></a-table>
    </a-table>
  </div>
</template>

<script>
import moment from "moment";
const columns = [
  {
    title: "名字",
    dataIndex: "name",
    key: "name"
  },
  {
    title: "年龄",
    dataIndex: "age",
    key: "age"
  },
  {
    title: "地址",
    dataIndex: "address",
    key: "address"
  },
  {
    title: "布尔",
    dataIndex: "bool",
    key: "bool"
  }
];
const data = [
  {
    key: "1",
    name: "John Brown",
    age: 32,
    address: "New York No. 1 Lake Park",
    bool: true
  },
  {
    key: "2",
    name: "Jim Green",
    age: 42,
    address: "London No. 1 Lake Park",
    bool: false
  },
  {
    key: "3",
    name: "Joe Black",
    age: 32,
    address: "Sidney No. 1 Lake Park",
    bool: false
  }
];
export default {
  name: "App",
  data() {
    return {
      moment,
      data,
      columns
    };
  },
  methods: {
    rowClassName(record) {
      return record.child && record.child.length ? "" : "no-expand";
    }
  }
};
</script>
<style>
.no-expand .ant-table-row-expand-icon {
  display: none;
}
</style>
