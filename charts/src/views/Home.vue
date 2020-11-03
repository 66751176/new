<template>
  <div class="home">
    <div>
      <bar></bar>
    </div>
    <div>
      <bars></bars>
    </div>
    <div>
      <myline></myline>
    </div>
    <div>
      <mypie></mypie>
    </div>
  </div>
</template>

<script>
import bar from "../components/chart/bar";
import bars from "../components/chart/bars";
import myline from "../components/chart/line";
import mypie from "../components/chart/mypie";

export default {
  name: "Home",
  components: { bar, bars, myline, mypie },
};
</script>
<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
.home {
  display: flex;
  flex-wrap: wrap;
  width: 100%;
  background: #f3f3f4;
}
.home > div {
  box-sizing: border-box;
  width: 50%;
  padding: 20px;
  background: #fff;
  border: 10px solid #f3f3f4;
  border-bottom: 0;
}
.home > div:nth-child(2n -1) {
  border-right: 0;
}
</style>
