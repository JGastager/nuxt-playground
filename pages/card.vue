<template>
  <main>
    <Card>
      <h1>Card</h1>
      <p>This is a card component</p>
    </Card>
    <Card>
      <h1>Card</h1>
      <p>This is a card component</p>
    </Card>
    <Card>
      <h1>Card</h1>
      <p>This is a card component</p>
    </Card>
    <Card>
      <h1>Card</h1>
      <p>This is a card component</p>
    </Card>
    <Card>
      <h1>Card</h1>
      <p>This is a card component</p>
    </Card>
    <Card>
      <h1>Card</h1>
      <p>This is a card component</p>
    </Card>
    <Card>
      <h1>Card</h1>
      <p>This is a card component</p>
    </Card>
  </main>
</template>

<script lang="ts" setup>

</script>

<style lang="scss">
main {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 1rem;
  padding: 3rem;
}
</style>