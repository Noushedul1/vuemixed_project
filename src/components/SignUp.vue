<template>
  <div>
      <pre>
          {{JSON.stringify(signUpdata,null,2)}}
      </pre>
      <form>
          <div>
              <label>Name : </label>
              <input type="text" placeholder="Name" v-model="signUpdata.name">
          </div>
          <div>
              <label>Email : </label>
              <input type="text" placeholder="Email" v-model="signUpdata.email">
          </div>
          <div>
              <label>Password : </label>
              <input type="text" placeholder="Password" v-model="signUpdata.password">
          </div>
          <div>
              <label>Skills : </label>
              <select v-model="signUpdata.skills">
                  <option value="html">HTML</option>
                  <option value="css">CSS</option>
                  <option value="sass">SASS</option>
                  <option value="bootstrap">Bootstrap</option>
                  <option value="javascript">Javascript</option>
                  <option value="jquery">jQuary</option>
                  <option value="vue">Vue</option>
                  <option value="php">Php</option>
                  <option value="mysql">Mysql</option>
              </select>
          </div>
          <div>
              <label>Gender : </label>
              <div>
                  <input type="radio" value="male" v-model="signUpdata.gender">
                  <label>Male</label>
              </div>
              <div>
                  <input type="radio" value="female" v-model="signUpdata.gender">
                  <label>Female</label>
              </div>
          </div>
          <div>
              <input type="checkbox" true-value="yes" false-value="no">
              <label>Remot job?</label>
          </div>
      </form>
  </div>
</template>

<script>
export default {
    name: 'SignUp',
    data() {
        return {
            signUpdata: {
                name: '',
                email: '',
                password: '',
                skills: [],
                gender: 'Male',
                remotejob: 'no'
            }
        }
    }
}
</script>

<style>

</style>