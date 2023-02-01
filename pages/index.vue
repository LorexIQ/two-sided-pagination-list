<template>
  <l-list v-model="values" v-slot="{ data }">
    <div class="el__title">
      {{ data.title }}
    </div>
    <div class="el__value">
      {{ data.value }}
    </div>
  </l-list>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      values: [{ title: 'Null', value: 0 }]
    }
  },
  mounted() {
    setTimeout(() => {
      this.values = [
        {
          title: 'Тест #1',
          value: 1
        },
        {
          title: 'Тест #2',
          value: 2
        },
        {
          title: 'Тест #3',
          value: 3
        },
        {
          title: 'Тест #4',
          value: 4
        },
        {
          title: 'Тест #5',
          value: 6
        },
        {
          title: 'Тест #7',
          value: 8
        },
        {
          title: 'Тест #9',
          value: 9
        },
        {
          title: 'Тест #10',
          value: 10
        },
        {
          title: 'Тест #11',
          value: 11
        },
        {
          title: 'Тест #12',
          value: 12
        },
        {
          title: 'Тест #13',
          value: 13
        },
        {
          title: 'Тест #14',
          value: 14
        },
        {
          title: 'Тест #15',
          value: 15
        },
        {
          title: 'Тест #16',
          value: 16
        },
        {
          title: 'Тест #17',
          value: 17
        },
        {
          title: 'Тест #18',
          value: 18
        },
        {
          title: 'Тест #19',
          value: 19
        },
        {
          title: 'Тест #20',
          value: 20
        },
        {
          title: 'Тест #21',
          value: 21
        },
        {
          title: 'Тест #22',
          value: 22
        },
      ]
    }, 5000)
  }
}
</script>

<style lang="scss">
.l-list {
  max-height: 300px;
  overflow: auto;
  &__el {
    padding: 9px 11px;
    background-color: antiquewhite;
    &:nth-child(odd) {
      background-color: beige;
    }
    & .el {
      &__title {
        font-size: 25px;
        padding-bottom: 10px;
      }
      &__value {

      }
    }
  }
}
</style>
