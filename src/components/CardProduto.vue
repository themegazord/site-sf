<template>
  <div class="produto">
    <div class="produto-titulo">
      <img
        :src="header.imagem.link"
        :alt="header.imagem.alt"
      />
      <h1>{{header.titulo}}</h1>
    </div>
    <div class="produto-conteudo">{{ conteudo }}</div>
  </div>
</template>

<script>
export default {
  props: {
    header: Object,
    conteudo: String,
  },
};
</script>

<style scoped>
.produto {
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 1rem;
}

.produto-titulo {
  display: flex;
  align-items: center;
  color: var(--sistemas);
  gap: 1rem;
}

.produto-conteudo {
  font-family: DM Sans, sans-serif;
}

</style>