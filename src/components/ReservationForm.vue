<template>
<q-card>
  <div class="q-pa-md">
<!--    <q class="text-h6">-->
<!--      Book your stay now and experience comfortable living with us!-->
<!--    </q>-->
    <div class="q-gutter-md" style="max-width: 300px">
      <q-input filled v-model="text" label="First Name" />
      <q-input filled v-model="text" label="Last Name" />
      <q-input standout v-model="email" type="email" prefix="Email:" suffix="@gmail.com">
        <template v-slot:prepend>
          <q-icon name="mail" />
        </template>
      </q-input>

      <!--      Dropdown-->
      <q-select
        filled
        v-model="single"
        :options="options"
        label="Room Number"
        style="width: 285px"
      />
      <!--Number of Guests-->
      <q-input
        v-model.number="model"
        type="number"
        filled
        style="max-width: 285px"
        label="Number of guests"
      />
      <div class="row">
        <q-input v-model="date" filled type="date" hint="Arrival Date" style="margin-right: 10px;"/>
        <q-input v-model="time" filled type="time" hint="Arrival Time" />
      </div>

      <div class="row">
        <q-input v-model="date" filled type="date" hint="Departure Date" style="margin-right: 10px;"/>
        <q-input v-model="time" filled type="time" hint="Departure Time" />
      </div>

      <q-card-actions align="center">
        <q-btn flat color="primary">RESERVE NOW</q-btn>
      </q-card-actions>

    </div>
  </div>
</q-card>
</template>

<style scoped lang="sass">
.q-pa-md
 padding: 20px

</style>

<script>
import { ref } from 'vue'
export default {
  setup() {
    const single = ref(null)
    const multiple = ref(null)
    const text = ref('')
    const options = [
      '1', '2', '5', '6', '7', '8', '9'
    ]

    return {
      single,
      multiple,
      text,
      options,
      model: ref(10),
      time: ref(''),
      date: ref('')
    }
  }
}
</script>
