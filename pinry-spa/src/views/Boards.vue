<template>
  <div class="boards">
    <PHeader></PHeader>
    <Boards :filters="filters"></Boards>
  </div>
</template>

<script>
import PHeader from '../components/PHeader.vue';
import Boards from '../components/Boards.vue';

export default {
  name: 'AllPublicBoards',
  data() {
    return {
      filters: { boardUsername: null, boardNameContains: '' },
    };
  },
  components: {
    PHeader,
    Boards,
  },
  created() {
    this.initialize();
  },
  beforeRouteUpdate(to, from, next) {
    this.filters = { boardUsername: null };
    next();
  },
  methods: {
    initialize() {
      this.filters = { boardUsername: null, boardNameContains: '' };
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
