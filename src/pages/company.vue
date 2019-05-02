<template>
  <q-page>
    <!--<img alt="Quasar logo" src="~assets/running.svg" style="width: 300px; height: 300px">-->

<div class="catalog-title">
Company Information
</div>
<div id="container" class="flex flex-center">
</div>
<q-list>
  <q-item>
    <q-item-side icon="grade" color="primary" />
    <q-item-main>
      <q-item-tile sublabel>Quality</q-item-tile>
      <q-rating v-model="company.quality" :max="5" />
       <q-item-tile sublabel>Service</q-item-tile>
      <q-rating v-model="company.service" :max="5" />
    </q-item-main>
  </q-item>
  <q-item>
    <q-item-side icon="business" color="primary" />
    <q-item-main>
      <q-item-tile sublabel>Name</q-item-tile>
      {{company.name}}
    </q-item-main>
  </q-item>
  <q-item>
     <q-item-side icon="location_on" color="primary" />
    <q-item-main inset>
      <q-item-tile sublabel>Address</q-item-tile>
      <q-item-tile label>{{company.adress1}}</q-item-tile>
      <q-item-tile label>{{company.adress2}}</q-item-tile>
      <q-item-tile label>{{company.adress3}}</q-item-tile>
    </q-item-main>
  </q-item>
  <q-item>
    <q-item-main inset>
      <q-item-tile sublabel>Registry</q-item-tile>
      <q-item-tile label>{{company.registry}}</q-item-tile>
      <q-item-tile sublabel>Company Nr</q-item-tile>
      <q-item-tile label>{{company.companyNr}}</q-item-tile>
    </q-item-main>
  </q-item>

  <q-item>
    <q-item-side icon="face" color="primary" />
    <q-item-main>
      <q-item-tile sublabel>Management</q-item-tile>
      {{company.contacts.management.name}}, {{company.contacts.management.phone}}
       <q-item-tile sublabel>Registry</q-item-tile>
     {{company.contacts.sales.name}}, {{company.contacts.sales.phone}}
    </q-item-main>
  </q-item>
</q-list>
</q-page>
 </template>

<style lang="css">
@import '/src/statics/css/main.css';
.catalog-title {
    text-align: center;
    margin-top: 10px;
    font-size: 3em;
    color: #a1a1a1;
}
.list-content {
  text-align: left;
  padding-left: 100px;
}

.list-title {
  text-align: left;
  width: 300px;
}

</style>
<script>
export default {
  name: 'Company',
  data: function () {
    return {
      company: {
        name: 'Mike Shoes',
        adress1: 'Auhofstraße 110',
        adress2: '84048 Mainburg',
        adress3: 'Deutschland',
        registry: 'A123455',
        companyNr: '1EEE1423',
        contacts: {
          management: { name: 'July Anders', phone: '00000' },
          sales: { name: 'Micky Mouse', phone: '234324' }
        },
        score: {
          quality: '5',
          service: '3'
        }
      }
    }
  }
  // components: { 'product-data': ProductData }
}
</script>
