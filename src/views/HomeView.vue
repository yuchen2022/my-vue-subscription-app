<template>
  <main class="main-container">
    <div v-if="apiData && !isLoading" class="subCardWrapper">
      <subscription-card
        v-for="item in apiData"
        :key="item.id"
        :packageData="item"
        :isSelectedPack="isPackSelected(item.id)"
        @getSelectedPackId="setSelectedPackId"
      />
    </div>
    <div class="loadingWrapper" v-else-if="isLoading">
      <svg id="page-loader">
        <circle cx="75" cy="75" r="20"></circle>
        <circle cx="75" cy="75" r="35"></circle>
        <circle cx="75" cy="75" r="50"></circle>
        <circle cx="75" cy="75" r="65"></circle>
      </svg>
    </div>
    <div class="ErrorMessageWrapper" v-else-if="showErrorMessage">
      <img src="/src/assets/images/Group%20515.png" />
      <span> خطای ارتباط با سرور </span>
    </div>
  </main>
</template>
<script setup>
import SubscriptionCard from '@/components/cards/subscriptionCard.vue'
import { ref } from 'vue'
import axios from 'axios'

//variables
const apiData = ref()
const apiKey = ref('PMAK-61325d70088f41003cdecd8a-dcb8940943ee694609eb0faf438043248d')
const isLoading = ref(null)
const showErrorMessage = ref(null)
const selectedPackId = ref(null)

//functions

function setSelectedPackId(id) {
  selectedPackId.value = id
}

function isPackSelected(packId) {
  if (packId == selectedPackId.value) {
    return true
  }
  return false
}

function getApiData() {
  isLoading.value = true
  axios
    .get('https://e6f6217f-1eb5-4d47-a974-369e92dca4e0.mock.pstmn.io/getpackageinfo', apiKey.value)
    .then((response) => {
      isLoading.value = false
      showErrorMessage.value = false
      apiData.value = response?.data?.data
    })
    .catch((error) => {
      isLoading.value = false
      showErrorMessage.value = true
      console.log(error)
    })
}
getApiData()
</script>
<style scoped>
.main-container {
  margin: 3rem 0;
  padding: 0 3rem;
}
</style>
