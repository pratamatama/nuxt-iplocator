<template>
  <Tutorial />
</template>

<script>
export default {
  name: 'IndexPage',
  mounted() {
    this.fetchIpaddress()
  },
  methods: {
    async fetchIpaddress() {
      try {
        const data = await this.$axios.$get(
          'https://api.ipregistry.co?key=han4um8qabhqcg00'
        )
        // eslint-disable-next-line
        console.log(data)

        const response = await this.$axios.$post('/api/ip-addresses', {
          data: {
            ipaddress: data,
          },
        })
        // eslint-disable-next-line
        console.log(response)
      } catch (err) {
        // eslint-disable-next-line
        console.error(err)
      }
    },
  },
}
</script>
