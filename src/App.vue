<template>
  <v-app  theme="">
   <v-navigation-drawer v-model="isDrawerOpen">

    <v-list>
      <v-list-subheader>Menu</v-list-subheader>
      <v-list-item prepend-icon="mdi-home-outline">Home</v-list-item>
      <v-list-item prepend-icon="mdi-account-outline">User</v-list-item>
    
      <v-list-group value="Clientes">
        <template #activator="{props}">

          <v-list-item
          v-bind="props"
          prepend-icon="mdi-account-circle"
          
          >
          Clientes

          </v-list-item>
          
        </template>
        <v-list-item
        prepend-icon="mdi-currency-usd"
        >
          Faturamento
        </v-list-item>
        <v-list-item
        prepend-icon="mdi-chart-line"
        >
          Relatório
        </v-list-item>
      </v-list-group>

    </v-list>

   </v-navigation-drawer>

    <v-app-bar flat class="border-b" >
      <v-app-bar-nav-icon @click="isDrawerOpen = !isDrawerOpen" ></v-app-bar-nav-icon>
      <v-app-bar-title>Meu App</v-app-bar-title>


      
      <template #append>
        <v-btn icon class="mr-2">

          <v-badge dot color="info">
            <v-icon icon="mdi-bell-outline"></v-icon>
          </v-badge>
        </v-btn>

          <v-menu>

          
            <template #activator="{props}">

              
              <v-avatar v-bind="props"
              >
              <v-img 
              src="https://img.assinaja.com/upl/lojas/mundosinfinitos/imagens/foto-one-piece.png"
              cover
              ></v-img>
            </v-avatar>
              
            </template>

            <v-card min-width="200px">
                <v-list density="compact" :lines="false" nav>
                  <v-list-item prepend-icon="mdi-account-outline">
                    
                    <v-list-item-title>Meu Perfil</v-list-item-title>
                    
                  </v-list-item>
                  <v-list-item prepend-icon="mdi-heart-outline">
                    
                    <v-list-item-title>Favoritos</v-list-item-title>
                    
                  </v-list-item>
                </v-list>

            </v-card>
            
          
        </v-menu>
        
      </template>

    

    </v-app-bar>
    <v-main>
   
      <v-container>
       
        <h1 class="mb-6" v-ripple>Dashboard</h1>
        

        
        <v-card class="border mb-4" flat>
          <div class="d-flex justify-space-between "   >
            <v-card-title>Ultimos Usuario</v-card-title>
            <v-card-title>
              <v-btn @click="isDialogOpen = true" v-bind="props" variant="tonal" size="small" >Adicionar usuarios</v-btn>
              <v-dialog width="600px"
              v-model="isDialogOpen"
              > 
                

                <v-card>
                  <v-card-title>Adicionar Usuario</v-card-title>
                  <v-card-text>
                  <div>
                    <v-row>
                      <v-col>
                        <v-text-field label="Nome" variant="outlined"></v-text-field>
                      
                      </v-col>
                      <v-col>
                        <v-text-field 
                        label="Email"
                         variant="outlined"
                         :rules="emailRules"
                         ></v-text-field>
                      </v-col>
                    </v-row>

                    <v-select label="Cargo" variant="outlined" :items="['Admin', 'Gerente', 'Convidado' ]"></v-select>
                  </div>
                  </v-card-text>
                  <v-card-actions >
                    <v-spacer></v-spacer>
                    <v-btn variant="tonal" color="error" @click="isDialogOpen = false">Cancelar</v-btn>

                    <v-btn variant="tonal" color="success">Salvar</v-btn>

                  </v-card-actions>
                </v-card>
              </v-dialog>


            </v-card-title>

  
          </div>
          <v-table density="compact">
            <thead>
              <tr>
                <th>
                  Nome
                </th>
                <th>
                  email
                </th>
                <th>
                  Cargo
                </th>
                <th>
                  Ações
                </th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>guilherme</td>
                <td>guilherme@gmail.com</td>
                <td>
                  
                <v-chip color="primary" size="small" variant="outlined">Admin</v-chip>
              </td>
                <td>
                  <v-btn   variant="tonal" color="primary" density="compact">
                    Editar
                  </v-btn>
                </td>

              </tr>
              <tr>
                <td>Isadora</td>
                <td>Isa@gmail.com</td>
                <td>

                <v-chip color="success" size="small" variant="outlined">Gerente</v-chip>

                </td>
                <td>
                  <v-btn variant="tonal" color="primary" density="compact">
                    Editar
                  </v-btn>
                </td>
              </tr>
              <tr>
                <td>Bel</td>
                <td>bel@gmail.com</td>
                <td>

                <v-chip  size="small" variant="outlined">Convidado</v-chip>

                </td>
                <td>
                  <v-btn variant="tonal" color="primary" density="compact">
                    Editar
                  </v-btn>
                </td>
              </tr>
            </tbody>
          </v-table>
        </v-card>
          
        
        <br>
        <v-row >
          <v-col cols="12" sm="6" md="4" lg="3">
            <v-card class="border">
              <v-img 
              class="align-end text-white"
              src="https://media.istockphoto.com/id/1304292664/pt/foto/sao-paulo.jpg?s=1024x1024&w=is&k=20&c=0oeNg7_7KDcuaOUAzu42f0iyPDIiM2PjCEOfhLvvFMY=">
                <v-card-title >Cidades</v-card-title>
              </v-img>
              <v-card-subtitle class="pt-3">imagem ilustrada</v-card-subtitle>
              <v-card-text>
                <div>
                  alguns predios
                </div>
                <div>Testesssssssssssssssssssss</div>
              </v-card-text>
              <v-card-actions>
                <v-btn color="primary" variant="outlined">Ver mais</v-btn>
                
                <v-btn prepend-icon="mdi-cart"color="blue" variant="tonal">Comprar</v-btn>
                <v-btn icon="mdi-home" color="blue" variant="tonal"> </v-btn>
                


              </v-card-actions>
            </v-card>

          </v-col>
         
          <v-col cols="12" sm="6" md="4" lg="3">
            <v-card class="border">
              <v-img 
              class="align-end text-white"
              src="https://media.istockphoto.com/id/1304292664/pt/foto/sao-paulo.jpg?s=1024x1024&w=is&k=20&c=0oeNg7_7KDcuaOUAzu42f0iyPDIiM2PjCEOfhLvvFMY=">
                <v-card-title >Cidades</v-card-title>
              </v-img>
              <v-card-subtitle class="pt-3">imagem ilustrada</v-card-subtitle>
              <v-card-text>
                <div>
                  alguns predios
                </div>
                <div>Testesssssssssssssssssssss</div>
              </v-card-text>
              <v-card-actions>
                <v-btn color="primary" variant="outlined">Ver mais</v-btn>
                
                <v-btn prepend-icon="mdi-cart"color="blue" variant="tonal">Comprar</v-btn>
                <v-btn icon="mdi-home" color="blue" variant="tonal"> </v-btn>
                


              </v-card-actions>
            </v-card>

          </v-col>
          <  <v-col cols="12" sm="6" md="4" lg="3">
            <v-card class="border">
              <v-img 
              class="align-end text-white"
              src="https://media.istockphoto.com/id/1304292664/pt/foto/sao-paulo.jpg?s=1024x1024&w=is&k=20&c=0oeNg7_7KDcuaOUAzu42f0iyPDIiM2PjCEOfhLvvFMY=">
                <v-card-title >Cidades</v-card-title>
              </v-img>
              <v-card-subtitle class="pt-3">imagem ilustrada</v-card-subtitle>
              <v-card-text>
                <div>
                  alguns predios
                </div>
                <div>Testesssssssssssssssssssss</div>
              </v-card-text>
              <v-card-actions>
                <v-btn color="primary" variant="outlined">Ver mais</v-btn>
                
                <v-btn prepend-icon="mdi-cart"color="blue" variant="tonal">Comprar</v-btn>
                <v-btn icon="mdi-home" color="blue" variant="tonal"> </v-btn>
                


              </v-card-actions>
            </v-card>

          </v-col>
          <v-col cols="12" sm="6" md="4" lg="3">
            <v-card class="border">
              <v-img 
              class="align-end text-white"
              src="https://media.istockphoto.com/id/1304292664/pt/foto/sao-paulo.jpg?s=1024x1024&w=is&k=20&c=0oeNg7_7KDcuaOUAzu42f0iyPDIiM2PjCEOfhLvvFMY=">
                <v-card-title >Cidades</v-card-title>
              </v-img>
              <v-card-subtitle class="pt-3">imagem ilustrada</v-card-subtitle>
              <v-card-text>
                <div>
                  alguns predios
                </div>
                <div>Testesssssssssssssssssssss</div>
              </v-card-text>
              <v-card-actions>
                <v-btn color="primary" variant="outlined">Ver mais</v-btn>
                
                <v-btn prepend-icon="mdi-cart"color="blue" variant="tonal">Comprar</v-btn>
                <v-btn icon="mdi-home" color="blue" variant="tonal"> </v-btn>
                


              </v-card-actions>
            </v-card>

          </v-col>
       

        </v-row>
    </v-container>
    </v-main>
  </v-app>
</template>

<script setup>
  import { ref } from 'vue';


  const isDrawerOpen = ref(false)
  const isDialogOpen = ref(false)
  const emailRules = [
    value => {
      if(value) return true

      return 'O email é obrigatorio'
    },
    value => {
      if ( value.includes('@')){
        return true
      }

      return 'email invalido'
    }
  ]

</script>


