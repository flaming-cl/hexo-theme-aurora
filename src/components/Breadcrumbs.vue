

<script lang="ts">
import { defineComponent } from 'vue'
import { useI18n } from 'vue-i18n'

export default defineComponent({
  name: 'Breadcrumb',
  props: {
    current: String
  },
  setup() {
    const { t } = useI18n()
    return { t }
  }
})
</script>

<style lang="scss" scoped>
.breadcrumbs {
  position: relative;
  z-index: 20;
  li {
    position: relative;
    z-index: 20;
    &:after {
      content: '>';
      position: absolute;
      top: 0.05rem;
      right: -0.95rem;
      opacity: 0.65;
    }
    &:last-of-type {
      &:after {
        content: '';
      }
    }
  }
}
</style>
