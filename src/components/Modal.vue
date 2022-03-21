<script>
  export default {
    props: ['state']
  };
  
</script>


<template>
  <div class="modal fade " id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog modal-dialog-centered modal-lg">
      <div class="modal-content">
        <div class="modal-header">
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>

        <div class="modal-body">
          <div v-for="item in state.SelectItemArr">
            <div class="w-64 h-72 pt-3.5 flex w-full">
              <img class="mb-1 h-64 float-left w-1/3" :src="item.picture.large" alt="userAvatar">
              <div class="float-right	w-2/3 pl-5">
                <div class="mb-2">Name : {{item.name.first}} {{item.name.last}}</div>
                <div class="mb-2">Phone : {{item.phone}}</div>
                <div class="mb-2">City : {{item.location.city}}</div>
                <div class="mb-2">State : {{item.location.state}}</div>
                <div class="mb-2">Age : {{item.dob.age}}</div>
                <div class="mb-2">Dob : {{item.dob.date}}</div>
                <div class="mb-2">Nat : {{item.nat}}</div>
                <div>Email : {{item.email}}</div>
              </div>
              
            </div>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>