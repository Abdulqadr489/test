<template>
  <form @submit.prevent="submitform">
    <div>
      <pre>
    {{ JSON.stringify(formValues, null, 2) }}
  </pre
      >
    </div>
    <div>
      <label for="name">Name</label>
      <input v-model.lazy="formValues.name" type="text" id="name" />
    </div>
    <br />
    <div>
      <label for="profile">Profile summary</label>
      <textarea name="" id="profile" cols="30" rows="10"></textarea>
    </div>
    <br />
    <div>
      <label for="country">COuntry</label>
      <select name="" id="country" v-model="formValues.country">
        <option value="">Select a country</option>
        <option value="india">India</option>
        <option value="karkuk">Krkuk</option>
        <option value="hawler">HAwler</option>
        <option value="duhok">Duhok</option>
      </select>
    </div>
    <br />
    <br />

    <div>
      <label for="job-location">Job location</label>
      <select name="" id="country" multiple v-model="formValues.joblocation">
        <option value="india">India</option>
        <option value="karkuk">Krkuk</option>
        <option value="hawler">HAwler</option>
        <option value="duhok">Duhok</option>
      </select>
    </div>

    <div>
      <input
        type="checkbox"
        name=""
        id="remotework"
        v-model="formValues.remotework"
        true-value="yes"
        false-value="no"
      />
      <label for="remotework">Open to remote work</label>
    </div> 

    <div>
      <label for="">Skills</label>
<br>
      <input @keyup="submitform" type="checkbox" id="html" value="html" v-model="formValues.skillset">
      <label for="html">HTML</label>
<br>

      <input type="checkbox" id="css" value="css" v-model="formValues.skillset">
      <label for="css">CSS</label>
<br>
      <input type="checkbox" id="javascript" value="javascript" v-model="formValues.skillset">
      <label for="javascript">JavaScript</label>
    </div>

    <div>
      <label for="age">Age</label>
      <br>
      <input type="number" name="" id="age" v-model.number="formValues.age">
    </div>

  
  </form>
</template>



<script >
import { toHandlerKey } from 'vue';
export default {
  name: "App",
  data() {
    return {
      formValues: {
        name: "",
        profileSummary: "",
        joblocation: [],
        remotework: "no",
        skillset:[],
        age:null,
      },
    };
  },
  methods: {
    submitform(event)
    {
      console.log('Form values',this.formValues)
    }

  },
};
</script>
