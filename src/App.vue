<template>
  <el-config-provider :locale="currentLocale">
    <router-view />
  </el-config-provider>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { ElConfigProvider } from "element-plus";
import vi from "element-plus/lib/locale/lang/vi";
import en from "element-plus/lib/locale/lang/en";
export default defineComponent({
  name: "app",
  components: {
    [ElConfigProvider.name]: ElConfigProvider
  },
  computed: {
    currentLocale() {
      return this.$storage.locale?.locale === "vi" ? vi : en;
    }
  }
});
</script>
