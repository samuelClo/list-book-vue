<template>
    <ion-fab
        vertical="bottom"
        horizontal="end"
        slot="fixed"
        @click="handleClick"
    >
        <ion-fab-button>
            <ion-icon id="ionIcon" :name="isCreating ? 'close' : 'add'"/>
        </ion-fab-button>
    </ion-fab>
</template>

<script>
export default {
  name: "FabButton",
  methods: {
    handleClick() {
      this.$emit("addCard")
    },
  },
  props: {
      isCreating: Boolean,
  },
};
</script>
<style>
    #ionIcon {
        font-size: 43px;
    }
</style>