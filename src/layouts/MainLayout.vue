<template>
  <q-layout view="lHh Lpr lFf">
    <q-header unelevated>
      <q-toolbar>
        <q-toolbar-title>
          SOS - Rio grande do sul
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>


    <div>
      Projeto de extensão - Aluno Gadiel Rangel - Cruzeiro do sul -
      <a href="https://sosenchentes.rs.gov.br/doacoes-em-geral">Fonte de informação</a>
    </div>
  </q-layout>
</template>

<script setup lang="ts">
defineOptions({
  name: "MainLayout",
});

</script>
