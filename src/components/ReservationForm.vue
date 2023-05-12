<template>
<q-card>
  <div class="q-pa-md">
    <div class="row">
      <q-img src="~assets/iloilo.jpg"></q-img>
    </div>
    <div class="text-center" style="font-weight: bold; padding: 10px;">
      <h7>"Book your perfect stay in just a few clicks"</h7>
    </div>
    <div class="q-gutter-md" style="max-width: 300px;">
      <q-input filled label-color="black" v-model="firstName" label="First Name"/> <!--First Name-->
      <q-input filled v-model="lastName" label-color="black" label="Last Name" /> <!--Last Name-->
      <q-input filled v-model="number" label-color="black" label="Contact Number" /> <!--Contact Number-->
      <!--Email-->
      <q-input filled v-model="email" label-color="black" type="email" prefix="Email:" suffix="@gmail.com">
        <template v-slot:prepend>
          <q-icon name="mail" color="black"/>
        </template>
      </q-input>

      <!--Number of Rooms-->
      <q-select filled v-model="single" label-color="black" :options="options" label="Room Number" style="width: 285px"/>
      <!--Number of Guests-->
      <q-input v-model.number="model" type="number" filled label-color="black" style="max-width: 285px" label="Number of guests"/>
      <!--Arrival Date & Time-->
      <div class="row">
        <q-input v-model="date" filled type="date" hint="Arrival Date" style="margin-right: 10px; "/>
        <q-input v-model="time" filled type="time" hint="Arrival Time"/>
      </div>
      <!--Departure Date & Time-->
      <div class="row">
        <q-input v-model="date" filled type="date" hint="Departure Date" style="margin-right: 10px;"/>
        <q-input v-model="time" filled type="time" hint="Departure Time" />
      </div>

      <q-card-actions align="center">
        <q-btn flat color="primary" style="padding-left: 10px; padding-right: 10px;">RESERVE NOW</q-btn>
      </q-card-actions>

    </div>
  </div>
</q-card>
</template>

<style scoped lang="sass">
.q-pa-md
  //padding: 10px
  //margin: 20px

</style>

<script>
import { ref } from 'vue'
export default {
  setup() {
    const single = ref(null)
    const multiple = ref(null)
    const firstName = ref('')
    const lastName = ref('')
    const number = ref('')
    const options = [
      '1', '2', '5', '6', '8', '9', '10', '11', '12', '14', '15', '17'
    ]

    return {
      single,
      multiple,
      firstName,
      lastName,
      number,
      options,
      model: ref(2),
      time: ref(''),
      date: ref('')
    }
  }
}
</script>
