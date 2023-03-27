<template>
    <div class="stopwatch-menu">
        <div @click="$emit(`leftBtnСlick`)" role="button" class="stopwatch-button">
          <img  :src="leftBtnImg" alt="Кнопка 1" />
        </div>
        <div @click="$emit(`rightBtnСlick`)" role="button" class="stopwatch-button">
          <img :src="rightBtnImg" alt="Кнопка 2" />
        </div>
      </div>
</template>


<script>
export default {
    props: {
        leftBtnImg: String,
        rightBtnImg: String
    },
}
</script>
