<template>
  <div class="paginator">
    <ul>
      <li v-for="(p, index) in pageData" :key="index">
        {{ renderFields(p) }}
      </li>
    </ul>
    <button :disabled="page == 0" @click="previousPage">Previous</button>
    <button :disabled="page >= pageCount -1" @click="nextPage">Next</button>
  </div>
</template>

<script>
export default {
  name: 'VPaginator',

  data () {
    return {
      page: 0
    }
  },

  props: {
    list: {
      type: Array,
      required: true
    },
    fields: {
      type: Array,
      required: false,
      default: undefined
    },
    rows: {
      type: Number,
      required: false,
      default: 5
    }
  },

  methods: {
    previousPage () {
      this.page--
    },

    nextPage () {
      this.page++
    },

    renderFields (obj) {
      if (this.fields !== undefined) {
        return this.renderByArray(obj)
      } else {
        return this.renderByObj(obj)
      }
    },

    renderByArray (obj) {
      let i = 0
      let renderText = ''

      this.fields.forEach(field => {
        if (i !== 0) { renderText += ' / ' }

        renderText += field.toUpperCase() + ': ' + this._.get(obj, field, 'Field Inexistente')

        i++
      })

      return renderText
    },

    renderByObj (obj) {
      let i = 0
      let renderText = ''

      this._.forIn(obj, function (value, key) {
        if (i !== 0) { renderText += ' / ' }

        renderText += key.toUpperCase() + ': ' + value

        i++
      })

      return renderText
    }
  },

  computed: {
    pageCount () {
      let l = this.list.length
      let s = this.rows

      return Math.ceil(l / s)
    },

    pageData () {
      const start = this.page * this.rows
      const end = start + this.rows

      return this.list.slice(start, end)
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
