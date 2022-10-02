<template>
  <div class="container">
    <pre>
    {{ JSON.stringify(formValues, null, 2) }}
  </pre
    >
  </div>
  <form action="">
    <div class="col-4">
      <div class="mb-3">
        <label for="exampleFormControlInput1" class="form-label">Name</label>
        <input v-model="formValues.name" type="text" class="form-control" id="exampleFormControlInput1" />
      </div>

      <div class="mb-3">
        <label for="exampleFormControlTextarea1" class="form-label">Profile Summary</label>
        <textarea class="form-control" id="exampleFormControlTextarea1" rows="3" v-model="formValues.profileSummary"></textarea>
      </div>

      <div class="mb-3">
        <label for="exampleFormControlTextarea1" class="form-label">Country</label>
        <select class="form-select" aria-label="Default select example" v-model="formValues.country">
          <option value="" selected>Open this select menu</option>
          <option value="Indonesia">Indonesia</option>
          <option value="Singapore">Singapore</option>
          <option value="Australia">Australia</option>
        </select>
      </div>

      <div class="mb-3">
        <select class="form-select" aria-label="Default select example" multiple v-model="formValues.jobLocation">
          <option value="Indonesia">Indonesia</option>
          <option value="Singapore">Singapore</option>
          <option value="Australia">Australia</option>
        </select>
      </div>

      <div class="form-check">
        <input class="form-check-input" type="checkbox" value="" id="flexCheckDefault" v-model="formValues.remoteWork" true-value="yes" false-value="no" />
        <label class="form-check-label" for="flexCheckDefault"> Open to remote work? </label>
      </div>

      <div>
        <label for="exampleFormControlTextarea1" class="form-label mt-3">Skill Set:</label>
      </div>
      <div class="form-check form-check-inline">
        <input class="form-check-input" type="checkbox" value="HTML" id="HTML" v-model="formValues.skillSet" />
        <label class="form-check-label" for="HTML">HTML</label>
      </div>
      <div class="form-check form-check-inline">
        <input class="form-check-input" type="checkbox" value="CSS" id="CSS" v-model="formValues.skillSet" />
        <label class="form-check-label" for="CSS">CSS</label>
      </div>
      <div class="form-check form-check-inline">
        <input class="form-check-input" type="checkbox" value="Javascript" id="Javascript" v-model="formValues.skillSet" />
        <label class="form-check-label" for="Javascript">Javascript</label>
      </div>
    </div>
  </form>
</template>

<script>
  export default {
    name: 'App',
    data() {
      return {
        formValues: {
          name: '',
          profileSummary: '',
          country: '',
          jobLocation: [],
          remoteWork: 'no',
          skillSet: [],
          yearsOfExperience: '',
        },
      }
    },
    components: {},

    methods: {},
  }
</script>

<style>
  #app {
    font-family: quicksand, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    /* text-align: center; */
    color: #2c3e50;
    margin-top: 60px;
    margin-left: 20px;
  }
</style>
