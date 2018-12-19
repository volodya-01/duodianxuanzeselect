<template>
  <div class="select">
    <div class="outbox">
      <div class="outbox1">
        <div class="outbox1-1">最大历时</div>
        <div class="outbox1-2">
          <div class="maxtimeinput">
            <input type="text" placeholder="请输入信息" class="maxtimeinput">
          </div>
          <div class="hourfont">小时</div>
        </div>
      </div>
      <div class="outbox2">
        <div class="outbox2-1">发现污染点</div>
        <div class="outbox2-2">
          <div class="wrdiput">
            <!--  <input class="inputbox" type="text" v-model="value" disabled> -->
            <div v-for="(item0,index0) in list0" :key="index0" class="wrdiputoutbox">
              <div class="wrdiputinbox">
                <span>{{item0.label}}</span>
                <span
                  class="delet0 iconfont icon-shanchu"
                  @click="selectapi0(index0)"
                  style="color:#729a18"
                ></span>
              </div>
            </div>
          </div>
          <div class="jiahao" @click="showselct">+</div>
          <div class="szdfont" @click="selectfun">水质点</div>
          <div class="searchpoint">.&nbsp;.&nbsp;.</div>
        </div>
      </div>
      <div class="outbox3">
        <div class="outbox3-1">污染发生时间</div>
        <div class="outbox3-2">
          <select class="outbox3-2">
            <option
              v-for="(item,index) in list1"
              :key="index"
              value="item.label"
              style="outline:none;border:none;height:30px"
            >{{item.label}}</option>
            <!--  <option value="saab">Saab</option>
            <option value="opel">Opel</option>
            <option value="audi">Audi</option>-->
          </select>
        </div>
      </div>
    </div>

    <!-- 下拉框部分 -->
    <div class="drapedwon" v-show="drap1">
      <div
        v-for="(item,index) in list1"
        :key="index"
        :class="{'active': listnum0[index] == index}"
        class="drapedwonlist1"
      >
        <div class="listinboix1" @click="selectapi(index)">
          <span>{{item.label}}</span>
        </div>
      </div>
    </div>

    <div class="drapedwon2" v-show="drap2">
      <div v-for="(item2,index2) in list0" :key="index2" class="drapedwonlist2">
        <div class="listinboix2">
          <span>{{item2.label}}</span>
          <span
            class="delet iconfont icon-shanchu"
            @click="selectapi2(index2)"
            style="color:#729a18"
          ></span>
        </div>
      </div>
    </div>

    <!-- 下拉框部分结束 -->
  </div>
</template>

<script>
import "../assets/iconfont/iconfont.css";
export default {
  name: "select2",
  data() {
    return {
      drap1: false,
      drap2: false,
      nowIndex: 0,
      listnum0: [],
      list0: [],
      list1: [],
      value: ["HTML", "CSS", "JavaScript", "HTML", "CSS", "JavaScript"]
    };
  },
  mounted() {
    var arr = [];
    var a = { label: "szxxc00", value: "1" };
    for (var i = 0; i < 20; i++) {
      arr.push(a);
    }
    this.list1 = arr;
    console.log(this.list1);
  },
  methods: {
    selectfun() {
      if (this.drap1 == false) {
        this.drap1 = true;
        this.drap2 = false;
      } else {
        this.drap1 = false;
      }
    },
    showselct() {
      if (this.drap2 == false) {
        this.drap2 = true;
        this.drap1 = false;
      } else {
        this.drap2 = false;
      }
    },
    selectapi(val) {
      var a=val
      a+=val
      alert(a)
      this.listnum0.length = this.list1.length;
      this.listnum0.splice(val, 1, val);
      /* this.listnum0.push(val) */
      this.list0.push(this.list1[val]);
      this.nowIndex = val;
     /*  alert(this.listnum0.length); */
    },
    selectapi2(val2) {
      /*  var v=val */
     /*  alert(val2); */
      this.list0.splice(val2, 1);
    },
    selectapi0(val0) {
      /*  var v=val */
      /* alert(val0); */
      this.list0.splice(val0, 1);
    }
  }
};
</script>
<style scoped>
.select {
  margin: 60px 400px;
}
.outbox {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: center;
  width: 424px;
  height: 192px;
  border: 1px #d1d1da solid;
}
.outbox1 {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: center;
  width: 382px;
  height: 25px;
}
.outbox1-1 {
  font-size: 12px;
  font-family: "微软雅黑";
  color: #818d9a;
}
.outbox1-2 {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: center;
}
.maxtimeinput {
  width: 258px;
  height: 24px;
  background-color: #f0f0f1;
  border-radius: 2px;
}
input {
  background-color: #f0f0f1;
  text-align: start;
  font-size: 12px;
  font-family: "微软雅黑";
  color: #818d9a;
  border: none;
  outline: none;
  border-radius: 2px;
}
input::-webkit-input-placeholder {
  padding-left: 5px;
  color: #acb3ba;
}
input:-moz-placeholder {
  margin-left: 5px;
  color: #acb3ba;
}
input::-moz-placeholder {
  margin-left: 5px;
  color: #acb3ba;
}
input:-ms-input-placeholder {
  margin-left: 5px;
  color: #acb3ba;
}

.hourfont {
  font-size: 12px;
  font-family: "微软雅黑";
  color: #818d9a;
  margin-left: 15px;
}
.outbox2 {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: center;
  width: 382px;
  height: 25px;
  margin-top: 30px;
}
.outbox2-1 {
  font-size: 12px;
  font-family: "微软雅黑";
  color: #818d9a;
}
.outbox2-2 {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: center;
}
.wrdiput {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: flex-start;
  align-items: center;
  width: 182px;
  height: 24px;
  /*  background-color: #bb2f36; */
  background-color: #f0f0f1;
  border-radius: 2px;
  overflow: hidden;
}
.wrdiputoutbox {
  width: 142px;
  height: 24px;
}
.wrdiputinbox {
  font-size: 12px;
  font-family: "微软雅黑";
  color: #818d9a;
  width: 65px;
  height: 24px;
  line-height: 24px;
}

.jiahao {
  width: 20px;
  height: 24px;
  line-height: 24px;
  background-color: #f0f0f1;
  /* margin-left: 10px; */
  cursor: pointer;
}
.delet0 {
  margin-left: 5px;
}
.iconfont {
  font-size: 12px;
}
.szdfont {
  width: 48px;
  height: 22px;
  line-height: 22px;
  font-size: 12px;
  font-family: "微软雅黑";
  color: #818d9a;
  background-color: #eeeef0;
  border: 1px #e4e4ec solid;
  margin-left: 10px;
  border-radius: 2px;
  cursor: pointer;
}
.searchpoint {
  width: 26px;
  height: 22px;
  line-height: 16px;
  font-size: 12px;
  font-family: "微软雅黑";
  color: #818d9a;
  border: 1px #e4e4ec solid;
  background-color: #eeeef0;
  margin-left: 10px;
  border-radius: 2px;
  cursor: pointer;
}
.outbox3 {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: center;
  width: 382px;
  height: 25px;
  margin-top: 30px;
}
.outbox3-1 {
  font-size: 12px;
  font-family: "微软雅黑";
  color: #818d9a;
}
.outbox3-2 {
  width: 296px;
  height: 24px;
  background-color: #f0f0f1;
  border-radius: 2px;
  margin-right: 5px;
  outline: none;
  border: none;
  font-size: 12px;
  font-family: "微软雅黑";
  color: #818d9a;
  cursor: pointer;
}

/* 下拉框部分样式 */
.drapedwon {
  width: 151px;
  height: 163px;
  border: 1px #e4e4ec solid;
  /*  background-color: #d1d1da; */
  position: relative;
  top: -80px;
  left: 315px;
  overflow: auto;
  background-color: #fff;
}

.drapedwonlist1 {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: center;
  color: #818d9a;
}
/* .drapedwonlist1:nth-child(even){
    background-color: #818d9a
} */
.listinboix1 {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: flex-start;
  align-items: center;
  height: 30px;
  width: 108px;
  /*  margin-left: 20px; */
}
.listinboix1 > span {
  font-size: 12px;
  font-family: "微软雅黑";
  /* color: #818d9a; */
  cursor: pointer;
}

.drapedwon2 {
  width: 198px;
  height: 110px;
  border: 1px #e4e4ec solid;
  /*  background-color: #d1d1da; */
  position: relative;
  top: -80px;
  left: 105px;
  overflow: auto;
  background-color: #fff;
}
.drapedwonlist2:hover {
  background-color: #f0f0f1;
}
.listinboix2 {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: center;
  height: 30px;
  width: 160px;
  margin: 0 15px;
}
.listinboix2 > span {
  font-size: 12px;
  font-family: "微软雅黑";
  color: #818d9a;
  cursor: pointer;
}
.delet {
  margin-left: 20px;
}
.active {
  background-color: #f0f0f1;
  color: #729a18;
  /*  border-bottom: 1px #d1d1da solid; */
}

select{border: none;outline: none;}

</style>
