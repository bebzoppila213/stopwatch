<template>
  <div class="stopwatch">
    <div @click="$emit('stopwatchAddClick')" role="button" class="stopwatch-new">
      <img :src="addImg" alt="Добавить" />
    </div>
  </div>
</template>

<script>
import AddImg from "assets/add.png"
export default {
    
    data: () => {
        return{
            addImg: AddImg
        }
    }
}
</script>