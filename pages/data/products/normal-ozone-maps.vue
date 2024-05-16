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
    }
  },
  computed: {
    normalOzoneMapsGlobal() {
      const { baseOzoneClimatologyURL } = this
      return [
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.JanDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.global'),
          url: `${baseOzoneClimatologyURL}/gl_cl/to01.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.FebDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.global'),
          url: `${baseOzoneClimatologyURL}/gl_cl/to02.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.MarDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.global'),
          url: `${baseOzoneClimatologyURL}/gl_cl/to03.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.AprilDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.global'),
          url: `${baseOzoneClimatologyURL}/gl_cl/to04.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.MayDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.global'),
          url: `${baseOzoneClimatologyURL}/gl_cl/to05.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.JuneDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.global'),
          url: `${baseOzoneClimatologyURL}/gl_cl/to06.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.JulyDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.global'),
          url: `${baseOzoneClimatologyURL}/gl_cl/to07.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.AugustDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.global'),
          url: `${baseOzoneClimatologyURL}/gl_cl/to08.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.SeptDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.global'),
          url: `${baseOzoneClimatologyURL}/gl_cl/to09.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.OctDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.global'),
          url: `${baseOzoneClimatologyURL}/gl_cl/to10.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.NovDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.global'),
          url: `${baseOzoneClimatologyURL}/gl_cl/to11.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.DecDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.global'),
          url: `${baseOzoneClimatologyURL}/gl_cl/to12.gif`,
        },
      ]
    },
    normalOzoneMapsNorthern() {
      const { baseOzoneClimatologyURL } = this
      return [
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.JanDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.northern'),
          url: `${baseOzoneClimatologyURL}/nh_cl/to01.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.FebDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.northern'),
          url: `${baseOzoneClimatologyURL}/nh_cl/to02.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.MarDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.northern'),
          url: `${baseOzoneClimatologyURL}/nh_cl/to03.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.AprilDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.northern'),
          url: `${baseOzoneClimatologyURL}/nh_cl/to04.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.MayDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.northern'),
          url: `${baseOzoneClimatologyURL}/nh_cl/to05.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.JuneDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.northern'),
          url: `${baseOzoneClimatologyURL}/nh_cl/to06.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.JulyDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.northern'),
          url: `${baseOzoneClimatologyURL}/nh_cl/to07.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.AugustDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.northern'),
          url: `${baseOzoneClimatologyURL}/nh_cl/to08.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.SeptDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.northern'),
          url: `${baseOzoneClimatologyURL}/nh_cl/to09.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.OctDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.northern'),
          url: `${baseOzoneClimatologyURL}/nh_cl/to10.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.NovDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.northern'),
          url: `${baseOzoneClimatologyURL}/nh_cl/to11.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.DecDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.northern'),
          url: `${baseOzoneClimatologyURL}/nh_cl/to12.gif`,
        },
      ]
    },
    normalOzoneMapsSouthern() {
      const { baseOzoneClimatologyURL } = this
      return [
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.JanDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.southern'),
          url: `${baseOzoneClimatologyURL}/sh_cl/to01.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.FebDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.southern'),
          url: `${baseOzoneClimatologyURL}/sh_cl/to02.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.MarDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.southern'),
          url: `${baseOzoneClimatologyURL}/sh_cl/to03.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.AprilDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.southern'),
          url: `${baseOzoneClimatologyURL}/sh_cl/to04.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.MayDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.southern'),
          url: `${baseOzoneClimatologyURL}/sh_cl/to05.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.JuneDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.southern'),
          url: `${baseOzoneClimatologyURL}/sh_cl/to06.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.JulyDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.southern'),
          url: `${baseOzoneClimatologyURL}/sh_cl/to07.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.AugustDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.southern'),
          url: `${baseOzoneClimatologyURL}/sh_cl/to08.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.SeptDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.southern'),
          url: `${baseOzoneClimatologyURL}/sh_cl/to09.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.OctDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.southern'),
          url: `${baseOzoneClimatologyURL}/sh_cl/to10.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.NovDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.southern'),
          url: `${baseOzoneClimatologyURL}/sh_cl/to11.gif`,
        },
        {
          caption:
            this.$t('data.products.normal-ozone-maps.Images.DecDes') +
            ' / ' +
            this.$t('data.products.normal-ozone-maps.southern'),
          url: `${baseOzoneClimatologyURL}/sh_cl/to12.gif`,
        },
      ]
    },
  },
}
</script>

<style scoped>
.recent {
  max-width: 800px;
}
</style>
