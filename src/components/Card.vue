<template>
  <div class="frame-big">
    <div class="frame">
      <div class="image">
        <img v-bind:src=images[0]
             width="90%"
             alt="Product image"
        >
      </div>
      <div class="grade_price">
        <div class="grade">
          <div class="grade_numbers align_center">
            {{ rating }}
            <svg width="15" height="14" viewBox="0 0 15 14" fill="none"
                 xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd" clip-rule="evenodd"
                    d="M7.69807 1L9.69699 4.94953L14.1671 5.58675L10.9326 8.65931L11.6959 13L7.69807
                                   10.9495L3.70022
                                  13L4.46357 8.65931L1.22906 5.58675L5.69915 4.94953L7.69807 1V1Z" stroke="white"
                    stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
        </div>
        <div class="price">
          {{ price }}
        </div>
      </div>
      <div class="name">
        {{ title }}
      </div>
      <div class="note">
        {{ category }}  >>  {{ brand }}
      </div>
      <div class="button_wrapper">
        <button class="button button_wishlist align_center">
          <svg width="18" height="15" viewBox="0 0 18 15" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd"
                  d="M15.4479 2.14929C14.7031 1.41343 13.6926 1 12.6389 1C11.5853 1 10.5748 1.41343
                                  9.82993
                                   2.14929L9.06449 2.90512L8.29906 2.14929C6.74769 0.61741 4.23242 0.617411 2.68105
                                   2.14929C1.12967 3.68118 1.12967 6.16485 2.68105 7.69674L3.44648 8.45256L9.06449
                                   14L14.6825 8.45256L15.4479 7.69674C16.1932 6.96122 16.6119 5.96344 16.6119
                                   4.92302C16.6119 3.88259 16.1932 2.88481 15.4479 2.14929Z" stroke="black"
                  stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
          WISHLIST
        </button>
        <button class="button button_cart align_center">
          <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path opacity="0.737212" fill-rule="evenodd" clip-rule="evenodd"
                  d="M4.52471 1L1.6496 4.6V17.2C1.6496 18.1941 2.50775 19 3.56634 19H16.9835C18.0421 19
                                  18.9003 18.1941 18.9003 17.2V4.6L16.0252 1H4.52471Z" stroke="white" stroke-width="2"
                  stroke-linecap="round" stroke-linejoin="round"/>
            <g transform="translate(5,8)">
              <svg width="10" height="5" viewBox="0 0 10 5" fill="none"
                   xmlns="http://www.w3.org/2000/svg">
                <path opacity="0.737212" d="M8.58757 1C8.58757 2.65685 6.89808 4 4.81399 4C2.7299
                                 4 1.04041
                                2.65685 1.04041 1" stroke="white" stroke-width="2" stroke-linecap="round"
                      stroke-linejoin="round"/>
              </svg>
            </g>
            <g transform="translate(0,4)">
              <svg width="20" height="3" viewBox="0 0 20 3" fill="none"
                   xmlns="http://www.w3.org/2000/svg">
                <path opacity="0.737212" d="M1.6496 1.5H18.9003" stroke="white" stroke-width="2"
                      stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </g>
          </svg>
          ADD TO CART
        </button>
      </div>
    </div>
  </div>
</template>

<script>

import {
  defineComponent,
  inject
} from 'vue';

export default defineComponent({
  components: {

  },
  props: {
    id: {
      type: String,
      default: ''
    },
    images: {
      type: Array,
      default: () => []
    },
    title: {
      type: String,
      default: ''
    },
    rating: {
      type: Number,
      default: 0
    },
    price: {
      type: Number,
      default: 0
    },
    category: {
      type: String,
      default: ''
    },
    brand: {
      type: String,
      default: ''
    }
  },
  setup(props, { emit }) {


    return {

    }
  }
})
</script>

<style scoped>
* {
  font-family: Montserrat, serif;
  font-style: normal;
}

.frame-big {
  max-width: 100%;
  height: 486px;
}

.frame {
  display: grid;
  grid-template-columns: 100%;
  grid-template-rows:  334px 31px 38px 38px 45px;
  background: #FFFFFF;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.135216);
  border-radius: 8px;
  width: 100%;
}

.image {
  text-align: center;
  align-self: center;
}

.image img {
  max-height: 300px;
  max-width: 90%;
  min-width: 90%;
}

.grade_price {
  display: grid;
  grid-template-columns: 50% 50%;
}

.grade {
  display: grid;
  width: 33%;
  height: 30px;
  background: #6F64F8;
  border-radius: 3px;
  margin-left: 6%;
}

.grade_numbers {
  font-weight: normal;
  font-size: 14px;
  line-height: 17px;
  color: #FFFFFF;
  grid-template-columns: 45% 20%;
}

.price {
  display: grid;
  align-items: center;
  font-weight: normal;
  font-size: 18px;
  line-height: 21px;
  color: #2C2C2C;
  text-align: end;
  padding-right: 6%;
  justify-content: flex-end;
}

.name {
  font-weight: normal;
  font-size: 16px;
  line-height: 19px;
  color: #2C2C2C;
  padding-left: 3%;
  align-self: end;
}

.note {
  font-weight: 300;
  font-size: 12px;
  line-height: 14px;
  color: #2C2C2C;
  padding-left: 3%;
}

.button_wrapper {
  display: grid;
  grid-template-columns: 50% 50%;
}

.button {
  font-weight: 600;
  font-size: 14px;
  line-height: 18px;
  border: none;
}

.button_wishlist {
  color: #2C2C2C;
  background: #EDEDED;
  border-radius: 0 0 0 8px;
  grid-template-columns: 1px 100px;
}

.button_cart {
  color: #FFFFFF;
  background: #6F64F8;
  border-radius: 0 0 8px 0;
  grid-template-columns: 35px 111px;
}

.align_center {
  display: grid;
  place-items: center;
  justify-content: center;
  align-items: center;
}

</style>
