<script>
  import axios from 'axios';
  import { ref, reactive, onMounted } from 'vue';
  import List from './components/List.vue'
  import Modal from './components/Modal.vue';

  export default {
    components: {
      Modal,
      List
    },
    setup() {
      const state = reactive({
        userList: [],
        SelectItemArr: []
      });

      function changeCard() {
        document.getElementById("card").style.display="flex";
        document.getElementById("list").style.display="none";
      };

      function changeList() {
        document.getElementById("list").style.display="block";
        document.getElementById("card").style.display="none";
      };

      function openMdal(item, index) {
        state.SelectItemArr = []
        state.userList.forEach((element, key) => {
          if (index == key) {
            state.SelectItemArr.push(element)
          };
        });
      };
      
      onMounted(async () => {
        axios.get("https://randomuser.me/api/?results=10")
          .then((res) => {
            state.userList = res.data.results
          });
        document.getElementById("list").style.display="none";
      });

      return { state, changeCard, changeList, openMdal }
    },
  };

</script>


<template>
  <div class="mx-8 my-8">
    <List :state="state" :openMdal="openMdal" :changeCard="changeCard" :changeList="changeList" />
    <Modal :state="state" />
  </div>
</template>