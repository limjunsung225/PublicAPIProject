<template>
  <b-container v-if="houses && houses.length != 0" class="bv-example-row mt-3">
    <house-list-item v-for="(house, index) in houses" :key="index" :house="house" />
  </b-container>
  <b-container v-else class="bv-example-row mt-3">
    <b-row>
      <b-col><b-alert show>관광지가 없습니다.</b-alert></b-col>
    </b-row>
  </b-container>
</template>

<script>
import HouseListItem from "@/components/house/HouseListItem";
import { mapState } from "vuex";
const houseStore = "houseStore";

export default {
  name: "HouseList",
  components: {
    HouseListItem,
  },
  data() {
    return {};
  },
  computed: {
    ...mapState(houseStore, ["houses"]),
  },
};
</script>

<style></style>
