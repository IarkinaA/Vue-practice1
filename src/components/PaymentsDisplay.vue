<template>
  <div>
    <div v-for="item in items" :key="item.id">
        {{ item }}
    </div>
  
  </div>
</template>

<script>
export default {
  name: 'PaymentsDisplay',
//   Для обмена данными м/ду компонентами используем св-во props
    props: {
        items: {
          type: Array,
          default() {
            return [];
          },
        },
        
    },
 
  data() {
    return {
      
    };
  },

  mounted() {
    
  },

  methods: {

   
  },
};
</script>

<style lang="css" scoped>

</style>