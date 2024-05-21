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
      <v-row>
        <v-col>
          <ozone-maps-info />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/gl_cl/to01.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/gl_cl/to02.gif`" class="recent" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/gl_cl/to03.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/gl_cl/to04.gif`" class="recent" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/gl_cl/to05.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/gl_cl/to06.gif`" class="recent" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/gl_cl/to07.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/gl_cl/to08.gif`" class="recent" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/gl_cl/to09.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/gl_cl/to10.gif`" class="recent" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/gl_cl/to11.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/gl_cl/to12.gif`" class="recent" />
        </v-col>
      </v-row>
    </section>

    <section v-if="ozoneMapTab === 'northern'">
      <h2>{{ $t('data.products.normal-ozone-maps.northernDesc') }}</h2>
      <v-row>
        <v-col>
          <ozone-maps-info />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/nh_cl/to01.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/nh_cl/to02.gif`" class="recent" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/nh_cl/to03.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/nh_cl/to04.gif`" class="recent" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/nh_cl/to05.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/nh_cl/to06.gif`" class="recent" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/nh_cl/to07.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/nh_cl/to08.gif`" class="recent" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/nh_cl/to09.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/nh_cl/to10.gif`" class="recent" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/nh_cl/to11.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/nh_cl/to12.gif`" class="recent" />
        </v-col>
      </v-row>
    </section>

    <section v-if="ozoneMapTab === 'southern'">
      <h2>{{ $t('data.products.normal-ozone-maps.southernDesc') }}</h2>
      <v-row>
        <v-col>
          <ozone-maps-info />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/sh_cl/to01.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/sh_cl/to02.gif`" class="recent" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/sh_cl/to03.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/sh_cl/to04.gif`" class="recent" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/sh_cl/to05.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/sh_cl/to06.gif`" class="recent" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/sh_cl/to07.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/sh_cl/to08.gif`" class="recent" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/sh_cl/to09.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/sh_cl/to10.gif`" class="recent" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <img :src="`${baseOzoneURL}/sh_cl/to11.gif`" class="recent" />
        </v-col>
        <v-col>
          <img :src="`${baseOzoneURL}/sh_cl/to12.gif`" class="recent" />
        </v-col>
      </v-row>
    </section>
  </v-container>
</template>

<script>
import OzoneMapsInfo from '~/components/OzoneMapsInfo'
export default {
  components: {
    'ozone-maps-info': OzoneMapsInfo,
  },
  data() {
    return {
      baseOzoneURL: `https://woudc.org/archive/products/ozone_maps/climatology/`,
      ozoneMapTab: 'global',
      archivedRerender: 0,
      archivedMeasurement: ['to'],
      archivedDateRangeType: 'daily', // day / 10 day mean / monthly mean
      archivedIntervalType: 'day1',
      archivedHemisphere: 'nh',
      sourcedForecastHemisphere: ['gl'], // north / south / global
      sourcedForecastMeasurement: ['to'], // total ozone / std dev.
      sourcedForecastSubPaths: [],
      sourcedForecastMapPaths: {},
      sourcedForecastPathsVerified: false,
      sourcedForecastLoading: false,
      sourcedObservedRerender: 0,
      sourcedObservedHemisphere: ['gl'], // north / south / global
      sourcedObservedMeasurement: ['to'], // total ozone / std dev.
      sourcedObservedSubPaths: [],
      sourcedObservedMapPaths: {},
      sourcedObservedPathsVerified: false,
      sourcedObservedLoading: false,
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
          content: this.$t('data.products.ozone_maps.description'),
        },
        {
          hid: 'keywords',
          name: 'keywords',
          content: this.$t('data.products.ozone_maps.keywords'),
        },
      ],
    }
  },
}
</script>

<style scoped>
.recent {
  max-width: 800px;
}
</style>
