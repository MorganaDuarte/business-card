<template>
  <div>
    <button>Voltar</button>
    <h1>{{ dataCard.name }}</h1>
    <h1>{{ dataCard.email }}</h1>
    <h1>{{ dataCard.phone }}</h1>
  </div>
</template>

<script>
export default {
  props: {
    dataCard: {
      type: Object,
      required: true
    }
  }
}
</script>