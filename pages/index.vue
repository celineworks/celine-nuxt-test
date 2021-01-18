<template>
  <ul>
    <li v-for="content in contents" :key="content.id">
      <nuxt-link :to="`/${content.id}`">
        {{ content.title }}
      </nuxt-link>
    </li>
  </ul>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData() {
    const { data } = await axios.get(
      'https://celine-test.microcms.io//api/v1/blog',
      {
        headers: { 'X-API-KEY': '9119be3c-501d-456d-a158-0d2025a88549' }
      }
    )
    return data
  }
}
</script>