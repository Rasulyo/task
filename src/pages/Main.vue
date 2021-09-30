<template>
  <div>
    <Index
      v-for="product in filterProducts"
      :key="product.id"
      :products_data='product'
    />
    <h1>
      Hello every body
    </h1>
    <h2>
      How are you
    </h2>
    <h3>
      I'm fine
    </h3>
  </div>
</template>

<script>
import Index from './Index.vue'
import { defineComponent } from 'vue';
import data from '../../data.json'
import names from '../../names.json'

export default defineComponent({
  name: 'Main',
  components: {
    Index
  },
  data(){
    return{
        sortedId: [],
        sortedProducts: [],
        dataBaseProducts:  {...names}

    }
  },
  computed: {
    filterProducts(){
      let arr = data.Value.Goods.map(item => {
        this.sortedId
        let sort = sort.push(item.G)
        return item
      })
      let list = []
      list.push(this.dataBaseProducts)
      list.map( item => {
        return item === this.sortedId
      } )

      console.log(list, 'list')
      arr.map(item => console.log(item, 'alf'))
     return arr
    }


  },
  methods: {
    getAll(){
     // console.log(dataBase)
    },
    sortById(){
        data.Value.Goods.map(item => {
          // let value = item.G
          // console.log('item it"self', value)
          // console.log(...names , `${value}`)
        })
    },
  },
  mounted() {

  },
})
</script>
