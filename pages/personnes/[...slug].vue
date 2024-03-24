<script lang="ts" setup>

import type { Player } from "~/models/player.model";

const {findOne} = useStrapi4()
const route = useRoute()

const {data: player} =useAsyncData('players', 
() => findOne<{data: Player[]}> (`player/${route.params.slug}`)
)

</script>
<template>
  <pre>{{ player }}</pre>
</template>
