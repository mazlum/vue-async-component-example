<template>
    <content-loader :height="60" class="mt-2" />
</template>

<script>
import { ContentLoader } from "vue-content-loader";

export default {
    name: "AsyncLoader",
    components: {
      ContentLoader
    }
};
</script>
