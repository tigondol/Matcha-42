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
            :value="userData.first_name"
            v-on:change="handleChange"
          />

          <label for="date_of_birth">Date de naissance :</label>
          <div className="multiple-input-container">
            <input
              type="number"
              id="dob_day"
              placeholder="DD"
              required="true"
              :value="userData.dob_day"
              v-on:change="handleChange"
            />
            <input
              type="number"
              id="dob_month"
              placeholder="MM"
              required="true"
              :value="userData.dob_month"
              v-on:change="handleChange"
            />
            <input
              type="number"
              id="dob_year"
              placeholder="YYYY"
              required="true"
              :value="userData.dob_year"
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
              :checked="userData.gender_identity === 'man'"
              v-on:change="handleChange"
            />
            <label>Homme</label>
            <input
              type="radio"
              id="woman-gender-identity"
              name="gender"
              required="true"
              value="female"
              :checked="userData.gender_identity === 'woman'"
              v-on:change="handleChange"
            />
            <label>Femme</label>
            <input
              type="radio"
              id="other-gender-identity"
              name="gender"
              required="true"
              value="other"
              :checked="userData.gender_identity === 'other'"
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
          />

          <label>Montrez moi :</label>
          <div className="multiple-input-container">
            <input
              type="radio"
              id="man-gender-interest"
              name="gender_interest"
              required="true"
              value="man"
              :checked="userData.gender_interest === 'man'"
              v-on:change="handleChange"
            />
            <label>Homme</label>
            <input
              type="radio"
              id="woman-gender-interest"
              name="gender_interest"
              required="true"
              value="woman"
              :checked="userData.gender_interest === 'woman'"
              v-on:change="handleChange"
            />
            <label>Femme</label>
            <input
              type="radio"
              id="all-gender-interest"
              name="gender_interest"
              required="true"
              value="all"
              :checked="userData.gender_interest === 'other'"
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
            :value="userData.about"
            v-on:change="handleChange"
          />
          <button className="secondary-button" onclick="handleSubmit">Submit</button>
        </section>
        <section>
          <label for="about">Photo de profile</label>
          <input
            type="url"
            name="url"
            id="url"
            :value="userData.url"
            v-on:change="handleChange">
          <div className="photo-container" v-if="userData.url">
              <img src={userData.url} alt="profile pic preview"/>
          </div>
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
      userData: {
        first_name: "",
        dob_day: "",
        dob_month: "",
        dob_year: "",
        show_gender: false,
        gender_identity: "man",
        gender_interest: "woman",
        url: "",
        about: "",
        matches: []
      },
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
    handleChange(e) {
      console.log(e)
      const value = e.target.type === "checkbox" ? e.target.checked : e.target.value
      const name = e.target.name
      this.userData[name] = value
    }
  },
  methods: {
  }
};
</script>
