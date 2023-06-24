<template>
  <v-app :theme="theme">
    <!--SIDEBAR-->
    <v-navigation-drawer v-model="isDrawerOpen">

      <v-text-field v-model="search" label="Busca por protocolo" single-line hide-details>
      </v-text-field>
      <v-btn icon>
        <v-icon icon="mdi-magnify"></v-icon>
      </v-btn>

      <v-divider></v-divider>
      <v-list-subheader><span>Menu</span></v-list-subheader>
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
      <v-list>
        <v-list-group value="Ficha Informativa">
          <template #activator="{ props }">
            <v-list-item v-bind="props" prepend-icon="mdi-file-outline" title="Ficha Informativa">
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
      </v-list>

        <!--Sobre o Fácil-->
        <v-list-item prepend-icon="mdi-information">Sobre Fácil</v-list-item>
    </v-navigation-drawer>



    <!--HEADER-->
    <v-app-bar flat class="border-b bg-light-blue-darken-1">
      <v-app-bar-nav-icon @click="isDrawerOpen = !isDrawerOpen"></v-app-bar-nav-icon>
      <v-app-bar-title>
        <v-btn to="#"><strong>Fácil</strong></v-btn>
      </v-app-bar-title>

      <template #append>
        <!--Button Toggle-->
        <v-btn :prepend-icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'" @click="onToggleTheme">
        </v-btn>
        <!--Notify-->
        <v-menu>
          <template #activator="{ props }">
            <v-btn icon v-bind="props">
              <v-badge dot color="#fc641a">
                <v-icon icon="mdi-bell-outline"></v-icon>
              </v-badge>
            </v-btn>
          </template>
          <v-card width="270px">
            <v-list :lines="false" density="compact" nav>
              <v-list-item><v-list-item-title>Você não tem notificações</v-list-item-title></v-list-item>
              <v-divider></v-divider>
              <v-list-item><v-list-item-title>Não lidas</v-list-item-title>
                <template v-slot:append>
                  <v-badge color="#fc641a" :content="99" inline text-color="white">
                  </v-badge>
                </template>
              </v-list-item>
              <v-divider></v-divider>
              <v-list-item prepend-icon="mdi-inbox">
                <v-list-item-title text-h6>Área Livre</v-list-item-title>
                <v-list-item-subtitle text mb-1>Lorem</v-list-item-subtitle>
                <text-medium-emphasis>Lorem ipsum dolor sit amet consectetur adipisicing elit. </text-medium-emphasis>
              </v-list-item>

              <v-divider></v-divider>
              <v-btn prepend-icon="mdi-home" color="white" to="#">Ir para a página inicial</v-btn>
            </v-list>

          </v-card>
        </v-menu>
        <!--Avatar-->
        <v-menu>
          <template #activator="{ props }">
            <v-avatar class="mr-2" v-bind="props">
              <v-img cover src="https://img.freepik.com/icones-gratis/do-utilizador_318-563642.jpg?size=626&ext=jpg"
                alt="user-image">
              </v-img>
            </v-avatar>
            JOHN DOE
          </template>

          <v-card min-width="200px">
            <v-list :lines="false" density="compact" nav>
              <v-list-item><v-list-item-title>Último Acesso DD/MM/YYYY HH24:MI:SS</v-list-item-title></v-list-item>
              <v-divider></v-divider>
              <v-list-item><v-list-item-title>Nome Completo: </v-list-item-title>JOHN DOE</v-list-item>
              <v-list-item><v-list-item-title>Email: </v-list-item-title>johndoe@email.com</v-list-item>
              <v-list-item><v-list-item-title>CPF: </v-list-item-title>123.XXX.XXX-00</v-list-item>
            </v-list>
          </v-card>
          <v-btn prepend-icon="mdi-account" color="white" to="#">Ver Perfil</v-btn>
          <v-btn prepend-icon="mdi-logout" color="error" to="#">Sair do Sistema</v-btn>
        </v-menu>
      </template>
    </v-app-bar>

    <!--MAIN-->
    <v-main>
      <v-container fluid>
        <h2 class="mb-6">Início</h2>

        <v-card flat class="border mb-4">
          <div class="d-flex justify-space-between">
            <v-card-title>Últimos Usuários Cadastrados</v-card-title>

            <!-- Button New User -->
            <v-card-title>
              <v-btn @click="isDialogOpen = true" variant="tonal">Criar novo Usuário</v-btn>
              <v-dialog v-model="isDialogOpen" width="85vh">
                <v-card>
                  <v-card-text>
                    Hey
                    <v-btn color="white">Enviar</v-btn>
                    <v-btn color="error">fechar</v-btn>
                  </v-card-text>

                </v-card>
              </v-dialog>
            </v-card-title>


          </div>
          <v-table>
            <thead>
              <tr>
                <th>Nome</th>
                <th>Email</th>
                <th>Função</th>
                <th>Ações</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>John Doe</td>
                <td>john.doe@email.com</td>
                <td>User</td>
                <td>
                  <v-btn icon="mdi-pencil" variant="tonal" color="primary"></v-btn>
                </td>
              </tr>
              <tr>
                <td>Jane Doe</td>
                <td>jane.doe@email.com</td>
                <td>Manager</td>
                <td>
                  <v-btn icon="mdi-pencil" variant="tonal" color="primary"></v-btn>
                </td>
              </tr>
              <tr>
                <td>No More</td>
                <td>nmore@email.com</td>
                <td>Admin</td>
                <td>
                  <v-btn icon="mdi-pencil" variant="tonal" color="primary"></v-btn>
                </td>
              </tr>
            </tbody>
          </v-table>
        </v-card>


        <v-row>
          <v-col v-for="item in items" cols="12" sm="6" md="4" lg="3">
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

      <!--FOOTER-->
      <v-footer>
        <pre>Departamento de Tecnologia da Informação</pre>
      </v-footer>

    </v-main>

  </v-app>
</template>

<script setup>
import HelloWorld from '@/components/HelloWorld.vue'
import { ref } from 'vue';

//Sidebar Config
const isDrawerOpen = ref(false);
//Sidebar Sub Menu
const isSubSide = ref(false);
//Show Dialog
const isDialogOpen = ref(false);
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
