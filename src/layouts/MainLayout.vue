<template>
  <q-layout view="hhh lpR fFf" class="container">
    <q-header elevated class="header" reveal>
      <q-tabs align="center">
        <q-route-tab to="/home" label="首页" />
        <q-route-tab to="/reference" label="归档" />
        <q-route-tab to="/classify" label="分类" />
        <q-route-tab to="/about" label="关于" />
      </q-tabs>
    </q-header>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>
<style scoped lang="scss"></style>
