<template>
  <div class="obs-page view">
    <Main>

      <h3>Publicação de livro</h3>
      <table>
        <tbody>
          <tr>
            <th>Título</th>
            <th>Autor</th>
          </tr>
          <tr v-for="(props, index) in all_livros" :key="index">
            <td class="title">
              <a :href="props.path" target="_blank" class="text-justify">
                {{ props.title }}
              </a>
            </td>
            <td class="autor">
              {{ props.autor }}
            </td>
          </tr>
        </tbody>
      </table>
      
      <h3>Anais da I JCPOLI</h3>
      <table>
        <tbody>
          <tr>
            <th>Título</th>
            <th>Autor</th>
          </tr>
          <tr v-for="(props, index) in all_anais2" :key="index">
            <td class="title">
              <a :href="props.path" target="_blank" class="text-justify">
                {{ props.title }}
              </a>
            </td>
            <td class="autor">
              {{ props.autor }}
            </td>
          </tr>
        </tbody>
      </table>

            <h3>Anais da II JCPOLI</h3>
        <table>
          <tbody>
            <tr>
              <th>Título</th>
              <th>Autor</th>
            </tr>
            <tr v-for="(props, index) in all_anais3" :key="index">
              <td class="title">
                <a :href="props.path" target="_blank" class="text-justify">
                  {{ props.title }}
                </a>
              </td>
              <td class="autor">
                {{ props.autor }}
              </td>
            </tr>
          </tbody>
        </table>

      <h3>Anais da IV Jornada Científica da ECEC</h3>
      <table>
        <tbody>
          <tr>
            <th>Título</th>
            <th>Autor</th>
          </tr>
          <tr v-for="(props, index) in all_anais" :key="index">
            <td class="title">
              <a :href="props.path" target="_blank" class="text-justify">
                {{ props.title }}
              </a>
            </td>
            <td class="autor">
              {{ props.autor }}
            </td>
          </tr>
        </tbody>
      </table>
    </Main>
  </div>
  
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator'
import Main from '../components/organization/Main.vue'
import { Anais, Anais2, Anais3, livros } from '@/storage/programacao/anais'

@Component({
  components: {
    Main
  }
})
export default class anais extends Vue {
  private all_anais: any
  private all_anais2: any
  private all_anais3: any
  private all_livros: any

  private title = 'Anais'


  constructor() {
    super()

    this.all_anais = Anais
    this.all_anais2 = Anais2
    this.all_anais3 = Anais3
    this.all_livros = livros
  }
}
</script>

<style scoped>
tr,
a,
td {
  font-size: 1.7rem;
  text-transform: uppercase;
}

th,
td {
  padding: 0.5rem;
  text-align: left;
}

table {
  margin-top: 2rem;
  width: 60vw;
  margin-bottom: 8rem;
}

@media screen and (max-width: 425px) {
  a,
  tr {
    font-size: 0.8rem;
  }

  table {
    width: 90vw;
  }

  .autor {
    font-size: 0.9rem;
  }

}
</style>
