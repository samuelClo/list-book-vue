<template>
  <div>
    <ion-header>
      <ion-toolbar>
        <ion-title>Ajouter un livre</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
      <input type="text" placeholder="titre" >
      <input type="text" placeholder="nombre de page" >
      <input type="text" placeholder="" >
      <input type="text" placeholder="" >
      <input type="text" placeholder="" >
      <input type="text" placeholder="" >
    </ion-content>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  props: {
    title: { type: String, default: 'Super Modal' },
  },
  data() {
    return {
      content: 'Content',
    }
  },
}
</script>