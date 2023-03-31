<script setup lang="ts">
// import TheWelcome from '../components/TheWelcome.vue'
import { ref } from "vue";
import { reactive } from "vue";
let navstyle = reactive({
  width: "110px",
  transition: "1s",
});
let linestyle = reactive({
  width: "60px",
  transition: "1s",
});
let constyle = reactive({
  width: "0px",
  opacity: 0,
  left: "-20px",
});
let switchstyle = reactive({
  transform: "rotate(180deg)",
});
let riconstyle = reactive({
  width: "0px",
  opacity: 0,
});
let username = ref("魏建奇111111");
let iconconstyle = reactive({
  opacity: 0,
  width: "0px",
});

function openControl() {
  console.log(navstyle.width);
  if (navstyle.width == "110px") {
    navstyle.width = "280px";
    linestyle.width = "230px";
    switchstyle.transform = "rotate(0deg)";
    iconconstyle.opacity = 1;
    iconconstyle.width = "130px";
    constyle = {
      width: "160px",
      opacity: 1,
      left: "0px",
    };
    riconstyle = {
      width: "60px",
      opacity: 1,
    };
  } else {
    navstyle.width = "110px";
    linestyle.width = "60px";
    switchstyle.transform = "rotate(180deg)";
    iconconstyle.opacity = 0;
    iconconstyle.width = "0px";
    constyle = {
      width: "0px",
      opacity: 0,
      left: "-20px",
    };
    riconstyle = {
      width: "0px",
      opacity: 0,
    };
  }
}
</script>

<template>
  <div class="wrap">
    <div class="nav" :style="navstyle">
      <div class="switch" :style="switchstyle" @click="openControl()">
        <span class="iconfont icon-cc-pointer-left"></span>
      </div>
      <div class="btn">
        <div class="btn-item"></div>
        <div class="btn-item"></div>
        <div class="btn-item"></div>
      </div>
      <div class="icon">
        <div class="icon-img">
          <img src="../assets/headimg.png" alt="111" />
        </div>
        <div class="icon-con" :style="iconconstyle">
          <p>Good Day</p>
          <h2>{{ username }}</h2>
        </div>
      </div>
      <div class="line" :style="linestyle"></div>
      <div class="title">
        <p>Menu</p>
      </div>

      <div class="menu" :style="linestyle">
        <div class="item">
          <div class="light"></div>
          <div class="licon"><span class="iconfont icon-wenjian"></span></div>
          <div class="con" :style="constyle">Dashboard</div>
          <div class="ricon" :style="riconstyle">
            <span class="iconfont icon-shezhi"></span>
          </div>
        </div>
        <div class="item">
          <div class="light"></div>
          <div class="licon"><span class="iconfont icon-qipao1"></span></div>
          <div class="con" :style="constyle">Products</div>
          <div class="ricon" :style="riconstyle"></div>
        </div>
        <div class="item">
          <div class="light"></div>
          <div class="licon"><span class="iconfont icon-shexiang1"></span></div>
          <div class="con" :style="constyle">Campaigns</div>
          <div class="ricon" :style="riconstyle"></div>
        </div>
        <div class="item">
          <div class="light"></div>
          <div class="licon"><span class="iconfont icon-xiaolian"></span></div>
          <div class="con" :style="constyle">Sales</div>
          <div class="ricon" :style="riconstyle">
            <span class="iconfont icon-caidan1"></span>
          </div>
        </div>
        <div class="item">
          <div class="light"></div>
          <div class="licon"><span class="iconfont icon-shexiang"></span></div>
          <div class="con" :style="constyle">Discount</div>
          <div class="ricon" :style="riconstyle"></div>
        </div>
        <div class="item">
          <div class="light"></div>
          <div class="licon"><span class="iconfont icon-wenjian1"></span></div>
          <div class="con" :style="constyle">Payouts</div>
          <div class="ricon" :style="riconstyle"></div>
        </div>
      </div>
      <div class="line" :style="linestyle"></div>
      <div class="title">
        <p>Server</p>
      </div>
      <div class="serve" :style="linestyle">
        <div class="item">
          <div class="light"></div>
          <div class="licon"><span class="iconfont icon-caidan"></span></div>
          <div class="con" :style="constyle">Software</div>
          <div class="ricon" :style="riconstyle">
            <span class="iconfont icon-Dashboard"></span>
          </div>
        </div>
        <div class="item">
          <div class="light"></div>
          <div class="licon"><span class="iconfont icon-renqun"></span></div>
          <div class="con" :style="constyle">Chat</div>
          <div class="ricon" :style="riconstyle"></div>
        </div>
        <div class="item">
          <div class="light"></div>
          <div class="licon"><span class="iconfont icon-sousuo"></span></div>
          <div class="con" :style="constyle">Intercom</div>
          <div class="ricon" :style="riconstyle">
            <span class="iconfont icon-caidan1"></span>
          </div>
        </div>
        <div class="item">
          <div class="light"></div>
          <div class="licon"><span class="iconfont icon-gengduo-a"></span></div>
          <div class="con" :style="constyle">Setting</div>
          <div class="ricon" :style="riconstyle"></div>
        </div>
      </div>
    </div>
    <div class="workspace">
      <h1>workspace</h1>
      <RouterView />
    </div>
  </div>
</template>
<style scoped>
@import url("../assets/css.css");
@import url("../assets/font/iconfont.css");
@import url("../assets/font1/iconfont.css");
@import url("../assets/font2/iconfont.css");

.licon .iconfont {
  font-size: 26px;
}
.workspace {
  height: calc(100vh - 40px);
  width: 100%;
  background: rgba(0, 0, 0, 0.8);
  margin-left: 48px;
  border-top-left-radius: 20px;
  border-bottom-left-radius: 20px;
  padding: 20px;
}
/* .switch {
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  right: -25px;
  top: 50%;
} */
</style>
