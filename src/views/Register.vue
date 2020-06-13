<template>
  <v-container>
    <v-row>
      <v-col>
        <h1>Register</h1>
        <v-form>
          <v-text-field label="Name" :rules="nameRules"></v-text-field>
          <v-text-field
            label="Email"
            type="email"
            v-model="email"
            :rules="emailRules"
            required
          ></v-text-field>
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
          <v-checkbox
            label="Agree to terms & conditions"
            v-model="agreeToTerms"
            :rules="agreeToTermsRules"
            required
          ></v-checkbox>
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    nameRules: [
      (value) => !!value || 'Name is required.',
      (value) => value.length > 1 || 'Minimum length is 2.'
    ],
    emailRules: [
      (value) => !!value || 'Email is required',
      (value) => value.indexOf('@') !== 0 || 'Email should have a username.',
      (value) => value.includes('@') || 'Email should include an @ symbol',
      (value) =>
        value.indexOf('.') - value.indexOf('@') > 1 ||
        'Email should contain a valid domain',
      (value) =>
        value.indexOf('.') <= value.length - 3 ||
        'Email should contain a valid domain extension.'
    ],
    agreeToTermsRules: [
      (value) =>
        !!value || 'You must agree to terms and conditions to register.'
    ],

    email: '',
    browsers: ['Chrome', 'Edge', 'Safari', 'Firefox', 'Brave'],

    birthday: '',
    agreeToTerms: false
  })
}
</script>
