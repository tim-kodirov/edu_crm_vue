<template>
  <div class="m-3">
    <div>
      <h2 class="text-dark">Text colors</h2>
      <div class="container-fluid">
        <div class="row">
          <div
            v-for="text in TEXTS"
            :key="text"
            :class="text"
            class="col-lg-3 col-md-4 col-sm-6 px-3 py-1"
          >
            <strong>{{ startCase(text) }}:</strong> Lorem ipsum dolor sit.
          </div>
        </div>
      </div>
    </div>

    <div class="mt-3">
      <h2 class="text-dark">Background colors</h2>
      <div class="d-flex flex-wrap mx-3">
        <div
          v-for="back in BACKGROUNDS"
          :key="back"
          :class="back"
          class="p-2"
          style="width: 12.5%"
          :title="back"
        >
          <div class="text-muted">{{ startCase(back) }}</div>
          <div class="text-white">{{ startCase(back) }}</div>
          <div class="text-black">{{ startCase(back) }}</div>
        </div>
      </div>
    </div>

    <div class="mt-3">
      <h2 class="text-dark">Button styles</h2>
      <div class="d-flex flex-wrap mx-2">
        <div v-for="button in BUTTONS" :key="button" class="d-grid p-2" style="width: 12.5%">
          <button type="button" class="btn btn-block" :class="button">
            {{ startCase(button) }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import _ from "lodash"

const BACKGROUNDS = [
  "bg-primary",
  "bg-secondary",
  "bg-info",
  "bg-success",
  "bg-warning",
  "bg-danger",
  "bg-light",
  "bg-dark"
]

const BUTTONS = [
  "btn-primary",
  "btn-secondary",
  "btn-info",
  "btn-success",
  "btn-warning",
  "btn-danger",
  "btn-light",
  "btn-dark"
]

const TEXTS = [
  "text-primary",
  "text-secondary",
  "text-info",
  "text-success",
  "text-warning",
  "text-danger",
  "text-white",
  "text-dark",
  "text-muted",
  "text-light"
]

export default {
  name: "ThemeView",

  created() {
    this.BACKGROUNDS = BACKGROUNDS
    this.BUTTONS = BUTTONS
    this.TEXTS = TEXTS
  },

  methods: {
    startCase: _.startCase
  }
}
</script>
