<script lang="ts" setup>
import {computed} from 'vue'
import {useData} from 'vitepress'
import VPContentDocFooter from './VPContentDocFooter.vue'
import {VTLink, VTIconEdit} from '../../core'
import {useConfig} from '../composables/config'

import _ from 'lodash'

const {page, frontmatter} = useData()
const {config} = useConfig()

const hashMatch = /#(\w+)$/

const pageClass = computed(() => {
  const {relativePath} = page.value
  return relativePath.slice(0, relativePath.indexOf('/'))
})

const heroImage = computed(() => {
   //return a background image style when the frontmatter image is set
    if (frontmatter.value.image) {
      // return `background: url(${frontmatter.value.image})`
    }
})

</script>

<template>
  <div class="container blogpost">
    <div class="blog-hero" v-if="frontmatter.hero !== false">
      <div>
        <img :src="frontmatter.image" alt=""/>
      </div>
    </div>
    <div class="content">
      <slot name="content-top"/>
      <main>
        <Content class="vt-doc" :class="pageClass"/>
      </main>
      <slot name="content-bottom"/>
      <VPContentDocFooter v-if="frontmatter.footer !== false"/>
    </div>
  </div>
</template>
