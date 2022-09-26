<template>
  <div class="main">
    <!-- Navigation -->
    <el-row>
      <el-col :span="5" class="hidden-xs-only"
        ><div class="grid-content bg-purple-dark">
          <h2>My Blog</h2>
        </div></el-col
      >
      <el-col :span="15" :xs="24" :sm="19" :md="15"
        ><div class="grid-content bg-purple menu-items">
          <div class="left-nav">
            <i
              class="hidden-sm-and-up el-icon-menu"
              type="primary"
              @click="drawer = true"
            >
            </i>
            <h2 class="hidden-sm-and-up">My Blog</h2>
          </div>

          <div class="right-nav">
            <ul class="hidden-xs-only list">
              <li class="list-item">AAbout</li>
              <li class="list-item">Team</li>
              <li class="list-item">Lorem</li>
              <li class="list-item">Lorem</li>
            </ul>
          </div>
          <i
            class="hidden-md-and-up el-icon-menu"
            type="primary"
            @click="outerVisible = true"
          >
          </i></div
      ></el-col>
      <el-col :span="4" class="hidden-sm-and-down"
        ><div class="grid-content bg-purple-light"></div
      ></el-col>
    </el-row>

    <!-- Main Page -->
    <el-row>
      <el-col :span="5" class="hidden-xs-only"
        ><div class="grid-content bg-purple-dark">Main Page</div></el-col
      >
      <el-col :span="15" :xs="24" :sm="19" :md="15"
        ><div class="grid-content bg-purple"></div
      ></el-col>
      <el-col :span="4" class="hidden-sm-and-down"
        ><div class="grid-content bg-purple-light"></div
      ></el-col>
    </el-row>

    <!-- Footer  -->
    <el-row>
      <el-col :span="5" class="hidden-xs-only"
        ><div class="grid-content bg-purple-dark">Footer</div></el-col
      >
      <el-col :span="15" :xs="24" :sm="19" :md="15"
        ><div class="grid-content bg-purple"></div
      ></el-col>
      <el-col :span="4" class="hidden-sm-and-down"
        ><div class="grid-content bg-purple-light"></div
      ></el-col>
    </el-row>

    <!-- Left Menu for Mobile View  -->
    <el-drawer
      title="I'm outer Drawer"
      :visible.sync="drawer"
      size="320px"
      :direction="direction"
    >
      <div></div>
    </el-drawer>

    <!-- Search Modal -->
    <el-dialog
      :visible.sync="outerVisible"
      width="80%"
      style="margin: 5vh auto"
    >
    <el-input placeholder="Please input" v-model="input"></el-input>
      <ul class="search-results">
        <li v-for="item in 10" :key="item">
          <h4>Hello World! Lorem text</h4>
          <p>
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Earum,
            veritatis.
          </p>
        </li>
      </ul>
    </el-dialog>
  </div>
</template>

<script>
import 'element-ui/lib/theme-chalk/display.css'

export default {
  name: 'DefaultLayout',
  data: () => ({
    drawer: false,
    direction: 'ltr',
    outerVisible: false,
    input: '',
  }),

  methods: {
    handleClose(done) {
      this.$confirm('You still have unsaved data, proceed?')
        .then((_) => {
          done()
        })
        .catch((_) => {})
    },
  },
}
</script>

<style>
* {
  font-family: sans-serif;
}

.main {
  width: 98%;
  margin: auto;
}

.el-row {
  margin-bottom: 20px;
}
.el-col {
  border-radius: 4px;
}
.bg-purple-dark {
  background: #99a9bf;
}
.bg-purple {
  background: #d3dce6;
}
.bg-purple-light {
  background: #e5e9f2;
}
.grid-content {
  border-radius: 4px;
  min-height: 36px;
}
.row-bg {
  padding: 10px 0;
  background-color: #f9fafc;
}

.main i {
  font-size: 24px;
  color: #8a8a8a;
  margin: 3px;
  padding: 8px;
  border-radius: 50%;
  cursor: pointer;
  border: 1px transparent;
}

.main i:hover {
  background: #ecf4ff;
  transition: ease-in-out 0.4s;
}

.main .menu-items {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.left-nav {
  background: wheat;
  display: flex;
  align-content: center;
  justify-content: space-between;
}

.right-nav {
  background: cornflowerblue;
}

.main h2 {
  margin: 0;
}

.list {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 0 5px;
}

.list .list-item {
  text-decoration: none;
  list-style: none;
  margin-right: 40px;
}

.main .search-results {
  /* position: fixed; */
  max-height: 400px;
  overflow-x: hidden;
  overflow-y: auto;
  text-align: justify;
}

.main h2 {
  padding: 5px;
}
</style>