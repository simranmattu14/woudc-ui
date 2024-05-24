<template>
  <v-container>
    <h1>{{ $t('data.products.normal-ozone-maps.title') }}</h1>
    <v-btn-toggle v-model="ozoneMapTab" mandatory>
      <v-btn value="global">
        {{ $t('data.products.normal-ozone-maps.global') }}
      </v-btn>
      <v-btn value="northern">
        {{ $t('data.products.normal-ozone-maps.northern') }}
      </v-btn>
      <v-btn value="southern">
        {{ $t('data.products.normal-ozone-maps.southern') }}
      </v-btn>
    </v-btn-toggle>

    <section v-if="ozoneMapTab === 'global'">
      <h2>{{ $t('data.products.normal-ozone-maps.globalDesc') }}</h2>
      <graph-carousel
        :key="Object.keys(normalOzoneMapsGlobal)"
        :graphs="normalOzoneMapsGlobal"
      ></graph-carousel>
    </section>

    <section v-if="ozoneMapTab === 'northern'">
      <h2>{{ $t('data.products.normal-ozone-maps.northernDesc') }}</h2>
      <graph-carousel
        :key="Object.keys(normalOzoneMapsNorthern)"
        :graphs="normalOzoneMapsNorthern"
      ></graph-carousel>
    </section>

    <section v-if="ozoneMapTab === 'southern'">
      <h2>{{ $t('data.products.normal-ozone-maps.southernDesc') }}</h2>
      <graph-carousel
        :key="Object.keys(normalOzoneMapsSouthern)"
        :graphs="normalOzoneMapsSouthern"
      ></graph-carousel>
    </section>
  </v-container>
</template>

<script>
import GraphCarousel from '~/components/GraphCarousel'
export default {
  components: {
    'graph-carousel': GraphCarousel,
  },
  data() {
    return {
      baseOzoneClimatologyURL: `${this.$config.WOUDC_UI_WAF_URL}/products/ozone_maps/climatology/`,
      ozoneMapTab: 'global',
      ozoneMapTypes: ['global', 'northern', 'southern'],
    }
  },
  head() {
    return {
      title: this.$t('data.products.normal-ozone-maps.title'),
      titleTemplate: this.$titleTemplate(
        this.$t('common.woudc'),
        this.$t('common.woudcFull')
      ),
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: this.$t('data.products.normal-ozone-maps.description'),
        },
        {
          hid: 'keywords',
          name: 'keywords',
          content: this.$t('data.products.normal-ozone-maps.keywords'),
        },
      ],
    }
  },
  computed: {
    normalOzoneMapsGlobal() {
      const { baseOzoneClimatologyURL } = this
      const months = [
        'jan',
        'feb',
        'mar',
        'apr',
        'may',
        'jun',
        'jul',
        'aug',
        'sept',
        'oct',
        'nov',
        'dec',
      ]
      const ozoneMaps = months.map((month, index) => {
        const paddedNumber = (index + 1).toString().padStart(2, '0')
        const caption = this.$t(
          `data.products.normal-ozone-maps.captions.globe.${month}`
        )
        const url = `${baseOzoneClimatologyURL}/gl_cl/to${paddedNumber}.gif`
        return { caption, url }
      })

      return ozoneMaps
    },
    normalOzoneMapsNorthern() {
      const { baseOzoneClimatologyURL } = this
      const months = [
        'jan',
        'feb',
        'mar',
        'apr',
        'may',
        'jun',
        'jul',
        'aug',
        'sept',
        'oct',
        'nov',
        'dec',
      ]
      const ozoneMaps = months.map((month, index) => {
        const paddedNumber = (index + 1).toString().padStart(2, '0')
        const caption = this.$t(
          `data.products.normal-ozone-maps.captions.northern.${month}`
        )
        const url = `${baseOzoneClimatologyURL}/nh_cl/to${paddedNumber}.gif`
        return { caption, url }
      })

      return ozoneMaps
    },

    normalOzoneMapsSouthern() {
      const { baseOzoneClimatologyURL } = this
      const months = [
        'jan',
        'feb',
        'mar',
        'apr',
        'may',
        'jun',
        'jul',
        'aug',
        'sept',
        'oct',
        'nov',
        'dec',
      ]
      const ozoneMaps = months.map((month, index) => {
        const paddedNumber = (index + 1).toString().padStart(2, '0')
        const caption = this.$t(
          `data.products.normal-ozone-maps.captions.southern.${month}`
        )
        const url = `${baseOzoneClimatologyURL}/sh_cl/to${paddedNumber}.gif`
        return { caption, url }
      })

      return ozoneMaps
    },
  },
  created() {
    const sanitizedOzoneType = encodeURIComponent(this.$route.query.type)
    if (this.ozoneMapTypes.includes(sanitizedOzoneType)) {
      this.ozoneMapTab = sanitizedOzoneType
    }
  },
}
</script>

<style scoped>
.recent {
  max-width: 800px;
}
</style>
