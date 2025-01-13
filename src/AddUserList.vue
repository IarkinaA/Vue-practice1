<template>
  <div>
    <div> <input type="text" v-model="category"> category</div>
    <div><input type="text" v-model="value"> value</div>
    <div><input type="text" v-model="date"> date</div>
    
    <button @click="saveClick">Save</button>

  </div>
</template>

<script>
export default {
  name: 'AddUserList',

  data() {
    return {
      category: '',
      value: '',
      date: '',
    };
  },

   methods: {
    saveClick() {
        const data = {
           value: +this.value,
           category: this.category,
           date: this.date,
        }
        // Передаем объект data в родительский объект
        this.$emit('addNewPay', data)
    }
  },
};
</script>