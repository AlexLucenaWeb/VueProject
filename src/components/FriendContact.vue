<template>
  <li>
    <h2>{{ name }} {{ isFavorite ? '*': '' }}</h2>
    <button @click="toogleDetails">
      {{ detailsVisibility ? 'Hide' : 'Show' }} details
    </button>
    <button @click="toogleFavorite">
      Toogle favorite
    </button>
    <ul v-if="detailsVisibility">
      <li><strong>Phone:</strong> {{ phoneNumber }}</li>
      <li><strong>Email:</strong> {{ emailAddress }}</li>
    </ul>
  </li>
</template>

<script>
export default {
  props: {
    id:{
      type: String,
      required: true
    },
    name: {
      type: String,
      required: true
    },
    phoneNumber: {
      type: String,
      required: true
    },
    emailAddress: {
      type: String,
      required: true
    },
    isFavorite: {
      type: Boolean,
      required: false,
      default: false
    }
  },
  // emits: {
  //   'toogle-favorite': function(id){
  //     if (id) {
  //       return true;
  //     } else {
  //       console.warn("Id is missing!")
  //       return false;
  //     }
  //   },
  // },
  emits: ['toogle-favorite'],
  data() {
    return {
      detailsVisibility: false,
    };
  },
  methods: {
    toogleDetails() {
      this.detailsVisibility = !this.detailsVisibility;
    },
    toogleFavorite() {
      this.$emit('toogle-favorite', this.id);
    }
  },
};
</script>
