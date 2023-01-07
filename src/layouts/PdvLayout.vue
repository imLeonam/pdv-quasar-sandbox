<template>
  <q-page class="row justify-start q-pa-md">
    <div class="row">
      <div class="col">
        <GenericCard title="Adicionar Item">
          <template v-slot:content>
            <div class="row">
              <div class="col q-mr-md">
                <q-input outlined label="Quantidade"></q-input>
              </div>
              <div class="col">
                <q-input outlined label="Código de Barras/Cód"></q-input>
              </div>
            </div>
            <div class="row q-mt-md">
              <div class="col-7">
                <q-item-label>Produto</q-item-label>
                <q-item-label>{{ product }}</q-item-label>
              </div>
              <div class="col-2">
                <q-item-label>Valor Unitário</q-item-label>
              </div>
              <div class="col-1"><q-item-label> Qtd.</q-item-label></div>
              <div class="col-2">
                <q-item-label> Valor Total </q-item-label>
              </div>
            </div>
          </template>
          <template v-slot:actions>
            <q-space />
            <q-btn
              icon="close"
              rounded
              label="Cancelar // Ctrl + Esc"
              color="negative"
            />
            <q-btn
              icon="check"
              rounded
              label="Finalizar // Ctrl + Enter"
              color="positive"
            />
          </template>
        </GenericCard>
        <GenericCard title="Atalhos">
          <template v-slot:content>
            <div class="row">
              <q-btn
                class="q-ma-sm"
                rounded
                size="md"
                icon="person"
                label="Cliente // F5"
                color="primary"
              ></q-btn>
              <q-btn
                class="q-ma-sm"
                rounded
                size="md"
                icon="error"
                label="Remover Item // F6"
                color="orange"
                text-color="black"
              ></q-btn>
              <q-btn
                class="q-ma-sm"
                rounded
                size="md"
                icon="sell"
                label="Vendas // F7"
                color="primary"
              ></q-btn>
              <q-btn
                class="q-ma-sm"
                rounded
                size="md"
                icon="description"
                label="Notas Fiscais // F8"
                color="primary"
              ></q-btn>
              <q-btn
                class="q-ma-sm"
                rounded
                size="md"
                icon="close"
                label="Sair // F9"
                color="negative"
              ></q-btn>
            </div>
          </template>
        </GenericCard>
      </div>
      <div class="col">
        <DataTable selectable title="Items" />
      </div>
    </div>
  </q-page>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

import GenericCard from '@sharedComponents/dynamic/GenericCard.vue';
import DataTable from '@sharedComponents/DataTableGrid.vue';

export default defineComponent({
  name: 'PdvLayout',
  components: { GenericCard, DataTable },
  methods: {
    sayHello() {
      console.log('hello');
    },
  },
  setup() {
    return {
      cpf: ref('108.634.709.98'),
      product: ref(''),
    };
  },
});
</script>
