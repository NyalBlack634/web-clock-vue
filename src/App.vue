<script setup>
  import DateView from "./components/DateView.vue"
  import TimeView from "./components/TimeView.vue"
  import { onMounted, ref } from "vue"

  let today = ref("Loading");
  let time = ref("Loading");

  const clock = () =>{
    // 現在の日時・時刻の情報を取得
    const d = new Date();

    // 年を取得
    let year = d.getFullYear();
    // 月を取得
    let month = d.getMonth() + 1;
    // 日を取得
    let date = d.getDate();
    // 曜日を取得
    let dayNum = d.getDay();
    const weekday = ["SUN", "MON", "TUE", "WED", "THU", "FRI", "SAT"];
    let day = weekday[dayNum];
    // 時を取得
    let hour = d.getHours();
    // 分を取得
    let min = d.getMinutes();
    // 秒を取得
    let sec = d.getSeconds();

    // 1桁の場合は0を足して2桁に
    month = month < 10 ? "0" + month : month;
    date = date < 10 ? "0" + date : date;
    hour = hour < 10 ? "0" + hour : hour;
    min = min < 10 ? "0" + min : min;
    sec = sec < 10 ? "0" + sec : sec;

    // 日付・時刻の文字列を作成
    today.value = `${year}.${month}.${date} ${day}`;
    time.value = `${hour}:${min}:${sec}`;
  } 

  onMounted(() => {
    setInterval(clock, 1000);
  })

</script>

<template>
  <div class="clock">
    <DateView :today=today />
    <TimeView :time=time />
  </div>
</template>


<style>
@import url("https://fonts.googleapis.com/css2?family=Share+Tech+Mono&display=swap");

/* 全体を囲うコンテナー */
#app {
  width: 100%;
  height: 100vh;
  background-color: #15151e;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

/* 時計の共通スタイル */
.clock {
  font-family: 'Share Tech Mono', monospace;
  color: #daf6ff;
  text-shadow: 0 0 20px #0aafe6;
  line-height: 1.2;
  text-align: center;
}

</style>
