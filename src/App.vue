<template>
<div id="app">
  <!-- Для получения данных из props биндим данные items из paymentList. Эти данные из props перекинуться в items -->
  <PaymentsDisplay :items="paymentList"  />
  <AddUserList @addNewPay="addNewPay" />

</div>

</template>

<script>
import AddUserList from './AddUserList.vue';
import PaymentsDisplay from './components/PaymentsDisplay.vue';



export default {
  name: 'App',
  components: {
        PaymentsDisplay,
        AddUserList
      },
  // Нужно создать св-ва, которые принимали бы массив из бекэнда(у нас храниться в Эпп вью, а так же то, что вводит сам пользователь)
  data() {
    return {
      paymentList: [],
      // В paymentList нужно передать данные с бекэнда, это будет осуществляться внутри св-ва 'created'.
      
    };
  },
  methods: {
        // Какие-то данные, полученные с бекэнда. Храним в Апп вью, чтобы иметь общий доступ к ним.
    fetchData() {
        return [
            {
                date: '28.05.2024',
                category: 'Food',
                value: 45
            },
            {
                date: '30.05.2024',
                category: 'Transport',
                value: 70,
            },
            {
                date: '30.05.2024',
                category: 'Clothes',
                value: 78
            },
        ]
    },
    addNewPay(data) {
      this.paymentList.push(data)
    }
  },
  created() {
    // В момент запуска приложения, должны придти данные с бекэнда. 
    // Т.е. изначально у нас нет данных, как только мы создаем приложение, он должен наполниться данными из бекэнда.
    this.paymentList = this.fetchData()
  }


}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
