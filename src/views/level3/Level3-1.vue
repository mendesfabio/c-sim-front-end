<template>
  <div class="layout-vertical">
    <form-navigation @help="$refs.modal.show()" @restart="() => {}" />
    <p text-xl>What percent of the contributions will be allocated to the Funding Pool?</p>
    <p style="opacity: 0.6;">The balance will be the Reserve that backs the RxC tokens.</p>
    <div class="layout-form">
      <form-progress />
      <input type="range" />
    </div>

    <button @click="$router.push('/level/3/2')">next</button>

    <modal ref="modal" bg="" overlay="dark">
      <div class="layout-modal">
        <h2 class="level-title">Funding Pools</h2>
        <p class="level-text mt-1">
          The RxC Reserve backs the RxC token, guaranteeing liquidity for all tokens issued so that
          they will always have monetary value. The Funding Pool will be used to fund RadicalxChange
          initiatives.
        </p>
        <grid class="x-subsection" gtc="1fr 1fr" gap="3">
          <div>
            <p class="level-subtitle">Hatch Tribute</p>
            <p class="mt-1">
              The total funds raised are split between the 2 pools, with the amount going to the
              Funding Pool being called <strong>the Hatch Tribute</strong>
            </p>
          </div>
          <div>
            <p class="level-subtitle">RxC token</p>
            <p class="mt-1">
              The RxC Reserve backs the RxC token, guaranteeing liquidity for all tokens issued so
              that they will always have monetary value.
            </p>
          </div>
        </grid>
        <p class="level-text">
          If you put too much funds in the Funding Pool, the token may have trouble maintaining
          value, and if you put too much in the RxC Reserve, the Commons won’t be able to support
          very many projects.
        </p>
        <button class="mt-2" @click="$refs.modal.hide()">OK</button>
      </div>
    </modal>
  </div>
</template>

<script>
import FormNavigation from '../../components/common/FormNavigation.vue'
import FormProgress from '../../components/common/FormProgress.vue'

export default {
  name: 'level-3-1',
  components: {
    FormNavigation,
    FormProgress,
  },
  props: {},
  methods: {},
}
</script>

<style scoped lang="scss">
.x-subsection {
  max-width: 800px;
}
</style>