<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <ion-app>
    <ion-content>
      <BookCard
        v-for="card in books"
        v-bind:key="card.isbn"

        :picturePath="card.thumbnailUrl"
        :author="card.authors"
        :title="card.title"
        :description="card.shortDescription"
        :id="card.isbn"

        @deleteCard="handleDelete"
      />
    </ion-content>
    </ion-app>
    <FabButton
      :isCreating="isCreating"
      @addCard="handleAdd"
    />
  </div>
</template>

<script>
import BookCard from '@/components/BookCard.vue'
import FabButton from '@/components/FabButton.vue'
import Modal from '@/components/Modal.vue'

import sdfsdfsdf from '../../data/book.json'

export default {
  name: 'Home',
  components: {
    BookCard,
    FabButton,
  },
  data() {
    return {
      books: sdfsdfsdf,
      isCreating: false,
    }
  },
  methods: {
    handleDelete(id) {
      this.books = this.books.filter(book => book.isbn !== id)
    },
    handleAdd() {
      if (this.isCreating)
        this.closeModal()
      else
        this.openModal()

      this.isCreating = !this.isCreating
    },
    closeModal() {
      return this.$ionic.modalController.dismiss()
    },
    openModal() {
      return this.$ionic.modalController
        .create({
          component: Modal,
          componentProps: {
            data: {
              content: 'New Content',
            },
            propsData: {
              title: 'New title',
            },
          },
        })
        .then(m => m.present())
    },
  },
}
</script>
