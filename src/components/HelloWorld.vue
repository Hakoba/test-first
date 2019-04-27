<template>
  <v-container>
    <v-layout
      text-xs-center
      wrap
    >
      <v-flex
        mb-5
        xs12
      >
        <h2 class="headline font-weight-bold mb-3">Калькулятор</h2>

        <v-layout justify-center>
         <v-card width="300px"> 
           
          <v-text-field
            class="text-input"
            v-model="firstAddend"
            :rules="addendRules"
            label="Первое число:"
            required
          ></v-text-field>
          <br>
           <v-text-field
           class="text-input"
            v-model="secondAddend"
            :rules="addendRules"
            label="Второе число:"
            required
          ></v-text-field>
             <v-btn @click="returnSum" color="info">Сложить</v-btn>
         </v-card>
        </v-layout>

      </v-flex>
<!-- 
      <v-flex
        xs12
        mb-5
      >
        <h2 class="headline font-weight-bold mb-3">Important Links</h2>

        <v-layout justify-center>
          <a
            v-for="(link, i) in importantLinks"
            :key="i"
            :href="link.href"
            class="subheading mx-3"
            target="_blank"
          >
            {{ link.text }}
          </a>
        </v-layout>
      </v-flex>

      <v-flex
        xs12
        mb-5
      >
        <h2 class="headline font-weight-bold mb-3">Ecosystem</h2>

        <v-layout justify-center>
          <a
            v-for="(eco, i) in ecosystem"
            :key="i"
            :href="eco.href"
            class="subheading mx-3"
            target="_blank"
          >
            {{ eco.text }}
          </a>
        </v-layout>
      </v-flex> -->
    </v-layout>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      firstAddend: 0.1,
      secondAddend: 0.2,
      addendRules: [
        v => !!v || 'Должен быть не пустым',
        v => /^\d[\d.]*$/.test(v) || 'должны быть использованы только цифры и точка (для дробных чисел)'
      ]
    }),
    methods: {
      returnSum(){
        confirm(`Ответ: ${(parseFloat(this.firstAddend)+parseFloat(this.secondAddend)).toFixed(2)}`);
      //  alert((parseFloat(this.firstAddend)+parseFloat(this.secondAddend)).toFixed(10));
      }
    }
  }
</script>

<style>
.text-input{
  margin: 5px 20px;
}
</style>
