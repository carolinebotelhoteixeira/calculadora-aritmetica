<template>
    <p class="resultado text-center fs-4 fw-bold text-primary">
      Resultado: {{ resultado }}
    </p>
  </template>
  
  <script>
  export default {
    name: "ResultadoCalculadora",
    props: {
      resultado: {
        type: [Number, String],
        required: true,
      },
    },
  };
  </script>
  
  <style scoped>
  .resultado {
    margin-top: 20px;
  }
  </style>
  