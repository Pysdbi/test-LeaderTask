<script>
import PopMenu from '@/components/modals/PopMenu.vue'
import PopMenuItem from '@/components/modals/PopMenuItem.vue'
export default {
  components: {
    PopMenu,
    PopMenuItem
  },
  props: {
    canDelete: {
      type: Boolean,
      default: true
    }
  },
  emits: ['onQuoteMessage']
}

</script>
<template>
  <PopMenu>
    <slot />
    <template #menu>
      <PopMenuItem
        icon="answer"
        @click="$emit('onQuoteMessage')"
      >
        Ответить
      </PopMenuItem>
      <PopMenuItem
        v-if="canDelete"
        icon="delete"
        @click="$emit('onDeleteMessage')"
      >
        Удалить
      </PopMenuItem>
    </template>
  </PopMenu>
</template>
