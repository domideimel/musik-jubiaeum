<template>
  <q-form @submit.prevent.stop="onSubmit" @reset.prevent.stop="onReset" class="q-gutter-md">
    <q-input outlined v-model="form.surname" label="Name" />
    <q-input outlined v-model="form.name" label="Nachname" />
    <q-input outlined v-model="form.street" label="Straße" />
    <q-input outlined v-model="form.town" label="PLZ / Ort" />
    <q-input outlined v-model="form.mail" label="E-Mail" />
    <q-separator />
    <div>
      <h5>31.01.2021 Jubiläumskonzert</h5>
      <q-option-group
        v-model="form.concert"
        :options="concert"
        color="red-12"
      />
    </div>
    <div>
      <h5>30.10.2021 Festveranstaltung</h5>
      <q-option-group
        v-model="form.party"
        :options="party"
        color="red-12"
      />
    </div>
    <div>
      <h5>31.10.2021 Frühschoppenkonzert anschl. gemütliches Beisammensein</h5>
      <q-option-group
        v-model="form.drinking"
        :options="drinking"
        color="red-12"
      />
    </div>
    <q-separator />
    <p>
      Beim Frühschoppenkonzert am 31.10.2021 möchte das Orchester gerne gemeinsam mit den ehemaligen Musikerinnen
      und Musikern 2–3 Musikstücke aus der Vergangenheit aufführen.
    </p>
    <p>
      Hast Du Lust mitzuspielen und noch ein eigenes Instrument?<br>
      Welches Instrument spielst Du?<br>
      Noten stellen wir Dir zur Verfügung.
    </p>
    <p>
      Wir freuen uns auf einen gemeinsamen Auftritt!
    </p>

    <q-input
      v-model="form.text"
      outlined
      type="textarea"
    />

    <div>
      <q-btn label="Anmelden" type="submit" color="red-12" />
    </div>
  </q-form>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Form',
  data () {
    return {
      form: {
        surname: null,
        name: null,
        street: null,
        town: null,
        mail: null,
        text: null,
        concert: null,
        party: null,
        drinking: null
      },
      concert: [{
        label: 'Ja',
        value: 'ja'
      }, {
        label: 'Ja mit Partner',
        value: 'ja (partner)'
      }, {
        label: 'Nein',
        value: 'nein'
      }],
      party: [{
        label: 'Ja',
        value: 'ja'
      }, {
        label: 'Ja mit Partner',
        value: 'ja (partner)'
      }, {
        label: 'Nein',
        value: 'nein'
      }],
      drinking: [{
        label: 'Ja',
        value: 'ja'
      }, {
        label: 'Ja mit Partner',
        value: 'ja (partner)'
      }, {
        label: 'Nein',
        value: 'nein'
      }]
    }
  },
  methods: {
    encode (data) {
      return Object.keys(data)
        .map(key => `${encodeURIComponent(key)}=${encodeURIComponent(data[key])}`)
        .join('&')
    },
    onSubmit () {
      const axiosConfig = {
        header: { 'Content-Type': 'application/x-www-form-urlencoded' }
      }
      axios.post('/', this.encode({
        'form-name': 'ask-question', ...this.form
      }), axiosConfig)
    }
  }
}
</script>

<style scoped>

</style>
