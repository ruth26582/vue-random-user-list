<script>
  export default {
    props: ['state', 'changeList', 'changeCard', 'openMdal']
  }
</script>

<template>
  <div class="flex justify-end items-center mb-8 h-10">
    <select id="count"  class="mr-3 border-solid border-2 border-slate-900">
      <option>10</option>
      <option selected>30</option>
      <option>50</option>
    </select>
    <img src="../image/card.png" alt="card" class="w-8  mr-3 cursor-pointer hover:bg-blue-400 active:bg-blue-300" @click="changeCard">
    <img src="../image/list.png" alt="list" class="w-8  mr-3 cursor-pointer hover:bg-blue-400 active:bg-blue-300" @click="changeList">
  </div>

  <div id="card" class="allCard flex justify-between flex-wrap">
    <div class="mb-8 bg-blue-200 cursor-pointer" v-for="(item, index) in state.userList" data-bs-toggle="modal" data-bs-target="#exampleModal" @click="openMdal(item,index)">
      <div class="w-64 h-72 card-item">
        <img class="mb-1 h-48" :src="item.picture.large" alt="userAvatar">
        <div class="mb-2">Name : {{item.name.first}} {{item.name.last}}</div>
        <div class="mb-2">Phone : {{item.phone}}</div>
        <div class="mb-2">City : {{item.location.city}}</div>
      </div>
    </div>
  </div>

  <div id="list" class="allList">
    <div class="mb-8 bg-blue-200 cursor-pointer" v-for="(item, index) in state.userList" data-bs-toggle="modal" data-bs-target="#exampleModal" @click="openMdal(item,index)">
      <div class="w-full h-48 flex items-center leading-10">
        <div class="w-1/5">
          <img class="h-48 mr-7" :src="item.picture.large" alt="userAvatar">
        </div>
        <div class="mr-7 w-2/5">
          <div>Name : {{item.name.first}} {{item.name.last}}</div>
          <div>Phone : {{item.phone}}</div>
          <div>City : {{item.location.city}}</div>
          <div>State : {{item.location.state}}</div>
        </div>
        <div class="w-2/5">
          <div>Age : {{item.dob.age}}</div>
          <div>Dob : {{item.dob.date}}</div>
          <div>Nat : {{item.nat}}</div>
          <div>Email : {{item.email}}</div>
        </div>
      </div>
    </div>
  </div>
</template>