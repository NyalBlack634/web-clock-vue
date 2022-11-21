<script setup>
    defineProps(['time']);
</script>

<template>
    <div class="clock-time"><p>{{time}}</p></div>
</template>

<style>
/* 時間のスタイル */
.clock-time {
  font-size: 100px;
}

/* 文字サイズ調整 */
@media screen and (max-width: 500px){
    .clock-time {
        font-size: 20vw;
    }
}
</style>