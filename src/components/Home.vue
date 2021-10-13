<template>
  <v-app id="inspire">
    <v-app-bar
        app
        color="white"
        flat
    >
      <v-container class="py-0 fill-height">
        <v-spacer></v-spacer>
        <v-btn
            v-for="link in links"
            :key="link"
            text
        >
          {{ link }}
        </v-btn>

        <v-responsive max-width="50">
          <v-avatar
              class="mr-0"
              color="grey darken-1"
              size="32"
          ></v-avatar>
        </v-responsive>
      </v-container>
    </v-app-bar>

    <v-main class="grey lighten-3">
      <v-container>
        <v-row>
          <v-col>
            <v-sheet
                min-height="70vh"
                rounded="lg"
            >
              <v-container>
                <v-switch class="v-input--reverse"
                          v-model="switch1"
                >
                  <template #label>
                    Guest dogs stay overnight in your home. Walks included.
                  </template>
                </v-switch>
                <v-switch class="v-input--reverse"
                          v-model="transportation"
                >
                  <template #label>
                    Pick-up / drop-off
                  </template>
                </v-switch>
                <v-checkbox
                    v-model="dogsLessThan1Year"
                    :label="`I accept puppies under 1 year of age`"
                ></v-checkbox>
              </v-container>
            </v-sheet>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    switch1: true,
    transportation: false,
    dogsLessThan1Year: true,
    links: [
      'Messages',
      'Booking',
      'Availability',
      'Profile',
    ],
  })
}
</script>

<style lang="scss">
.v-input--reverse .v-input__slot {
  flex-direction: row-reverse;
  justify-content: flex-end;

  .v-application--is-ltr & {
    .v-input--selection-controls__input {
      margin-right: 0;
      margin-left: 8px;
    }
  }

  .v-application--is-rtl & {
    .v-input--selection-controls__input {
      margin-left: 0;
      margin-right: 8px;
    }
  }
}
</style>