<template>
  <v-app>
      <v-tabs align-with-title class="hidden-sm-and-down" >
          <v-tab>Об анализе данных</v-tab>
          <v-tab>О машинном обучении</v-tab>
          <v-tab>Возможности {{ productName }}</v-tab>
          <v-tab>Лаборатория</v-tab>
          <v-spacer></v-spacer>
          <v-layout align-center justify-end class="mr-5">
            <v-flex shrink>
              <v-menu offset-y>
                <template v-slot:activator="{ on }">
                  <v-btn flat v-on="on"> 
                    {{ account.name }}
                    <v-icon>arrow_drop_down</v-icon>
                  </v-btn>
                </template>
                <v-list>
                  <v-list-tile
                    v-for="(item, index) in accountMenu"
                    :key="index"
                    @click=""
                  >
                  <v-list-tile-title>{{ item }}</v-list-tile-title>
                </v-list-tile>
              </v-list>
              </v-menu>
            </v-flex> 
            <v-flex shrink>
              <v-avatar
                size="40"
                color="blue lighten-4"
              >
               <v-icon dark>account_circle</v-icon>
              </v-avatar>
            </v-flex>
          </v-layout>
      </v-tabs>

      <v-navigation-drawer permanent>
      <v-toolbar flat>
        <v-list>
          <v-list-tile>
            <v-list-tile-title class="title">
              Application
            </v-list-tile-title>
          </v-list-tile>
        </v-list>
      </v-toolbar>
  
      <v-divider></v-divider>
  
      <v-list dense class="pt-0">
        <v-list-tile
          v-for="(item) in {1:'one', 2:'two', 3:'trhee'}"
          :key="item"
          @click=""
        >
          <v-list-tile-action>
            {{ item }}
          </v-list-tile-action>
  
          <v-list-tile-content>
            <v-list-tile-title>{{ item.title }}</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <router-view></router-view>
  </v-app>
</template>

<script>

export default {
  name: 'App',
  components: {

  },
  data () {
    return {
      productName: "ML-UI",
      account: {
        name: "Техновизор МЛ"
      },
      accountMenu: {
        profile: 'Профиль',
        messages: 'Сообщения',
        exit: 'Выход'
      }
    }
  }
}
</script>
