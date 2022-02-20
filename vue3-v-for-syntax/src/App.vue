<template>
  <ul>
    <!-- 타언어 for 문 과 같이 index 또 한 가져올 수 있다. -->
    <li
      v-for="(fruit,index) in fruits"
      :key="fruit">
      {{ fruit }}-{{ index + 1 }}
    </li>
  </ul>

  <button @click="handler">
    Click Me!!
  </button>

  <ul>
    <!-- 이 ul 태그 내부의 fruit는 newFruts 의 값으로 id,name으로 이루어져 있다는 점을 참고해 간단히 표현할 수 있다. -->
    <li
      v-for="{id, name} in newFruits"
      :key="id">
      {{ name }}-{{ id }}
    </li>
  </ul>
</template>

<script>
//shortid 패키지 import
import shortid from 'shortid'

export default {
  data(){
    return{
      fruits:['Apple','Banana','Cherry']
    }
  },
  computed: {
    newFruits(){
      //fruits배열을 map()함수를 통해 새로운 배열 데이터로 반환 => newFruits
      return this.fruits.map((fruit) => {
        return{
          // id: index,
          id: shortid.generate(), // shortid.generate()를 통해 고유한 아이디값 생성 가능
          name:fruit
        }
      })
    }
  },
  methods:{
    handler(){
      //배열에 값 추가 -> 반응성(데이터에 변경 사항이 있으면 화면이 바뀐다.)
      this.fruits.push('Orange')
    }
  }
}
</script>