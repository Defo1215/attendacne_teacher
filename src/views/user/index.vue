<template>
  <div class="p-4">
    <title-bar class="mb-4" title="我的" />

    <div
      class="p-6 w-full bg-white rounded-xl shadow"
      @click="userStore.user.id === '' ? $router.push('/login') : ''"
    >
      <div class="flex items-center">
        <n-avatar
          round
          :size="60"
          src="https://07akioni.oss-cn-beijing.aliyuncs.com/07akioni.jpeg"
        />
        <div class="ml-5 text-6" v-if="userStore.user.id !== ''">
          {{ userStore.user.teacherName }}
        </div>
        <div v-else>点击登录</div>
      </div>
    </div>
  </div>
</template>

<script setup>
import TitleBar from "../../components/TitleBar.vue";

import { useUserStore } from "../../store/userStore";

const userStore = useUserStore();
</script>
