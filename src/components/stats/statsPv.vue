<template>
    <div>
        <v-row justify="space-between">
            <v-col cols="12" sm="4">
        <v-card
    class="mx-15 mt-15 elevation-20"
    color="green lighten-1"
    dark
    style="max-width: 300px;"
  >
    <v-row justify="space-between">
      <v-col cols="8">
        <v-card-title>
          <div>
            <div class="text-h5">
            المحاضر
            <div>المعالجة</div>
            </div>
          </div>
        </v-card-title>
      </v-col>
      <v-icon
        class="shrink ma-2"
        contain
        size="35px"
        style="flex-basis: 65px"
      >mdi-progress-check</v-icon>
    </v-row>
    <v-divider dark class="mt-2"></v-divider>
    <v-card-actions class="text-h6 pa-4">
      العدد الاجمالي
      <v-spacer></v-spacer>
      <span class="text-h6 ml-10">
        ({{ traite }})
      </span>
      
    </v-card-actions>
  </v-card></v-col>
  <v-col cols="12" sm="4">
  <v-card
    class="mx-15 mt-15 elevation-20"
    color="orange lighten-1"
    dark
    style="max-width: 300px;"
  >
    <v-row justify="space-between">
      <v-col cols="8">
        <v-card-title>
          <div>
            <div class="text-h5">
              المحاضر  في 
             <div>طور المعالجة</div>
            </div>
          </div>
        </v-card-title>
      </v-col>
      <v-icon
        class="shrink ma-2"
        contain
        size="35px"
        style="flex-basis: 65px"
      >mdi-progress-alert</v-icon>
    </v-row>
    <v-divider dark></v-divider>
    <v-card-actions class="text-h6 pa-4">
      العدد الاجمالي
      <v-spacer></v-spacer>
      <span class="text-h6 ml-10">
        ({{  nontraite }})
      </span>
      
    </v-card-actions>
  </v-card></v-col>
  <v-col cols="12" sm="4">
  <v-card
    class="mx-15 mt-15 elevation-20"
    color="red lighten-1"
    dark
    style="max-width: 300px;"
  >
    <v-row justify="space-between">
      <v-col cols="8">
        <v-card-title>
          <div>
            <div class="text-h5">
           &nbsp;المحاضر غير
             <div>المعالجة</div>
            </div>
          </div>
        </v-card-title>
      </v-col>
      <v-icon
        class="shrink ma-2"
        contain
        size="35px"
        style="flex-basis: 65px"
      >mdi-progress-close</v-icon>
    </v-row>
    <v-divider dark></v-divider>
    <v-card-actions class="text-h6 pa-4">
      العدد الاجمالي
      <v-spacer></v-spacer>
      <span class="text-h6 ml-10">
        ({{ traite }})
      </span>
      
    </v-card-actions>
  </v-card></v-col>
  </v-row>
 <v-card class="mt-10">
  <div>
    <v-data-table
    :headers="headers"
    :items="plaint" no-data-text="معلومات غير متاحة"
     class="elevation-1 font-weight-black"
    hide-default-footer
    :loading="table_vide"
     loading-text="إنتظر قليلا"
    >
    </v-data-table>
  </div>
  <div class="text-center">
    <v-pagination
    v-model="pagination.current"
    :length="pagination.total"
    @input="onPageChange"
></v-pagination>
    </div>
    
     </v-card>
    </div>
</template>

<script>
  export default {
    data: () => ({
      traite: 4,
      nontraite: 10,
      encoretrt: 6,
    traiteds:{},
    headers: [
          { text: 'نوع المحضر', value: 'typepvsID' },
          { text: ' تاريخ التسجيل', value: 'dateEnregPvs' },
          { text: '  رقم الإرسالية', value: 'numEnvoi' },
          { text: 'موضوع المحضر', value: 'sujetpvs' },
          { text: 'معالجة؟', value: 'trait' },
          ],
         pvs:[],
         load:false,
            pagination: {
                current: 1,
                total: 0
            }
    }),
  }
</script>
