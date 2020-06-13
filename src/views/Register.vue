<template>
  <v-container>
    <v-row>
      <v-col>
        <h1>Register</h1>
        <v-form>
          <v-text-field label="Email" type="email"></v-text-field>
          <v-autocomplete
            label="Which browser do you use?"
            :items="browsers"
          ></v-autocomplete>
          <v-file-input label="Attach profile picture"></v-file-input>
          <!-- We don't bother with the hiding/showing for the example. See docs. -->
          <v-text-field
            v-model="Birthday"
            label="Birthday"
            readonly
          ></v-text-field>
          <v-date-picker label="Birthday" v-model="birthday"></v-date-picker>
          <v-checkbox label="Agree to terms & conditions"></v-checkbox>
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    browsers: ['Chrome', 'Edge', 'Safari', 'Firefox', 'Brave'],
    birthday: ''
  })
}
</script>
