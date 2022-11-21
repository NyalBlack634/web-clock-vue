<script setup>
    defineProps(['today']);
</script>

<template>
    <div class="clock-date"><p>{{today}}</p></div>
</template>

<style scoped>
/* 日付のスタイル */
.clock-date {
  font-size: 25px;
}

/* 文字サイズ調整 */
@media screen and (max-width: 500px){
    .clock-date {
        font-size: 5vw;
    }
}
</style>