<template>
  <div>
    <header v-if="$route.meta.title">
      <Navbar authToken="true" @loginClick="logIn" />
    </header>
    <div className="onboarding">
      <h1>Inscrirption</h1>
      <form onSubmit="submit">
        <section>
          <label for="first_name">Prenom :</label>
          <input
            type="text"
            id="first_name"
            placeholder="Prenom"
            required="true"
            value=""
            v-on:change="handleChange"
          />

          <label for="date_of_birth">Date de naissance :</label>
          <div className="multiple-input-container">
            <input
              type="number"
              id="dob_day"
              placeholder="DD"
              required="true"
              value=""
              v-on:change="handleChange"
            />
            <input
              type="number"
              id="dob_month"
              placeholder="MM"
              required="true"
              value=""
              v-on:change="handleChange"
            />
            <input
              type="number"
              id="dob_year"
              placeholder="YYYY"
              required="true"
              value=""
              v-on:change="handleChange"
            />
          </div>

          <label>Genre :</label>
          <div className="multiple-input-container">
            <input
              type="radio"
              id="man-gender-identity"
              name="gender"
              required="true"
              value="male"
              checked="false"
              v-on:change="handleChange"
            />
            <label>Homme</label>
            <input
              type="radio"
              id="woman-gender-identity"
              name="gender"
              required="true"
              value="female"
              checked="false"
              v-on:change="handleChange"
            />
            <label>Femme</label>
            <input
              type="radio"
              id="other-gender-identity"
              name="gender"
              required="true"
              value="other"
              checked="false"
              v-on:change="handleChange"
            />
            <label>Autre</label>
          </div>

          
          <label for="show_gender">Afficher mon genre</label>
          <input
            type="checkBox"
            id="show-gender"
            name="show-gender"
            required="true"
            v-on:change="handleChange"
            checked="false"
          />

          <label>Montrez moi :</label>
          <div className="multiple-input-container">
            <input
              type="radio"
              id="man-gender-interest"
              name="gender_interest"
              required="true"
              value="man"
              checked="false"
              v-on:change="handleChange"
            />
            <label>Homme</label>
            <input
              type="radio"
              id="woman-gender-interest"
              name="gender_interest"
              required="true"
              value="woman"
              checked="false"
              v-on:change="handleChange"
            />
            <label>Femme</label>
            <input
              type="radio"
              id="all-gender-interest"
              name="gender_interest"
              required="true"
              value="all"
              checked="false"
              v-on:change="handleChange"
            />
            <label>Tous</label>
          </div>
          <label for="show_gender">Description</label>
          <input
            type="text"
            id="description"
            name="description"
            required="true"
            v-on:change="handleChange"
            checked="false"
          />
          <button className="secondary-button" onclick="handleSubmit">Submit</button>
        </section>
        <section>
          <label for="about">Photo de profile</label>
          <input
            type="url"
            name="url"
            id="url"
            v-on:change="handleChange">
          <div></div>
        </section>
      </form>
    </div>
  </div>
</template>

<style lang="sass"></style>

<script>
import Navbar from "../components/Navbar.vue";

export default {
  name: "Onboarding",
  components: {
    Navbar,
  },
  data() {
    return {
      authToken: true,
    };
  },
  created() {
    console.log(this.authToken);
  },
  computed: {
    handleClick() {
      console.log("clicked");
    },
    handleSubmit() {
      console.log("submitted")
    },
    handleChange() {
      console.log("changed")
    }
  },
  methods: {
  }
};
</script>
