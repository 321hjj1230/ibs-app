<template>
    <showtop Text="食物列表"></showtop>
  <!-- 菜单左右联动 -->
  <div class="menu_detail">
    <!-- 左侧菜单 -->
    <div class="menu_list">
      <van-sidebar v-model="tabValue">
        <van-sidebar-item
          :title="index.name"
          v-for="index in menuList"
          :key="index"
          @click="handleMenulist(index)"
        />
      </van-sidebar>
    </div>
    <!-- 右侧菜单 -->
    <div>
      <van-list
        v-model="loading"
        :finished="finished"
        finished-text="没有更多了"
        @load="onLoad"
      >
        <van-cell v-for="item in list" :key="item" :title="item" />
      </van-list>
    </div>
  </div>
  <top-nav></top-nav>
</template>

<script>
import { ref, reactive, toRefs, onMounted } from "vue";
import { useRouter } from "vue-router";
import Showtop from '@/components/line/showtop.vue';
import TopNav from '@/components/line/topNav.vue';
export default {
  components: {Showtop, TopNav},
  setup() {
    const router = useRouter();
    const tabValue = ref(0);
    const state = reactive({
      menuList: [
        {
          id: 1,
          name: "水果",
        },
        {
          id: 1,
          name: "水果",
        },
        {
          id: 1,
          name: "水果",
        },
      ],
    });

    onMounted(() => {

    });

    //左侧菜单点击联动左侧
    const handleMenulist = (index) => {
      console.log(index);
    };

    return {
      ...toRefs(state),
      tabValue,
      handleMenulist,
    };

  },
  data() {
    return {
      list: [],
      loading: false,
      finished: false
    };
  },

  methods: {
    onLoad() {
      // 异步更新数据
      setTimeout(() => {
        for (let i = 0; i < 10; i++) {
          this.list.push(this.list.length + 1);
        }
        // 加载状态结束
        this.loading = false;

        // 数据全部加载完成
        if (this.list.length >= 40) {
          this.finished = true;
        }
      }, 500);
    }
  }
};
</script>
<style>
.menu_detail {
  height: calc(100vh - 140px);
  display: flex;
}

.menu_list {
  width: auto;
  height: 100%;
  background-color: var(--van-gray-0);;
}

/* 选中标签三角标识 */
.van-sidebar-item--select:before {
  position: absolute;
  top: 50%;
  left: 0;
  width: 0;
  height: 0;
  border-top: 5px solid transparent;
  border-left: 10px solid #3adbde;
  border-bottom: 5px solid transparent;
  -webkit-transform: translateY(-50%);
  background-color: #fff;
  transform: translateY(-50%);
  content: "";
}
</style>
