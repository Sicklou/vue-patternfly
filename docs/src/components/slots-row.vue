<template>
<tr>
  <td>{{name}}</td>
  <td v-html="description"></td>
  <td style="height: 150px">
    <ace-editor class="form-control" :value="value.toString()" @input="update" lang="html"></ace-editor>
  </td>
</tr>
</template>

<script>
export default {
  name: 'slots-row',

  props: {
    name: String,
    description: String,
    value: String,
  },

  methods: {
    update(e) {
      const value = e && e.target ? e.target.value : e;
      this.$emit('input', value);
    },
  },
};
</script>
