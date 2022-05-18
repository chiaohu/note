- ```
  //composition api
  proxy 
  vue 透過proxy來做建構
  
  vuex 主要用在大型專案的元件資料傳遞方法
  vuex安裝 npm install vuex --save
  在main.js 
  import Vuex from 'vuex'
  import store from './store'
  Vue.use(Vuex)
  
  在SRC下新增一個STORE資料夾新增index.js <-- 彙整所有vuex行為
  index.js
  import vue 與 vuex
  Vue.use(Vuex)
  
  export default new Vuex.Store({
      state: {
          資料: false,
      },
      actions: {
          // status --> payload 載荷
          updateLoading(context, status) {
              context.commit('ISLOADING', status)
          }
      },
      //不要執行AJAX跟非同步行為
      mutations: {
          LOADING(state, status) {
              state.資料 = status
          }
      }
  })
  
  在app.vue中
  computed: {
      資料() {
          return this.$store.state.資料;
      }
  }
  
  vm.$store.dispatch('ISLOADING', true)
  
  元件方法 -> Vuex
  data-- state 資料狀態
  methods-- actions 進行非同步的行為及取得資料
  computed-- getter 資料呈現的方式
  mutation-- - 改變資料內容的方法
  ```
- ---
- Vue3
- ```
  Vue 3 
  應用程式
  Vue.createdApp({
      data() {
          return{
  
          }
      },
      methods: {
  
      },
      mounted: {
  
      }
  }).mount('#app')
  
  refs: 快速取得畫面上的DOM元素，也可以取得元件內容，所以要在mounted階段使用 < 標籤 ref = "名稱" ></標籤 > this.$refs.名稱直接指向DOM元素
  
  teleport: 將元件的內容跨區塊放置可新增多個  在元件的template中增加 < teleport to = "dom元素名稱" ></teleport >
  
  provide: 跨元件的資料傳遞，如果元件有很多層級 在外層的VUE應用程式增加provide屬性(像methods一樣) ，在內層元件補上inject: ['user'(provide的key名稱)],
  當provide是物件模式時，如果只在內層元件更改值其他地方不會跟著變動(只會改到當前元件) ，如果要做到響應式要將provide改成函式(像data一樣) 
  provide() { 
      return { 
          user: this.物件 
      } 
  }
  
  元件加入v-model: 將元件內使用v-model做到雙向綁定可使用多個v-model。
  <元件 v-model:props的值="外層參數"></元件>
  元件 :value="props的值" 到此只有單向綁定
  在元件的template中+@input="$emit('update(固定的名稱) : props的值', $event.targer.value)"
  
  mixins: 將元件載入到別的元件內，生命週期可以重複觸發，如果變數方法同名第一順位是元件本身的資料，再來是最後加入的元件資料。
  使用: mixins:[元件名稱, 元件名稱]
  
  extend(擴展): 一次只能擴展一個元件使用方法跟Mixins相似生命週期可以重複觸發，權重:元件屬性>mixins>extend。
  使用: extends: 元件名稱 (不用括號)
  
  自定義指令 directive
  v-自定義名稱
  註冊指令:
  app.directive('自定義名稱',{
      //生命週期 
      // el 元素本體
      // binding 綁定的資源狀態
      // 虛擬DOM節點
      mounted(el, binding, vnode){
  
      }
  })
  ```
-