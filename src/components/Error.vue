<template>
    <div class="mt-2">
        <div>
            <div>Something went wrong</div>
            <button @click="reload">
                Try Again
            </button>
        </div>
    </div>
</template>

<script>
export default {
    name: "AsyncError",
    methods: {
      reload() {
        this.$emit("reload");
      }
    }
};
</script>
