<template>
  <div class="main__left">
    <div class="main__left-filter">
      <p class="textFilter set-font">Filters</p>
      <div class="contButton">
        <button class="buttonFilter">
          <svg width="8" height="13" viewBox="0 0 8 13" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M6.79823 0.999718L1.01028 6.49446L6.77765 12.0108" stroke="black" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
          <svg width="8" height="13" viewBox="0 0 8 13" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M6.79823 0.999718L1.01028 6.49446L6.77765 12.0108" stroke="black" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </button>
      </div>
    </div>
    <div class="main__left-bar">
      <div class="categoryRange set-font">
        <p class="nameCategory set-font">Multi Range</p>

        <div id="dbl">
          <DoubleSlider
            min="0"
            max="10000"
            filter-name="Price"
          />
        </div>
        <div id="dblRating">
          <DoubleSlider
            min="0"
            max="5"
            filter-name="Rating"
          />
        </div>

      </div>
      <div class="line">
        <svg width="378" height="1" viewBox="0 0 378 1" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M0 0.5H377.456" stroke="#D6D6D6"/>
        </svg>
      </div>

      <div id="category">
        <FilterList title="Categories"
                    :list="categoriesList"
        />
      </div>

      <div class="line">
        <svg width="378" height="1" viewBox="0 0 378 1" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M0 0.5H377.456" stroke="#D6D6D6"/>
        </svg>
      </div>

      <div id="brand">
        <FilterList title="Brands"
                    v-bind:list="brandsList"
        />
      </div>

    </div>
    <div class="main__left-button">
      <button class="buttonClear set-font center_items">
        CLEAR ALL FILTERS
      </button>
    </div>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import FilterList from "@/components/FilterList";
import DoubleSlider from "@/components/DoubleSlider";
let mockCategories = [
  "Monitors",
  "Laptops",
  "Video cards",
  "Gaming keyboards",
  "Computer mouse",
  "SSD",
  "Sound cards",
  "RAM"
].map(item => {
  return {
    title: item,
    value: item.toLowerCase().replace(',', '_')
  }
});

let mockBrands = [
  "Asus",
  "Acer",
  "Apple",
  "Dell",
  "Dynamode",
  "Gigabyte",
  "Kingston",
  "Lenovo",
  "Logitech",
  "MSI",
  "BenQ",
  "A4Tech"
].map(item => {
  return {
    title: item,
    value: item.toLowerCase()
  }
});
export default defineComponent({
  components: {
    FilterList,
    DoubleSlider
  },
  props: {
    title: {
      type: String,
      default: ''
    },
    categoriesList: {
      type: Array,
      default: () => mockCategories
    },
    brandsList: {
      type: Array,
      default: () => mockBrands
    },
  },
  setup(props, { emit }) {

  }
})
</script>

<style>
.textFilter {
  font-weight: normal;
  font-size: 18px;
  line-height: 21px;
  color: #2C2C2C;
  display: grid;
  align-items: center;
}

.contButton {
  display: grid;
  align-items: center;
  justify-content: right;
}

.buttonFilter {
  background: #FFFFFF;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.135216);
  border-radius: 8px;
  width: 47px;
  height: 40px;
  border: none;
}

.main__left-bar {
  background: #FFFFFF;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.135216);
  border-radius: 8px;
  display: grid;
  grid-template-rows: 254px 20px 476px 20px auto;
}

.categoryRange {
  font-weight: 300;
  font-size: 16px;
  line-height: 32px;
  color: #2C2C2C;
  padding: 8% 8% 0 8%;
  width: 100%;
  /*border: black 1px solid;*/
  position: relative;
}

input[type='range'] {
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  /*width: 560px;*/
  position: relative;
  margin-left: 11%;
  top: 38%;
  bottom: 0;
  /*pointer-events: none;*/
  background-color: transparent;
}

.slider-track {
  width: 75%;
  height: 10px;
  position: relative;
  margin: auto;
  top: 50%;
  bottom: 0;
  border-radius: 5px;
  background-color: #EDEDED;
}
input[type="range"]::-webkit-slider-runnable-track {
  -webkit-appearance: none;
  height: 5px;
}
input[type="range"]::-moz-range-track {
  -webkit-appearance: none;
  height: 5px;
}
input[type="range"]::-ms-track {
  -webkit-appearance: none;
  height: 5px;
}
input[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none;
  height: 1.2em;
  width: 1.2em;
  background-color: #6F64F8;
  cursor: pointer;
  border-radius: 2px;
  pointer-events: auto;
}
input[type="range"]::-moz-range-thumb {
  -webkit-appearance: none;
  height: 1.2em;
  width: 1.2em;
  background-color: #6F64F8;
  cursor: pointer;
  border-radius: 2px;
}
input[type="range"]::-ms-thumb {
  -webkit-appearance: none;
  height: 1.2em;
  width: 1.2em;
  background-color: #6F64F8;
  cursor: pointer;
  border-radius: 2px;
  pointer-events: auto;
}
.values {
  background-color: #6F64F8;
  width: 55%;
  position: relative;
  margin: auto;
  border-radius: 5px;
  text-align: center;
  font-weight: 500;
  font-size: 25px;
  color: #f9f9f9;
  top: 25%;
}

.category {
  font-weight: 300;
  font-size: 16px;
  line-height: 32px;
  color: #2C2C2C;
  padding: 7% 0 0 8%;
}

.nameCategory {
  font-weight: 600;
  font-size: 18px;
  line-height: 22px;
  color: #2C2C2C;
}

.listCategory {
  display: grid;
  grid-template-columns: auto auto;
  align-items: center;
}

.valuesCategory > li {
  list-style-type:none;
  display: grid;
  justify-content: right;
  padding-right: 26%;
}

.main__left-button {
  display: grid;
  grid-template-columns: 100%;
  justify-content: center;
  align-items: flex-end;
}

.buttonClear {
  background: #6F64F8;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.135216);
  border-radius: 8px;
  font-weight: normal;
  font-size: 18px;
  line-height: 21px;
  color: #FFFFFF;
  height: 56px;
  border: none;
}

.buttonHeart {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.135216);
  border-radius: 8px;
  width: 47px;
  height: 40px;
  border: none;
  background: #6F64F8;
}

.main__right-search {
  max-width: 100%;
}

.gridContainer {
  display: grid;
  grid-template-columns: 32% 32% 32%;
  grid-template-rows: 486px 486px 486px;
  grid-gap: 28px;
  background: #F9F9F9;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.0778245);
  justify-content: center;
  align-items: center;
}

@media screen and (max-width: 1200px) {
  .gridContainer {
    grid-template-columns: 50% 50%;
  }
  .main__left {
    display: none;
  }
  .main {
    grid-template-columns: 100%;
  }
  .header__name {
    grid-template-columns: 16% 84%;
  }
  .header__menu {
    grid-template-columns: 5% 1% 1% 12% 1% 1% 16%;
    margin-left: 0.8%;
  }
}

@media screen and (max-width: 720px) {
  .gridContainer {
    grid-template-columns: 100%;
  }
  .main__left {
    display: none;
  }
  .header__menu {
    grid-template-columns: 10% 2% 2% 20% 2% 2% 20%;
    margin-left: 0.8%;
  }
}

.footer {
  display: grid;
  justify-content: center;
  align-items: center;
  grid-template-columns: 40px 358px 40px;
  margin-top: 30px;
}

.center_items {
  display: grid;
  justify-content: center;
  align-items: center;
}

.set-font {
  font-family: Montserrat, serif;
  font-style: normal;
}

.line {
  padding: 10px 0 0  36px;
}

.search {
  position: relative;
  display: flex;
}

.searchTerm {
  width: 100%;
  border: none;
  height: 62px;
  border-radius: 8px 0 0 8px;
  outline: none;
  background: #FFFFFF;
  font-weight: 300;
  font-size: 22px;
  line-height: 26px;
  color: #999999;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.135216);
  padding-left: 32px;
}

.searchButton {
  width: 64px;
  height: 64px;
  border: none;
  background: #FFFFFF;
  text-align: center;
  color: #fff;
  border-radius: 0 8px 8px 0;
  font-size: 20px;
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.135216);
}
</style>
