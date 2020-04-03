<template>
    <transition name="fade" mode="out-in">
        <component
            ref="asyncComponent"
            :is="asyncComponent"
            v-bind.sync="$attrs"
            @reload="getComponent"
            v-on="$listeners"
        />
    </transition>
</template>

<script>
import AsyncLoading from "./Loader";
import AsyncError from "./Error";

export default {
    name: "AsyncComponent",
    props: {
      component: {
        type: Function,
        required: true
      }
    },
    data() {
      return {
        asyncComponent: null
      };
    },
    mounted() {
      this.getComponent();
    },
    methods: {
      getComponent() {
        // load component
        this.asyncComponent = () => ({
          component: this.component(),
          loading: AsyncLoading,
          error: AsyncError,
          timeout: 3000,
          delay: 200
        });
      }
    }
};
</script>
