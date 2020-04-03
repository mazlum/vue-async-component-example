<template>
    <div style="margin-top:10px">
        The component has been loaded.

        <div style="margin-top: 10px">
            It's props value: {{ example }}
        </div>

        <div>
            <button @click="emitListen" style="margin-top:10px">Emit</button>
        </div>
    </div>
</template>

<script>
    export default {
      name: "Example",
      props: {
        example: {
          type: String,
          default: ""
        }
      },
      methods: {
        emitListen() {
          this.$emit("listen")
        }
      }
    }
</script>