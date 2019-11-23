<template>
  <div class="body-container">
    <h1>Contact list of 109 Nigerian Senetors</h1>
    <input
      v-model="searchValue"
      @keyup="searchAction"
      type="search"
      name="search"
      placeholder="Search by state"
    />
    <div v-for="senator in senatorList" :key="senator.state">
      <h1>{{ senator.state }}</h1>
      <div class="row">
        <CardComponent
          v-for="singleSenator in senator.senators"
          :key="singleSenator.name"
          :detail="singleSenator"
        />
      </div>
    </div>
  </div>
</template>

<script>
import CardComponent from "@/components/CardComponent.vue";
import list from "../senator-list";

export default {
  name: "home",
  components: {
    CardComponent
  },
  data() {
    return {
      senatorList: list,
      searchValue: ""
    };
  },
  methods: {
    searchAction() {
      if (this.searchValue === "" || this.searchValue === " ") {
        this.senatorList = list;
      } else {
        let newList = this.senatorList.filter(senator =>
          senator.state.toLowerCase().includes(this.searchValue.toLowerCase())
        );
        this.senatorList = newList;
      }
    }
  }
};
</script>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.row {
  padding: 15px;
  display: -webkit-flex;
  display: flex;
  -webkit-flex-flow: row;
  flex-flow: row;
  flex-wrap: wrap;
}
input[type="search"] {
  width: 60%;
  margin-bottom: 30px;
  margin-top: 30px;
  font-size: 20px;
}
</style>
