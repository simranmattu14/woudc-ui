<template>
  <v-container>
    <h1>{{ $t('data.products.josieBesos.title') }}</h1>

    <h2>{{ $t('common.abstract') }}</h2>

    <!-- prettier-ignore -->
    <i18n path="data.products.josieBesos.josieBlurb" tag="p">
      <template #wccosFullName>
        <a
          href="https://www.wccos-josie.org/en/wccos"
          hreflang="en"
          target="_blank"
        >{{ $t('data.products.josieBesos.wccosFullName') }}
          <v-icon small>mdi-open-in-new</v-icon>
        </a>
      </template>
      <template #josieFullName>
        <a
          href="https://www.wccos-josie.org/en/josie"
          hreflang="en"
          target="_blank"
        >{{ $t('data.products.josieBesos.josieFullName') }}
          <v-icon small>mdi-open-in-new</v-icon>
        </a>
      </template>
      <template #attribution>
        <span class="font-italic">
          [Smit et al., J. Geophys. Res., 2007; Smit et al., 2023, Atm. Meas.
          Tech., 2023]
        </span>
      </template>
    </i18n>

    <i18n path="data.products.josieBesos.besosBlurb" tag="p">
      <template #attribution>
        <span class="font-italic">[Deshler et al., J. Geophys. Res. 2008]</span>
      </template>
    </i18n>

    <v-card tile max-width="300">
      <v-card-title>{{ $t('common.datasets') }}</v-card-title>
      <v-list>
        <v-list-item v-for="(entry, index) in dataList" :key="index" link>
          <v-list-item-icon>
            <v-icon>mdi-file-download</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>
              <a :href="entry.href" download type="application/zip">
                {{ entry.text }}
              </a>
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-card>
  </v-container>
</template>

<script>
export default {
  head() {
    return {
      title: this.$t('data.products.josieBesos.title'),
      titleTemplate: this.$titleTemplate(
        this.$t('common.woudc'),
        this.$t('common.woudcFull')
      ),
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: this.$t('data.products.josieBesos.metaDescription', {
            josie: this.$t('data.products.josieBesos.josie'),
            besos: this.$t('data.products.josieBesos.besos'),
          }),
        },
        {
          hid: 'keywords',
          name: 'keywords',
          content: this.$t('data.products.josieBesos.keywords'),
        },
      ],
    }
  },
  computed: {
    dataList() {
      return [
        {
          text: `${this.$t('data.products.josieBesos.josie')} 1996`,
          href: `${this.$config.WOUDC_UI_WAF_URL}/Summaries/josie-besos/JOSIE 1996 Data.zip`,
        },
        {
          text: `${this.$t('data.products.josieBesos.josie')} 1998`,
          href: `${this.$config.WOUDC_UI_WAF_URL}/Summaries/josie-besos/JOSIE 1998 Data.zip`,
        },
        {
          text: `${this.$t('data.products.josieBesos.josie')} 2000`,
          href: `${this.$config.WOUDC_UI_WAF_URL}/Summaries/josie-besos/JOSIE 2000 Data.zip`,
        },
        {
          text: `${this.$t('data.products.josieBesos.josie')} 2002`,
          href: `${this.$config.WOUDC_UI_WAF_URL}/Summaries/josie-besos/JOSIE 2002 Data.zip`,
        },
        {
          text: `${this.$t('data.products.josieBesos.josie')} 2009 & 2010`,
          href: `${this.$config.WOUDC_UI_WAF_URL}/Summaries/josie-besos/JOSIE 2009 & 2010 Data.zip`,
        },
        {
          text: `${this.$t('data.products.josieBesos.josie')}-SHADOZ 2017`,
          href: `${this.$config.WOUDC_UI_WAF_URL}/Summaries/josie-besos/JOSIE-SHADOZ 2017 Data.zip`,
        },
        {
          text: `${this.$t('data.products.josieBesos.besos')} 2004`,
          href: `${this.$config.WOUDC_UI_WAF_URL}/Summaries/josie-besos/BESOS 2004 Data.zip`,
        },
      ]
    },
  },
  nuxtI18n: {
    paths: {
      en: '/data/products/josie-besos',
      fr: `/donnees/produits/eisoj-ebsso`,
    },
  },
}
</script>
