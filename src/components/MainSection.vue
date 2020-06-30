<template>
  <section class="section main-section">
    <div class="container">
      <div class="main-content">
        <div class="header">
          <Header />
        </div>
        <div class="filter-characters">
          <div class="filter-section">
            <CharacterFilter
              class="filter-component"
              v-bind:value="value"
              v-on:statusChange="changeFilter"
            />
          </div>
        </div>
        <div v-if="$apollo.loading" class="loading-database">
          Loading Database...
        </div>
        <div v-if="error">{{ error }}</div>
        <div class="character-database">
          <div class="character-database-content">
            <div class="columns limit-flex">
              <div
                v-for="character in characters.results"
                v-bind:key="character.id"
              >
                <CharacterCards v-bind:character="character" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import characters from "../graphql/characters.gql";
import Header from "./Header.vue";
import CharacterCards from "./CharacterCards.vue";
import CharacterFilter from "./CharacterFilter.vue";

export default {
  name: "MainSection",
  components: {
    Header,
    CharacterFilter,
    CharacterCards
  },
  data() {
    return {
      characters: [],
      error: null,
      value: "Alive"
    };
  },
  apollo: {
    characters: {
      query: characters,
      variables() {
        console.log("updating filter value");
        return {
          status: this.value
        };
      },
      error(error) {
        this.error = JSON.status(error.message);
      }
    }
  },
  methods: {
    changeFilter: function(event) {
      return (this.value = event);
    }
  }
};
</script>
