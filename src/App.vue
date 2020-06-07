<template>
  <v-app>
    <!-- the card serves as the container -->
    <!-- the classes are utility classes to centre it and give it margin on the top -->
    <v-card width="400" class="mx-auto mt-5">
      <!-- Ensures the heading has correct spacing -->
      <v-card-title>
        <h1 class="display-1">Login</h1>
      </v-card-title>
      <!-- Wraps the form inputs -->
      <v-card-text>
        <v-form>
          <v-text-field label="Username" prepend-icon="mdi-account-circle" />
          <v-text-field
            label="Password"
            :type="showPassword ? 'text' : 'password'"
            prepend-icon="mdi-lock"
            :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
            @click:append="showPassword = !showPassword"
          />
        </v-form>
      </v-card-text>
      <!-- Add some space for it -->
      <v-divider></v-divider>
      <v-card-actions>
        <v-btn color="success">Register</v-btn>
        <v-spacer></v-spacer>
        <v-btn color="info">Login</v-btn>
      </v-card-actions>
    </v-card>
  </v-app>
</template>

<script>
export default {
  name: 'App',

  components: {},

  data: () => ({
    showPassword: false
  })
}
</script>
