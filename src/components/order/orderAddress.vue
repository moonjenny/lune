<script>
export default {
  data() {
    return {
      tabs: ["상품정보", "최근 배송지", "신규 배송지"],
      selectedTab: 0
    };
  },
  methods: {
    selectTab(index) {
      this.selectedTab = index;
    }
  }
};
</script>

<template>
  <section class="order-address">
    <div class="title">
      <h3>받으시는 분</h3>
      <router-link
        :to="''"
        class="button-address"
      >배송지 목록</router-link>
    </div>

    <ul class="order-address-tab">
      <li v-for="(tab, index) in tabs" :key="index">
        <button type="button" @click="selectTab(index)" :class="{ active: selectedTab === index }">{{ tab }}</button>
      </li>
    </ul>
    <ul class="order-address-tab-con">
      <li v-if="selectedTab === 0">상품정보1</li>
      <li v-if="selectedTab === 1">최근 배송지2</li>
      <li v-if="selectedTab === 2">신규 배송지3</li>
    </ul>
  </section>
</template>

<style lang="scss"> 
  .order-address {
    padding: 60px 0;
    .title {
      display: flex;
      padding-bottom: 24px;
      align-items: center;
      justify-content: space-between;
      h3 {
        font-size: 18px;
        line-height: 24px;
        font-weight: 500;
      }
      .button-address {
        padding: 8px 12px;
        font-size: 13px;
        line-height: 14px;
        color: #666;
        border: 1px solid #666;
      }
    }
    &-tab {
      display: flex;
      flex-wrap: wrap;
      align-items: flex-end;
      li {
        flex: 1;
        button {
          display: block;
          padding: 20px 0 23px;
          width: 100%;
          text-align: center;
          color: #999;
          border-bottom: 1px solid #eee;
          &.active {
            padding-bottom: 21px;
            color: #111;
            font-weight: 500;
            border-bottom: 3px solid #111;
          }
        }
      }
    }
  }
</style>