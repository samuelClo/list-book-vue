<template>
<div>
  <ion-card>
    <img :src="picturePath" />
    <ion-card-header>
      <ion-card-subtitle>{{ author }}</ion-card-subtitle>
      <ion-card-title>{{ title }}</ion-card-title>
    </ion-card-header>
    <ion-card-content>
      {{ description }}
    </ion-card-content>
    <ion-button
      no-margin
      expand="full"
      color="danger"
      @click="handleDelete(id)"
    >
    Delete
    </ion-button>
  </ion-card>
</div>
</template>

<script>
export default {
  name: "BookCard",
    props: {
      picturePath: String,
      author: String,
      title: String,
      description: String,
      id: String,
  },
  methods: {
    handleDelete(id) {
      this.$emit("deleteCard", id)
    },
  },
};
</script>