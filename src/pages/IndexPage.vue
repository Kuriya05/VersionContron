HEAD
<template>
  <div class="q-pa-md" style="max-width: 400px">

    <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="name"
        label="your name *"
        hint="name-surname"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />

      <q-input
        filled
        type="number"
        v-model="age"
<<<<<<< HEAD
        label="your age *"
=======
        label="อายุของคุณ*"
>>>>>>> 4eecc82 (th-lang)
        lazy-rules
        :rules="[
          val => val !== null && val !== '' || 'Please type your age',
          val => val > 0 && val < 100 || 'Please type a real age'
        ]"
      />

      <q-toggle v-model="accept" label="I accept the license and terms" />

      <div>
        <q-btn label="ยอมรับ" type="submit" color="primary"/>
        <q-btn label="ล้างข้อมูล" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>

  </div>
 HEAD
 HEAD
</template>
 d30582c (eng-merge)

  <script>
import { useQuasar } from 'quasar'
import { ref } from 'vue'

export default {
  setup () {
    const $q = useQuasar()

    const name = ref(null)
    const age = ref(null)
    const accept = ref(false)
    return {
      name,
      age,
      accept,
      onSubmit () {
        if (accept.value !== true) {
          $q.notify({
            color: 'red-5',
            textColor: 'white',
            icon: 'warning',
            message: 'You need to accept the license and terms first'
          })
        }
        else {
          $q.notify({
            color: 'green-4',
            textColor: 'white',
            icon: 'cloud_done',
            message: 'Submitted'
          })
        }
      },
      onReset () {
        name.value = null
        age.value = null
        accept.value = false
      }
    }
  }
}
</script>
</template>
 7c179da (Add script part)

</template>
 fd0c64d (eng-nerVs)
