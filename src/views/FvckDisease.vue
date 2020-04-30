<template>
  <div>
    <h1>U Little Fvcking Disease</h1>
    <el-select v-model="value" multiple placeholder="请选择">
      <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value"></el-option>
    </el-select>
    <!-- <el-table :data="list" border width="200">
      <el-table-column label="k1" prop="k1" min-width="120"></el-table-column>
      <el-table-column label="k2" prop="k2" min-width="130"></el-table-column>
      <el-table-column label="k3" prop="k3" min-width="150"></el-table-column>

      <el-table-column
        v-for="item in structureList"
        :label="item.name"
        :prop="item.attr"
        :key="item.attr"
        width="120"
      ></el-table-column>

      <el-table-column label="map" min-width="200">
        <template slot-scope="scope">
          {{ scope.row.map }}
          <el-row>
            <el-input v-for="item in scope.row.map" :key="item.key1" v-model="item.key2"></el-input>
          </el-row>
        </template>
      </el-table-column>

      <el-table-column label="ToolTip">
        <template slot-scope="scope">{{ scope.store }}</template>
      </el-table-column>
    </el-table> -->
    <el-button @click="printMap">Print</el-button>
    <h1>{{ print }}</h1>
    <el-button @click="dialogVisible = true">Visible</el-button>
    <el-dialog :visible.sync="dialogVisible">
      <h1>Dialog</h1>
      <about></about>
    </el-dialog>
  </div>
</template>
<script>
// import About from "./About.vue";
export default {
  components: {
    About: () => import("./About.vue")
  },
  data() {
    return {
      value: undefined,
      print: undefined,
      dialogVisible: false,
      options: [
        {
          value: "选项1",
          label: "黄金糕"
        },
        {
          value: "选项2",
          label: "双皮奶"
        },
        {
          value: "选项3",
          label: "蚵仔煎"
        },
        {
          value: "选项4",
          label: "龙须面"
        },
        {
          value: "选项5",
          label: "北京烤鸭"
        }
      ],
      list: [
        {
          k1: "v1",
          k2: "v2",
          k3: "v3",
          a1: "11",
          a2: "22",
          a3: "33",
          map: [
            { key1: "value1", key2: "value2" },
            { key1: "value3", key2: "value4" },
            { key1: "value5", key2: "value6" }
          ]
        },
        {
          k1: "v2",
          k2: "v4",
          k3: "v6",
          a1: "111",
          a2: "222",
          a3: "333",
          map: []
        }
      ],
      structureList: [
        {
          attr: "a1",
          name: "n1"
        },
        {
          attr: "a2",
          name: "n2"
        },
        {
          attr: "a3",
          name: "n3"
        }
      ]
    };
  },
  methods: {
    focus() {
      alert("focus");
    },
    printMap() {
      // this.print = this.list[0].map;
      this.print = this.value;
    }
  },
  created() {
    // alert("created");
  },
  activated() {
    // alert("activated");
  },
  destroyed() {
    // alert("destroyed");
  }
};
</script>
<style></style>
