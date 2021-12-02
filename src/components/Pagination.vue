<template>
  <div class="footer">
    <div class="footer__pgnLeft">
      <button data-element="prev" type="button" class="footer__pgnLeft-icon center_items">
        <svg width="9" height="14" viewBox="0 0 9 14" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M7.09959 13L1.07361 7L7.09959 1" stroke="black" stroke-width="2"
                stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </button>
    </div>
    <div class="pagination set-font">
      <a v-for="item in pages"
         :key="item"
         :class="item == currentPage ? 'active' : ''"
      >
        {{ item + 1 }}
      </a>
    </div>
    <div class="footer__pgnRight">
      <button data-element="next" type="button" class="footer__pgnRight-icon center_items">
        <svg width="9" height="14" viewBox="0 0 9 14" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M1.93566 1L7.96164 7L1.93566 13" stroke="black" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </button>
    </div>
  </div>
</template>

<script>
import {defineComponent} from "vue";

export default defineComponent({
  components: {

  },
  props: {
    totalPages: {
      type: Number,
      default: 1
    },
    pages: {
      type: Array,
      default: () => []
    },
    currentPage: {
      type: Number,
      default: 0
    }
  },
  setup(props, { emit }) {

  }
})
</script>

<style scoped>
.pagination {
  border-radius: 20px;
  background: #EDEDED;
  width: max-content;
  height: 40px;
  text-align:center;
  text-decoration: none;
  cursor: pointer;
}

.pagination a {
  float: left;
  text-align: center;
  padding: 7px 10px 8px 15px;
  text-decoration: none;
  font-weight: normal;
  font-size: 18px;
  letter-spacing: 4px;
  color: #2C2C2C;
}

.pagination a.active {
  background: #6F64F8;
  color: white;
  border-radius: 20px;
}

.footer__pgnLeft {
  display: grid;
  justify-content: right;
}

.footer__pgnLeft-icon {
  background: #EDEDED;
  width: 40px;
  height: 40px;
  border-radius: 20px;
  margin-right: 17px;
  border: none;
  cursor: pointer;
}

.footer__pgnRight {
  display: grid;
  justify-content: left;
}

.footer__pgnRight-icon {
  background: #EDEDED;;
  width: 40px;
  height: 40px;
  border-radius: 20px;
  margin-left: 17px;
  border: none;
  cursor: pointer;
}

.footer {
  display: grid;
  justify-content: center;
  align-items: center;
  grid-template-columns: 40px auto 40px;
  margin-top: 30px;
}
</style>
