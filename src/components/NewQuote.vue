<template>
  <div class="row">
    <form>
      <div
        class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-2 form-group"
      >
        <label for="">Quote</label>
        <textarea v-model="quote" rows="3" class="form-control"></textarea>
      </div>

      <div
        class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-2 form-group"
      >
        <button class="btn btn-primary" @click.prevent="createNew">
          Add Quote
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      quote: ""
    };
  },
  methods: {
    createNew: function() {
      this.$emit("quoteAdded", this.quote);
      this.quote = "";
    }
  }
};
</script>

<style scoped></style>
