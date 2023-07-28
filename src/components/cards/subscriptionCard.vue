<template>
  <div class="subCard" :class="isSelectedPack ? 'selectedSubCard' : ''">
    <div class="selected-box" v-if="isSelectedPack">
      <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 10.3 10.596">
        <path
          id="Path_5478"
          data-name="Path 5478"
          d="M2909.139,3526.383c-.075-.01,2.781,3.814,2.781,3.814l4.552-7.632"
          transform="translate(-2907.887 -3520.85)"
          fill="none"
          stroke="#fff"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2.5"
        />
      </svg>
    </div>
    <div class="card-bg-img">
      <span class="discount-badge custom-red-bg" v-show="packageData.discountPercent">
        %{{ packageData.discountPercent }}
      </span>
      <img class="xo-img" src="/images/cardHeader/xo.png" alt="" />
      <img class="card-header-img" :src="`/images/${packageData.id}.png`" alt="" />
    </div>
    <!--title-->
    <span class="heading">
      {{ packageData.name }}
    </span>
    <!--price-->

    <div class="price-main-container w-100">
      <span
        class="price-before-discount price-inner-container"
        v-show="packageData.discountPercent"
      >
        {{ priceConvert }}
      </span>

      <div class="flex w-100">
        <span class="price text-primary">
          {{ calculatedDiscountedPriceOrPurePrice }}
        </span>
        <span> تومان/ماهانه </span>
      </div>
    </div>
    <!--description data-->
    <div class="w-100">
      <div class="flex custom-margin-bottom">
        <!--Traffic-->
        <div class="flex">
          <svg
            id="hdd"
            xmlns="http://www.w3.org/2000/svg"
            width="14.16"
            height="17.402"
            viewBox="0 0 14.16 17.402"
          >
            <path
              id="XMLID_376_"
              d="M47.5,0V17.4H61.66V0ZM60.637,16.378H48.524V1.024H60.637Z"
              transform="translate(-47.5)"
              fill="#93b2b2"
            />
            <path
              id="XMLID_390_"
              d="M210.033,160.622a1.589,1.589,0,1,0-1.589-1.589A1.59,1.59,0,0,0,210.033,160.622Zm0-2.153a.565.565,0,1,1-.565.565A.565.565,0,0,1,210.033,158.469Z"
              transform="translate(-202.953 -152.073)"
              fill="#93b2b2"
            />
            <path
              id="XMLID_391_"
              d="M96.474,53.524h.011a.512.512,0,1,0,0-1.024h-.011a.512.512,0,1,0,0,1.024Z"
              transform="translate(-94.308 -50.709)"
              fill="#93b2b2"
            />
            <path
              id="XMLID_392_"
              d="M96.306,429.024h.011a.512.512,0,1,0,0-1.024h-.011a.512.512,0,1,0,0,1.024Z"
              transform="translate(-94.146 -413.396)"
              fill="#93b2b2"
            />
            <path
              id="XMLID_393_"
              d="M384.679,53.524h.011a.512.512,0,0,0,0-1.024h-.011a.512.512,0,0,0,0,1.024Z"
              transform="translate(-372.679 -50.709)"
              fill="#93b2b2"
            />
            <path
              id="XMLID_394_"
              d="M384.69,428h-.011a.512.512,0,0,0,0,1.024h.011a.512.512,0,0,0,0-1.024Z"
              transform="translate(-372.679 -413.396)"
              fill="#93b2b2"
            />
            <path
              id="XMLID_398_"
              d="M145,378.154h7.507v-2.821H145Zm1.024-1.8h5.459v.773h-5.459Z"
              transform="translate(-141.673 -362.526)"
              fill="#93b2b2"
            />
            <path
              id="XMLID_469_"
              d="M105.716,61.95l-.776.776.724.724.788-.788a5.145,5.145,0,1,0-.736-.712Zm3.919-7.426a4.112,4.112,0,1,1-2.454,7.409l.47-.47-.724-.724-.485.485a4.109,4.109,0,0,1,3.192-6.7Z"
              transform="translate(-102.555 -51.675)"
              fill="#93b2b2"
            />
          </svg>
          <span> Trafic: </span>
          <span class="text-primary">
            {{ packageData.trafficCapacity }}
          </span>
        </div>
        <!--Ram-->
        <div class="flex">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="14.967"
            height="17.182"
            viewBox="0 0 14.967 17.182"
          >
            <path
              id="Path_5417"
              data-name="Path 5417"
              d="M46.121,10.168a.5.5,0,0,0,.5-.5v-.57h.839a.5.5,0,1,0,0-1.007h-.839v-.57a.5.5,0,0,0-.5-.5H44.477V5.6h1.644a.5.5,0,0,0,.5-.5V4.53h.839a.5.5,0,1,0,0-1.007h-.839v-.57a.5.5,0,0,0-.5-.5H44.477V1.007A1.008,1.008,0,0,0,43.47,0H37.5A1.008,1.008,0,0,0,36.49,1.007V2.45H34.846a.5.5,0,0,0-.5.5v.57H33.5a.5.5,0,0,0,0,1.007h.839V5.1a.5.5,0,0,0,.5.5H36.49V7.014H34.846a.5.5,0,0,0-.5.5v.57H33.5a.5.5,0,0,0,0,1.007h.839v.57a.5.5,0,0,0,.5.5H36.49v1.409H34.846a.5.5,0,0,0-.5.5v.57H33.5a.5.5,0,1,0,0,1.007h.839v.57a.5.5,0,0,0,.5.5H36.49v1.443A1.008,1.008,0,0,0,37.5,17.182H43.47a1.008,1.008,0,0,0,1.007-1.007V14.732h1.644a.5.5,0,0,0,.5-.5v-.57h.839a.5.5,0,1,0,0-1.007h-.839v-.57a.5.5,0,0,0-.5-.5H44.477V10.168Zm-.5-2.148V9.161H44.477V8.02Zm0-4.564V4.6H44.477V3.456ZM35.349,4.6V3.456H36.49V4.6Zm0,4.564V8.02H36.49V9.161Zm0,4.564V12.584H36.49v1.141Zm8.121,2.45H37.5V1.007H43.47C43.471,16.537,43.473,16.175,43.47,16.175Zm2.148-3.591v1.141H44.477V12.584Z"
              transform="translate(-33)"
              fill="#93b2b2"
            />
          </svg>
          <span> RAM: </span>
          <span class="text-primary">
            {{ packageData.ramCapcity }}
            <span class="text-primary"> گیگ </span>
          </span>
        </div>
      </div>
      <div class="flex">
        <!--CPU-->
        <div class="flex">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="16.878"
            height="16.878"
            viewBox="0 0 16.878 16.878"
          >
            <g id="Group_3224" data-name="Group 3224" transform="translate(-216.751 -428.438)">
              <g id="Group_3222" data-name="Group 3222" transform="translate(221.088 432.775)">
                <g id="Group_2576" data-name="Group 2576">
                  <path
                    id="Path_5415"
                    data-name="Path 5415"
                    d="M137.49,129.753h-7.267a.47.47,0,0,0-.469.469v7.267a.47.47,0,0,0,.469.469h7.267a.47.47,0,0,0,.469-.469v-7.267A.47.47,0,0,0,137.49,129.753Zm-.469,7.267h-6.329v-1.758h.938a.469.469,0,1,0,0-.938h-.938v-.938h1.875a.469.469,0,0,0,0-.938h-1.875v-1.758h6.329Z"
                    transform="translate(-129.754 -129.753)"
                    fill="#93b2b2"
                  />
                </g>
              </g>
              <g id="Group_3223" data-name="Group 3223" transform="translate(216.751 428.438)">
                <g id="Group_2578" data-name="Group 2578">
                  <path
                    id="Path_5416"
                    data-name="Path 5416"
                    d="M16.878,7.22a.47.47,0,0,0-.469-.469h-1.5V5.274h1.5a.469.469,0,1,0,0-.938h-1.5V3.329a1.361,1.361,0,0,0-1.36-1.36H12.541V.469a.469.469,0,0,0-.938,0v1.5H10.1V.469a.469.469,0,0,0-.938,0v1.5h-1.5V.469a.469.469,0,0,0-.938,0v1.5H5.274V.469a.469.469,0,0,0-.938,0v1.5H3.329a1.361,1.361,0,0,0-1.36,1.36V4.337H.469a.469.469,0,0,0,0,.938h1.5v1.5H.469a.469.469,0,1,0,0,.938h1.5v1.5H.469a.469.469,0,0,0,0,.938h1.5V11.6H.469a.469.469,0,0,0,0,.938h1.5v1.008a1.361,1.361,0,0,0,1.36,1.36H4.337v1.5a.469.469,0,1,0,.938,0v-1.5h1.5v1.5a.469.469,0,0,0,.938,0v-1.5h1.5v1.5a.469.469,0,1,0,.938,0v-1.5H11.6v1.5a.469.469,0,1,0,.938,0v-1.5h1.008a1.361,1.361,0,0,0,1.36-1.36V12.541h1.5a.469.469,0,1,0,0-.938h-1.5V10.1h1.5a.469.469,0,1,0,0-.938h-1.5v-1.5h1.5v.023A.47.47,0,0,0,16.878,7.22Zm-2.883,6.329h-.023a.42.42,0,0,1-.422.422H3.329a.42.42,0,0,1-.422-.422V3.329a.42.42,0,0,1,.422-.422H13.573a.42.42,0,0,1,.422.422V13.549Z"
                    fill="#93b2b2"
                  />
                </g>
              </g>
            </g>
          </svg>
          <span> CPU: </span>
          <span class="text-primary">
            {{ packageData.ramCapcity }}
            <span class="text-primary"> هسته </span>
          </span>
        </div>
        <!--storage SSD-->
        <div class="flex">
          <svg
            id="hdd"
            xmlns="http://www.w3.org/2000/svg"
            width="14.16"
            height="17.402"
            viewBox="0 0 14.16 17.402"
          >
            <path
              id="XMLID_376_"
              d="M47.5,0V17.4H61.66V0ZM60.637,16.378H48.524V1.024H60.637Z"
              transform="translate(-47.5)"
              fill="#93b2b2"
            />
            <path
              id="XMLID_390_"
              d="M210.033,160.622a1.589,1.589,0,1,0-1.589-1.589A1.59,1.59,0,0,0,210.033,160.622Zm0-2.153a.565.565,0,1,1-.565.565A.565.565,0,0,1,210.033,158.469Z"
              transform="translate(-202.953 -152.073)"
              fill="#93b2b2"
            />
            <path
              id="XMLID_391_"
              d="M96.474,53.524h.011a.512.512,0,1,0,0-1.024h-.011a.512.512,0,1,0,0,1.024Z"
              transform="translate(-94.308 -50.709)"
              fill="#93b2b2"
            />
            <path
              id="XMLID_392_"
              d="M96.306,429.024h.011a.512.512,0,1,0,0-1.024h-.011a.512.512,0,1,0,0,1.024Z"
              transform="translate(-94.146 -413.396)"
              fill="#93b2b2"
            />
            <path
              id="XMLID_393_"
              d="M384.679,53.524h.011a.512.512,0,0,0,0-1.024h-.011a.512.512,0,0,0,0,1.024Z"
              transform="translate(-372.679 -50.709)"
              fill="#93b2b2"
            />
            <path
              id="XMLID_394_"
              d="M384.69,428h-.011a.512.512,0,0,0,0,1.024h.011a.512.512,0,0,0,0-1.024Z"
              transform="translate(-372.679 -413.396)"
              fill="#93b2b2"
            />
            <path
              id="XMLID_398_"
              d="M145,378.154h7.507v-2.821H145Zm1.024-1.8h5.459v.773h-5.459Z"
              transform="translate(-141.673 -362.526)"
              fill="#93b2b2"
            />
            <path
              id="XMLID_469_"
              d="M105.716,61.95l-.776.776.724.724.788-.788a5.145,5.145,0,1,0-.736-.712Zm3.919-7.426a4.112,4.112,0,1,1-2.454,7.409l.47-.47-.724-.724-.485.485a4.109,4.109,0,0,1,3.192-6.7Z"
              transform="translate(-102.555 -51.675)"
              fill="#93b2b2"
            />
          </svg>
          <span> SSD: </span>
          <span class="text-primary row-reverse">
            <span class="text-primary"> گیگ </span>
            {{ packageData.storageCapacity }}
          </span>
        </div>
      </div>
    </div>
    <div class="select-wrapper">
      <span class="dropdown-chevron">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="8.079"
          height="4.747"
          viewBox="0 0 8.079 4.747"
        >
          <path
            id="Path_6485"
            data-name="Path 6485"
            d="M180.417,524.8l3.686,3.686,3.686-3.686"
            transform="translate(-180.063 -524.451)"
            fill="none"
            stroke="#707070"
            stroke-width="1"
          />
        </svg>
      </span>
      <select class="w-100 duration-btn">
        <option value="duration">{{ packageData.duration }}</option>
      </select>
    </div>
    <primary-btn :isSelectedPack="isSelectedPack" @selected="setSelectedItem"></primary-btn>
  </div>
</template>
<script setup>
import PrimaryBtn from '@/components/buttons/PrimaryBtn.vue'
import { computed, ref } from 'vue'
//variables
const toggleDropdown = ref(false)
// props
const props = defineProps(['packageData', 'isSelectedPack'])

// emits
const emit = defineEmits(['getSelectedPackId'])

// functions
function setSelectedItem() {
  const packageDataId = props.packageData.id
  emit('getSelectedPackId', packageDataId)
}

// converting the price from RLs to Toman
const priceConvert = computed(() => {
  const price = props.packageData.price
  return new Intl.NumberFormat('fa-IR').format(price)
})

const calculatedDiscountedPriceOrPurePrice = computed(() => {
  if (props.packageData.discountPercent) {
    return new Intl.NumberFormat('fa-IR').format(
      props.packageData.price - (props.packageData.price * props.packageData.discountPercent) / 100
    )
  } else {
    return priceConvert
  }
})
</script>

<style scoped>
.discount-badge {
  width: 2.4rem;
  height: 2.4rem;
  font-size: 14px;
  position: absolute;
  top: 1rem;
  right: 4.4rem;
  color: #ffffff;
  border: #000000;
  border-radius: 200rem;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 3px solid #000000;
  z-index: 10 !important;
}
.price-inner-container {
  margin-top: 2rem;
}
.price-main-container {
  position: relative;
}
.price-before-discount {
  font-size: large;
  color: rgba(245, 48, 127, 1);
  text-decoration: line-through;
}
.selected-box {
  background-color: #53c786;
  width: 3rem;
  height: 3rem;
  display: flex;
  align-items: center;
  justify-content: center;
  position: absolute;
  top: 0;
  left: 0;
  border-top-left-radius: 10px;
  border-bottom-right-radius: 10px;
}
</style>
