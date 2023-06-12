<template>
  <div class="result">
    <div class="progress">
        <div class="bar"></div>
        <div class="status"> {{ totalCorrect }} question(s) are correct</div>
    </div>
        <div class="title" >{{results[resultIndex].title}}</div>
        <div class="desc">
            {{results[resultIndex].desc}}
        </div>
    </div>
</template>

<script>
export default {
    props: ['results','totalCorrect'],
    computed:{
        resultIndex(){
            let index = 0;
            this.results.forEach((e,i) => {
                if(e.min <= this.totalCorrect && this.totalCorrect <= e.max){
                    index = i
                }
            });
            return index;
        }
    }

}
</script>

<style>

</style>