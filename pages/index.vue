<template>
  <div class="MainPage">
    <div class="Header mb-3">
      <page-header :icon="headerItem.icon">
        {{ headerItem.title }}
      </page-header>
      <div class="UpdatedAt">
        <span>{{ $t('最終更新') }} </span>
        <time :datetime="updatedAt">{{ Data.lastUpdate }}</time>
      </div>
      <div v-if="!['ja', 'ja-basic'].includes($i18n.locale)" class="Annotation">
        <span>{{ $t('注釈') }} </span>
      </div>
    </div>
    <whats-new class="mb-4" :items="newsItems" />
    <v-row class="DataBlock">
      <confirmed-cases-details-card />
      <tested-cases-details-card />
      <confirmed-cases-attributes-card />
      <confirmed-cases-number-card />
    </v-row>
      <whats-new2 class="mb-4" :items="eventItems" />
      <whats-new3 class="mb-4" :items="sportsItems"/>
      
      <div class="DataCard col-md-6 col-12">
        <div class="infogram-embed" data-id="ba9944f3-2ecf-4f77-8f90-8203cd3663af" data-type="interactive" data-title="ワクチン接種数（県別）"></div><script>!function(e,i,n,s){var t="InfogramEmbeds",d=e.getElementsByTagName("script")[0];if(window[t]&&window[t].initialized)window[t].process&&window[t].process();else if(!e.getElementById(n)){var o=e.createElement("script");o.async=1,o.id=n,o.src="https://e.infogram.com/js/dist/embed-loader-min.js",d.parentNode.insertBefore(o,d)}}(document,0,"infogram-async");</script><div style="padding:8px 0;font-family:Arial!important;font-size:13px!important;line-height:15px!important;text-align:center;border-top:1px solid #dadada;margin:0 30px"><a href="https://infogram.com/ba9944f3-2ecf-4f77-8f90-8203cd3663af" style="color:#989898!important;text-decoration:none!important;" target="_blank">ワクチン接種数（県別）</a><br><a href="https://infogram.com" style="color:#989898!important;text-decoration:none!important;" target="_blank" rel="nofollow">Infogram</a></div>
      </div>
      
      <div class="DataCard col-md-6 col-12">
          <iframe src="https://e.infogram.com/ba9944f3-2ecf-4f77-8f90-8203cd3663af?src=embed" title="ワクチン接種数（県別）" width="100%" height="550" scrolling="no" frameborder="0" style="border:none;" allowfullscreen="allowfullscreen"></iframe><div style="padding:8px 0;font-family:Arial!important;font-size:13px!important;line-height:15px!important;text-align:center;border-top:1px solid #dadada;margin:0 30px;width: 640px"><a href="https://infogram.com/ba9944f3-2ecf-4f77-8f90-8203cd3663af" style="color:#989898!important;text-decoration:none!important;" target="_blank">ワクチン接種数（県別）</a><br><a href="https://infogram.com" style="color:#989898!important;text-decoration:none!important;" target="_blank" rel="nofollow">Infogram</a></div>
      </div>
        

      <div class="WorryInfoBlock mb-4">
        <h3 class="WhatsNew-heading"><i aria-hidden="true" class="v-icon notranslate WhatsNew-heading-icon mdi mdi-information theme--light" style="font-size: 24px;"></i>
        新型コロナウイルスの感染が心配なときは
        </h3>
        <img class="worryimg" src="/worryinfo.png" alt="新型コロナウイルスの感染が心配なときは" />
        <h4 class="tabletitle">帰国者・接触者相談センター相談窓口</h4>
        <table>
          <thead>
              <tr>
                  <th class="col1"  scope="col">保健所名</th>
                  <th class="col2" scope="col">電話番号</th>
                  <th class="col3" scope="col">管轄市町村</th>
              </tr>
          </thead>
          <tbody>
            <tr>
                <th>八戸市保健所</th>
                <td data-label="電話番号" class="tel"><a href="tel:0178432291">0178-43-2291</a></td>
                <td data-label="管轄市町村" class="txt">八戸市</td>
            </tr>
            <tr>
                <th>三戸地方保健所</th>
                <td data-label="電話番号" class="tel"><a href="tel:0178275111">0178-27-5111</a></td>
                <td data-label="管轄市町村"class="txt">三戸町、五戸町、田子町、南部町、階上町、新郷村、おいらせ町</td>
            </tr>
            <tr>
                <th>上十三保健所</th>
                <td data-label="電話番号" class="tel"><a href="tel:0176234261">0176-23-4261</a></td>
                <td data-label="管轄市町村"class="txt">十和田市、三沢市、野辺地町、七戸町、六戸町、横浜町、東北町、六ケ所村</td>
            </tr>
            <tr>
                <th>むつ保健所</th>
                <td data-label="電話番号" class="tel"><a href="tel:0175311388">0175-31-1388</a></td>
                <td data-label="管轄市町村"class="txt">むつ市、大間町、東通村、風間浦村、佐井村</td>
            </tr>
            <tr>
                <th>岩手県帰国者・接触者相談センター</th>
                <td data-label="電話番号" class="tel"><a href="tel:0196513175">019-651-3175</a></td>
                <td data-label="管轄市町村"class="txt">岩手県全域</td>
            </tr>
          </tbody>
        </table>   

      </div>

  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { MetaInfo } from 'vue-meta'
import PageHeader from '@/components/PageHeader.vue'
import WhatsNew from '@/components/WhatsNew.vue'
import WhatsNew2 from '@/components/WhatsNew2.vue'
import WhatsNew3 from '@/components/Sports.vue'
import Data from '@/data/data.json'
import News from '@/data/news.json'
import Event from '@/data/event.json'
import Sports from '@/data/sports.json'
import ConfirmedCasesDetailsCard from '@/components/cards/ConfirmedCasesDetailsCard.vue'
import TestedCasesDetailsCard from '@/components/cards/TestedCasesDetailsCard.vue'
import ConfirmedCasesNumberCard from '@/components/cards/ConfirmedCasesNumberCard.vue'
import ConfirmedCasesAttributesCard from '@/components/cards/ConfirmedCasesAttributesCard.vue'
import TestedNumberCard from '@/components/cards/TestedNumberCard.vue'
import InspectionPersonsNumberCard from '@/components/cards/InspectionPersonsNumberCard.vue'
import TelephoneAdvisoryReportsNumberCard from '@/components/cards/TelephoneAdvisoryReportsNumberCard.vue'
import ConsultationDeskReportsNumberCard from '@/components/cards/ConsultationDeskReportsNumberCard.vue'
import MetroCard from '@/components/cards/MetroCard.vue'
import AgencyCard from '@/components/cards/AgencyCard.vue'
import { convertDatetimeToISO8601Format } from '@/utils/formatDate'
import ShinjukuVisitorsCard from '@/components/cards/ShinjukuVisitorsCard.vue'
import ChiyodaVisitorsCard from '@/components/cards/ChiyodaVisitorsCard.vue'

export default Vue.extend({
  components: {
    PageHeader,
    WhatsNew,
    WhatsNew2,
    WhatsNew3,
    ConfirmedCasesDetailsCard,
    TestedCasesDetailsCard,
    ConfirmedCasesNumberCard,
    ConfirmedCasesAttributesCard,
    TestedNumberCard,
    InspectionPersonsNumberCard,
    TelephoneAdvisoryReportsNumberCard,
    ConsultationDeskReportsNumberCard,
    MetroCard,
    AgencyCard,
    ShinjukuVisitorsCard,
    ChiyodaVisitorsCard
  },
  data() {
    const data = {
      Data,
      headerItem: {
        icon: 'mdi-chart-timeline-variant',
        title: this.$t('青森県内の最新感染動向')
      },
      newsItems: News.newsItems,
      eventItems: Event.eventItems,
      sportsItems: Sports.sportsItems
    }
    return data
  },
  computed: {
    updatedAt() {
      return convertDatetimeToISO8601Format(this.$data.Data.lastUpdate)
    }
  },
  head(): MetaInfo {
    return {
      title: this.$t('青森県内の最新感染動向') as string
    }
  }
})
</script>

<style lang="scss" scoped>
.MainPage {
  .Header {
    display: flex;
    flex-wrap: wrap;
    align-items: flex-end;

    @include lessThan($small) {
      flex-direction: column;
      align-items: baseline;
    }
  }

  .UpdatedAt {
    @include font-size(14);

    color: $gray-3;
    margin-bottom: 0.2rem;
  }

  .Annotation {
    @include font-size(12);

    color: $gray-3;
    @include largerThan($small) {
      margin: 0 0 0 auto;
    }
  }
  .DataBlock {
    margin: 20px -8px;

    .DataCard {
      @include largerThan($medium) {
        padding: 10px;
      }

      @include lessThan($small) {
        padding: 4px 8px;
      }
    }
  }
  .WorryInfoBlock {
    margin: 20px 0;
    background-color: #fff;
    box-shadow: 0 0 2px rgba(112, 15, 15, 0.15);
    border: 0.5px solid #d9d9d9 !important;
    border-radius: 4px;
    padding: 10px;

    .worryimg {
      display: block;
      width: 85%;
      margin: 20px auto 40px auto;
      @include lessThan($small) {
        width: 100%;
      }
    }
    h4 {
      font-size: 1rem;
      text-align: center;
    }
    table {
      border-collapse: collapse;
      margin: 0 auto;
      padding: 0;
      width: 95%;
      table-layout: fixed;
    }

    table tr {
      background-color: #fff;
      border: 1px solid #bbb;
      padding: .35em;
    }
    table th,
    table td {
      padding: 1em 10px 1em 1em;
      border-right: 1px solid #bbb;
    }
    table th {
      font-size: .85em;
    }
    table thead tr{
      background-color: #eee;
    }
    table .col1,table .col2 {
      width: 20%;
    }
    .tel{
      text-align: left;
      font-size: .85em;
    }
    .tel a{
      text-decoration: none;
      font-weight: bold;
    }
    .txt{
      text-align: left;
    }
    @media screen and (max-width: 600px) {
      table {
        border: 0;
        width:100%
      }
      table th{
        background-color: #eee;
        display: block;
        border-right: none;
      }
      table thead {
        border: none;
        clip: rect(0 0 0 0);
        height: 1px;
        margin: -1px;
        overflow: hidden;
        padding: 0;
        position: absolute;
        width: 1px;
      }
      
      table tr {
        display: block;
        margin-bottom: .625em;
      }
      
      table td {
        border-bottom: 1px solid #bbb;
        display: block;
        font-size: .8em;
        text-align: right;
        position: relative;
        padding: .625em .625em .625em 7.5em;
        border-right: none;
      }
      
      table td::before {
        content: attr(data-label);
        font-weight: bold;
        position: absolute;
        left: 10px;
      }
      
      table td:last-child {
        border-bottom: 0;
      }
    }

  }
  
}
</style>
