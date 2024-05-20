<template>
  <q-page class="row q-pa-lg justify-evenly">
    <q-card flat bordered class="col-xs-12 col-md-3" style="min-height: calc(100vh - 100px)">
      <q-card-section>
        <div class="text-h6">
          Ideias de doações
        </div>

        <ul>
          <li>cesta básica</li>
          <li>cobertores</li>
          <li>roupas íntimas novas (masculinas e femininas)</li>
          <li>meias</li>
          <li>água sanitária</li>
          <li>sabão em pó</li>
          <li>escova e pasta de dente</li>
          <li>desodorante</li>
          <li>xampu</li>
          <li>panos de limpeza</li>
          <li>papel higiênico</li>
          <li>botas de borracha</li>
          <li>baldes</li>
          <li>panos</li>
          <li>vassouras (com cabo)</li>
          <li>rodos (com cabo)</li>
          <li>escova de limpeza</li>
          <li>luvas</li>
          <li>colchões (novos ou em bom estado)</li>
          <li>roupa de cama</li>
          <li>roupa de banho</li>
          <li>cobertores</li>
          <li>ração animal</li>
          <li>cestas básicas fechadas</li>
          <li>fraldas infantis e geriátricas</li>
          <li>arroz</li>
          <li>feijão</li>
          <li>macarrão</li>
          <li>açúcar</li>
          <li>farinha de trigo</li>
          <li>café</li>
          <li>sal</li>
          <li>óleo</li>
          <li>biscoito</li>
          <li>achocolatado</li>
          <li>leite em pó</li>
          <li>enlatados (atum, sardinha, legumes)</li>
        </ul>
      </q-card-section>
    </q-card>

    <q-card flat bordered class="col-xs-12 col-md-8 row" style="min-height: calc(100vh - 100px)">
      <q-card-section>
        <div class="text-h6">
          Onde doar
        </div>

        <div class="row">
          <card-donation-place class="col-auto" v-for="info in dados" :title="info.title" :overline="info.overline"
            :key="info.title">
            <template #media>
              <google-map :query="info.address"></google-map>

            </template>

            <template #expand-content>
              O que doar: Alimentos não perecíveis, cestas básicas montadas, água, artigos de higiene, cobertores,
              colchões,
              roupas

            </template>

            * O local realiza também a entrega de donativos para pessoas físicas.
          </card-donation-place>
        </div>

      </q-card-section>
    </q-card>
  </q-page>
</template>

<script setup lang="ts">
import CardDonationPlace from "src/components/CardDonationPlace.vue"
import GoogleMap from "src/components/GoogleMap.vue"

// eslint-disable-next-line @typescript-eslint/no-unused-vars
const dados =
  [
    {
      title: "Ginásio do Demhab - O local é ponto de referência para doações na Capital.",
      overline: "Horário de funcionamento: 24 horas",
      address: "Rua Conde D’Eu, 66 – bairro Santana",
      obs: "O que doar: cobertores (principalmente), colchões, água e produtos de higiene."
    },

    {
      title: "Sindicato Médico do Rio Grande do Sul (Simers)",
      overline: "Rua Coronel Corte Real, 975 – bairro Petrópolis",
      address: "Horário de funcionamento: 24 horas",
      obs: "O que doar: Alimentos não perecíveis, cestas básicas montadas, água, artigos de higiene, cobertores, colchões"
    },

    {
      title: "Estádio Olímpico",
      overline: "Largo Patrono Fernando Kroeff, 1",
      address: "Horário de funcionamento: 9h às 18h",
      obs: "O que doar: Alimentos não perecíveis, cestas básicas montadas, água, artigos de higiene, cobertores, colchões"
    },

    {
      title: "Conselho Regional de Medicina do Estado do Rio Grande do Sul (Cremers)",
      overline: "Rua Bernardino Pires, 415 – bairro Santana",
      address: "Horário de funcionamento: das 9h às 19h",
      obs: "O que doar: Alimentos não perecíveis, cestas básicas montadas, água, artigos de higiene, cobertores, colchões"
    },

    {
      title: "Associação Médica do Rio Grande do Sul (AMRIGS)",
      overline: "Apenas medicamentos e produtos médicos",
      address: "Av. Ipiranga, 5.311 – bairro Partenon",
      obs: "Horário de funcionamento: das 9h às 18h"
    },

    {
      title: "Ministério Público RS (MPRS)",
      overline: "Rua Santana 440",
      address: "Horário de Funcionamento: 9h às 18h",
      obs: "O que doar: Alimentos não perecíveis, cestas básicas montadas, água, artigos de higiene, cobertores, colchões"
    },

    {
      title: "Depósito da Defesa Civil Municipal",
      address: "Rua La Plata, 693",
      overline: "Horário de Funcionamento: das 9h às 18h",
      obs: "O que doar: Alimentos não perecíveis, cestas básicas montadas, água, artigos de higiene, cobertores, colchões"
    },

    {
      title: "Shopping Total - estacionamento gratuito para doações",
      overline: "Horário de Funcionamento: das 10h às 22h",
      address: "Avenida Cristovão Colombo, 545",
      obs: "O que doar: Alimentos não perecíveis, cestas básicas montadas, água, artigos de higiene, cobertores, colchões"
    },

    {
      title: "CTG 35",
      address: "Avenida Ipiranga, 5300",
      overline: "Horário de Funcionamento: das 9h às 18h",
      obs: "O que doar: Alimentos não perecíveis, cestas básicas montadas, água, artigos de higiene, cobertores, colchões"
    },

    {
      title: "Shopping Iguatemi",
      address: "Avenida João Wallig, 1800",
      overline: "Horário de Funcionamento: das 11h às 20h",
      obs: "O que doar: Alimentos não perecíveis, cestas básicas montadas, água, artigos de higiene, cobertores, colchões"
    },

    {
      title: "Shopping João Pessoa",
      address: "Avenida João Pessoa, 1831",
      overline: "Horário de Funcionamento: das 10h às 21h",
      obs: "O que doar: Alimentos não perecíveis, cestas básicas montadas, água, artigos de higiene, cobertores, colchões"
    },

    {
      title: "Conselho Regional de Contabilidade do Rio Grande do Sul (CRCRS)",
      address: "Avenida Sen. Tarso Dutra, 170",
      overline: "Horário de Funcionamento: das 9h às 18h",
      content: "* O local realiza também a entrega de donativos para pessoas físicas.",

      obs: "O que doar: Alimentos não perecíveis, cestas básicas montadas, água, artigos de higiene, cobertores"
    },

    {
      title: "Palácio da Polícia",
      address: "Entrada Principal - Avenida João Pessoa, 2050",
      overline: "Horário de Funcionamento: das 8h30 às 18h",
      content: "* O local realiza também a entrega de donativos para pessoas físicas.",
      obs: "O que doar: Alimentos não perecíveis, cestas básicas montadas, água, artigos de higiene, cobertores"
    },

    {
      title: "Cidade da Polícia",
      address: "Prédio 2 - Avenida Bento Gonçalves, 8855",
      overline: "Horário de Funcionamento: das 8h30 às 18h",
      obs: "O que doar: Alimentos não perecíveis, cestas básicas montadas, água, artigos de higiene, cobertores, colchões",
      content: "* O local realiza também a entrega de donativos para pessoas físicas.",
    },

    {
      title: "Sport Club Internacional",
      address: "Escola de Samba Fidalgos e Aristocratas_ Av. Ipiranga 2485",
      overline: "Horário de Funcionamento: das 9h às 18h",
      obs: "O que doar: Alimentos não perecíveis, cestas básicas montadas, água, artigos de higiene, cobertores, colchões"
    },

    {
      title: "Centro da Comunidade Parque Madepinho (Cecopam)",
      address: "Rua Arroio Grande, 50",
      overline: "Horário de Funcionamento: das 9h às 16h",
      obs: "O que doar: Alimentos não perecíveis, cestas básicas montadas, água, artigos de higiene, cobertores"
    },
  ]
</script>
