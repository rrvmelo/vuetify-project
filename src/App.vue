<template>
  <v-app :theme="theme">
    <!--SIDEBAR-->
    <v-navigation-drawer v-model="isDrawerOpen">

      <v-avatar class="mr-2">
        <v-img cover src="https://img.freepik.com/icones-gratis/do-utilizador_318-563642.jpg?size=626&ext=jpg"
          alt="user-image">
        </v-img>
      </v-avatar>
      USERNAME<br>
      CPF: XXX.XXX.XXX-XX


      <v-text-field v-model="search" label="Busca por protocolo" single-line hide-details>
      </v-text-field>
      <v-btn icon>
        <v-icon icon="mdi-magnify"></v-icon>
      </v-btn>


      <v-divider></v-divider>
      <v-list-subheader><strong>Menu</strong></v-list-subheader>
      <v-divider></v-divider>
      <v-list-item prepend-icon="mdi-home">Início</v-list-item>
      <v-list-item prepend-icon="mdi-inbox">Solicitaçõs em Análise</v-list-item>
      <v-list-item prepend-icon="mdi-currency-usd">Aguardando Pagamento</v-list-item>
      <v-list-item prepend-icon="mdi-close-thick">Com Pendências</v-list-item>
      <v-list-item prepend-icon="mdi-check-bold">Solcitações concluídas
        <template v-slot:append>
          <v-badge color="info" content="6" inline>
          </v-badge>
        </template>
      </v-list-item>

      <!--Ficha Informativa-->
      <v-list-group value="Ficha Informativa">
        <template #activator="{ props }">
          <v-list-item v-bind="props" prepend-icon="mdi-file-outline">
            Ficha Informativa
          </v-list-item>
        </template>
        <v-list-item prepend-icon="mdi-format-list-bulleted">Listar Fichas</v-list-item>
        <v-list-item prepend-icon="mdi-plus-thick">Relatório</v-list-item>
        <v-list-item prepend-icon="mdi-information-outline">Sobre a Ficha Informativa</v-list-item>
      </v-list-group>

      <!--FUMCRIA-->
      <v-list-group value="FUMCRIA">
        <template #activator="{ props }">
          <v-list-item v-bind="props" prepend-icon="mdi-emoticon-happy-outline">
            FUMCRIA
          </v-list-item>
        </template>
        <v-list-item prepend-icon="mdi-format-list-bulleted">Listar Doações</v-list-item>
        <v-list-item prepend-icon="mdi-plus-thick">Nova Doação</v-list-item>
        <v-list-item prepend-icon="mdi-list-box-outline">Extrato de Doações</v-list-item>
        <v-list-item prepend-icon="mdi-format-list-bulleted">Listar Doações ao FUMCRIA</v-list-item>
        <v-list-item prepend-icon="mdi-information-outline">Sobre o FUMCRIA</v-list-item>
        <v-list-item prepend-icon="mdi-gavel">Legislação do FUMCRIA</v-list-item>
        <v-list-item prepend-icon="mdi-magnify">Lista de Entidades</v-list-item>
        <v-list-item prepend-icon="mdi-help">Dúvidas Frequentes</v-list-item>
      </v-list-group>

      <!--Agendar Serviço Presencial-->
      <v-list-group value="Agendar Serviço Presencial">
        <template #activator="{ props }">
          <v-list-item v-bind="props" prepend-icon="mdi-calendar-month">
            Agendar Serviço Presencial
          </v-list-item>
        </template>
        <v-list-item prepend-icon="mdi-format-list-bulleted">Meus Agendamentos</v-list-item>
        <v-list-item prepend-icon="mdi-plus-thick">Novo Agendamento</v-list-item>
      </v-list-group>

      <!--Licitações-->
      <v-list-group value="Licitações">
        <template #activator="{ props }">
          <v-list-item v-bind="props" prepend-icon="mdi-file-document-outline">
            Licitações
          </v-list-item>
        </template>
        <v-list-item prepend-icon="mdi-format-list-bulleted">Listar Licitações</v-list-item>
        <v-list-item prepend-icon="mdi-close-thick">Licitações Suspensas</v-list-item>
        <v-list-item prepend-icon="mdi-check-bold">Licitações Encerradas</v-list-item>
        <v-list-item prepend-icon="mdi-download">Instruções Fornecedores</v-list-item>
      </v-list-group>

      <!--Fiscalizações-->
      <v-list-group value="Fiscalizações">
        <template #activator="{ props }">
          <v-list-item v-bind="props" prepend-icon="mdi-progress-check">
            Fiscalizações
          </v-list-item>
        </template>
        <v-list-item prepend-icon="mdi-cash">Multas</v-list-item>
      </v-list-group>

      <!--Zoneamento-->
      <v-list-group value="Zoneamento">
        <template #activator="{ props }">
          <v-list-item v-bind="props" prepend-icon="mdi-map-outline">
            Zoneamento
          </v-list-item>
        </template>
        <v-list-item prepend-icon="mdi-format-list-bulleted">Consultar Viabilidade</v-list-item>
      </v-list-group>

      <!--Meio Ambiente-->
      <v-list-group value="Meio Ambiente">
        <template #activator="{ props }">
          <v-list-item v-bind="props" prepend-icon="mdi-leaf">
            Meio Ambiente
          </v-list-item>
        </template>
        <v-list-item prepend-icon="mdi-folder-open-outline">Solicitações Não Enviadas</v-list-item>
        <v-list-item prepend-icon="mdi-plus-thick">Solicitar Serviço</v-list-item>
        <v-list-item prepend-icon="mdi-domain">Empresas Credenciadas</v-list-item>
      </v-list-group>

      <!--PROCON-->
      <v-list-group value="PROCON">
        <template #activator="{ props }">
          <v-list-item v-bind="props" prepend-icon="mdi-alpha-p-circle-outline">
            PROCON
          </v-list-item>
        </template>
        <v-list-item prepend-icon="mdi-format-list-bulleted">Solicitações Retorno</v-list-item>
        <v-list-item prepend-icon="mdi-plus-thick">Solicitar Serviço</v-list-item>
        <v-list-item prepend-icon="mdi-information-outline">Sobre o PROCON</v-list-item>
      </v-list-group>

      <!--Pacicipação Cidadã-->
      <v-list-group value="Pacicipação Cidadã">
        <template #activator="{ props }">
          <v-list-item v-bind="props" prepend-icon="mdi-chat-processing">
            Pacicipação Cidadã
          </v-list-item>
        </template>
        <v-list-item prepend-icon="mdi-chat-processing-outline">Participar</v-list-item>
        <v-list-item prepend-icon="mdi-format-list-bulleted">Minhas manifestações - PPA</v-list-item>
        <v-list-item prepend-icon="mdi-gavel">Votação LDO</v-list-item>
        <v-list-item prepend-icon="mdi-format-list-bulleted">Resultado das Votações</v-list-item>
      </v-list-group>

      <!--Sobre o Fácil-->
      <v-list-item prepend-icon="mdi-information">Sobre  Fácil</v-list-item>
    </v-navigation-drawer>

    <!--HEADER-->
    <v-app-bar flat class="border-b bg-light-blue-darken-1">
      <v-app-bar-nav-icon @click="isDrawerOpen = !isDrawerOpen"></v-app-bar-nav-icon>
      <v-app-bar-title>
        <v-btn><strong>Fácil</strong></v-btn>
      </v-app-bar-title>

      <template #append>
        <!--Button Toggle-->
        <v-btn :prepend-icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'" @click="onToggleTheme">
        </v-btn>
        <v-btn icon>
          <v-badge dot color="#fc641a">
            <v-icon icon="mdi-bell-outline"></v-icon>
          </v-badge>
        </v-btn>
        <v-btn>
          <v-avatar class="mr-2">
            <v-img cover src="https://img.freepik.com/icones-gratis/do-utilizador_318-563642.jpg?size=626&ext=jpg"
              alt="user-image">
            </v-img>
          </v-avatar>
          user-full-name
        </v-btn>
      </template>
    </v-app-bar>

    <!--MAIN-->
    <v-main>
      <v-container fluid>
        <h2>Início</h2>
        <v-row>
          <v-col v-for="item in items" 
          cols="12" sm="6" md="4" lg="3">
            <!--construção do card-->
            <v-card>
              <!--add imagem no card-->
              <v-img :src="item.coverimage" height="200px" class="align-end" cover alt="item.detail">
              </v-img>
              <v-card-title class="text-white" v-text="item.name"></v-card-title>
              <v-card-text v-text="item.detail"></v-card-text>
              <v-divider></v-divider>
              <v-card-actions>
                <v-btn>
                  Learn More
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>

    <!--FOOTER-->
    <v-footer>
      //<pre>Departamento de Tecnologia da Informação</pre>
    </v-footer>
  </v-app>
</template>

<script setup>
import HelloWorld from '@/components/HelloWorld.vue'
import { ref } from 'vue';
//Sidebar Config
const isDrawerOpen = ref(false);
//Theme Config Toogle
const theme = ref('dark')
function onToggleTheme() {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
}

const items = ref([])

fetch('https://www.melivecode.com/api/attractions').then(res => res.json()).then((result) => {
  items.value = result
})

</script>
