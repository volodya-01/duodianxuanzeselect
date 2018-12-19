<template>
  <div class="select">
         <div class="wroutbox">
           <div class="inbox1">
              发现污染点
           </div>
           <div class="inbox2">
                 <div class="rbox1">
                    <el-select
                      v-model="value10"
                      multiple
                      filterable
                      allow-create
                      default-first-option
                      placeholder="请选择">
                      <el-option
                        v-for="(item,index) in options5"
                        :key="index"
                        :label="item.label"
                        :value="item">
                      </el-option>
                    </el-select>
                 </div>
                  <div class="rbox2" @click="dialogTableVisible = true">水质点</div>
                  <div class="rbox3" @click="add">.&nbsp;.&nbsp;.</div>
           </div>
         </div>
          <!-- //弹出框1 -->
<el-dialog title="水质点列表" :visible.sync="dialogTableVisible">
 <div class="outbox">
     <div class="tablebox">
                    <el-table
                :data="value10"
                style="width: 100%"
                max-height="250">
                <el-table-column
                  prop="label"
                  width="90">
                </el-table-column>
                <el-table-column>
                  <template slot-scope="scope">
                    <el-button
                      @click.native.prevent="deleteRow(scope.$index, value10)"
                      type="text"
                      size="small">
                      移除
                    </el-button>
                  </template>
                </el-table-column>
              </el-table>
      </div>
  </div>
</el-dialog>
<!--          
            <div>{{value10}}</div>
 <div class="outbox">
     <div class="tablebox">
                    <el-table
                :data="value10"
                style="width: 100%"
                max-height="250">
                <el-table-column
                  prop="label"
                  width="150">
                </el-table-column>
                <el-table-column>
                  <template slot-scope="scope">
                    <el-button
                      @click.native.prevent="deleteRow(scope.$index, value10)"
                      type="text"
                      size="small">
                      移除
                    </el-button>
                  </template>
                </el-table-column>
              </el-table>
      </div>
  </div>
<button @click="add">点击</button> -->

  </div>
</template>

<script>
export default {
  name: 'selectdemo',
   data() {
      return {
        options5: [{
          value: 'HTML',
          label: 'HTML'
        }, {
          value: 'CSS',
          label: 'CSS'
        }, {
          value: 'JavaScript',
          label: 'JavaScript'
        }],
        value10: [],
        dialogTableVisible: false,
      }
    },
    watch:{
      value10(val){
console.log(this.value10)
      }
    },
    methods:{
      deleteRow(index, rows) {
        rows.splice(index, 1);
      },
      add(){
        var a={
          value: 'vue',
          label: 'vue'
        }
        this.value10.push(a);
        this.options5.push(a)
      }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.el-select {
       height: 24px;
    width: 182px;
    overflow: hidden;
}
.el-select__tags {
      height: 24px;
    overflow: hidden;
}
.el-select__input {
    height: 24px;
}
.el-select>.el-input {
    display: block;
    height: 24px;
}
.el-input__icon {
    line-height: 24px;
}
.el-tag--small {
    height: 20px;
    line-height: 20px;
}
input::-webkit-input-placeholder {
   font-size: 12px;
  color: #acb3ba;
}
input:-moz-placeholder {
 font-size: 12px;
  color: #acb3ba;
}
input::-moz-placeholder {
  font-size: 12px;
  color: #acb3ba;
}
input:-ms-input-placeholder {
  font-size: 12px;
  color: #acb3ba;
}

  .el-button--text {
    margin-left: 170px;
}
.el-dialog__body {
    padding: 0px;
        height: 260px;
}
.el-dialog {
    width: 380px;
}
.el-dialog__header {
   display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: center;
    padding: 20px 20px 0px;
}
.el-dialog__title {
    line-height: 12px;
    font-size: 12px;
    color: #acb3ba;
}
.el-table--scrollable-y .el-table__body-wrapper {
    overflow-y: auto;
    width: 340px;
}
.el-table td, .el-table th {
    padding: 0px 0;
}
.el-table .cell {
    font-size:12px;
  font-family:"微软雅黑";
  color:#818d9a;
    line-height: 12px;
    font-size: 12px;
}
.el-button--text {
     font-size:12px;
  font-family:"微软雅黑";
  color:#818d9a;
    line-height: 12px;
    font-size: 12px;
}

.el-select-dropdown__item {
    font-size:12px;
  font-family:"微软雅黑";
  color:#818d9a;
    line-height: 12px;
   
}
</style>

<style scoped>
.select{
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: center;
  width:424px;
  height: 194px;
  border:1px #d1d1da solid;
  margin:0 400px
}
.wroutbox{
display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: center;
}
.inbox1{
  font-size:12px;
  font-family:"微软雅黑";
  color:#818d9a;
  margin-right:30px;
}
.inbox2{
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: center;
}
.rbox2{
  width:48px;
  height: 22px;
  line-height:22px;
   font-size:12px;
  font-family:"微软雅黑";
  color:#818d9a;
  background-color:#eeeef0;
  border:1px #e4e4ec solid;
  margin-left:10px;
  border-radius:2px;
}
.rbox3{
  width:26px;
   height: 22px;
  line-height:16px;
   font-size:12px;
  font-family:"微软雅黑";
  color:#818d9a;
   border:1px #e4e4ec solid;
   background-color:#eeeef0;
 margin-left:10px;
  border-radius:2px;
}
.outbox {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  justify-content: flex-start;
  align-items: center;
  width: 320px;
  height: 200px;
   margin-left: 20px;
  
}
.tablebox {
  width: 320px;
  height: 200px;
}

/* .deleteBtn {
  width: 12px;
  height: 16px;
  background: url("~@/assets/delete.png") no-repeat;
  cursor: pointer;
}
 */

</style>
