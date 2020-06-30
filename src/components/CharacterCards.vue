<template>
  <div class="column card-column">
    <div class="character-card">
      <div class="character-card-content box character-box">
        <div class="character-image">
          <img class="character-image" :src="character.image" />
        </div>
        <div class="character-name">
          <h3>
            {{ character.name }}
          </h3>
          <div class="underline"></div>
        </div>
        <div class="character-status">
          <div class="status-icon" :class="getStatus(character.status)"></div>
          {{ character.status }}
        </div>
        <div class="character-species">
          <p class="sub-title">
            Species:
          </p>
          <a href="/">
            {{ character.species }}
          </a>
        </div>
        <div class="character-location">
          <p class="sub-title">
            Origin:
          </p>
          <a href="/">
            {{ character.origin.name }}
          </a>
          <p class="sub-title">
            Last known location:
          </p>
          <a href="/">
            {{ character.location.name }}
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CharacterCards",
  props: {
    character: {}
  },
  methods: {
    getStatus: function(stat) {
      var status = stat;
      if (status === "Alive") {
        return "is-green";
      } else if (status === "Dead") {
        return "is-red";
      } else if (status === "unknown") {
        return "is-gray";
      }
    },
    mounted: function() {
      this.$nextTick(this.getStatus);
    }
  }
};
</script>
