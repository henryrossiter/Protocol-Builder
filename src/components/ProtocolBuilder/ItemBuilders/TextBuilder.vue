<template>
  <v-form
    ref="form"
    v-model="valid"
  >
    <v-text-field
      v-model="maxLength"
      label="Maximum response length"
      type="number"
      :disabled="!isItemEditable"
      :rules="maxLengthRules"
      @change="update"
    />
    <v-checkbox
      v-model="requiredValue"
      label="Response required"
      :disabled="!isItemEditable"
      @change="update"
    />
  </v-form>
</template>

<script>
export default {
  props: {
    initialItemData: {
      type: Object,
      required: true
    },
    isItemEditable: {
      type: Boolean,
      default: true,
    },
  },
  data: function () {
    return {
      maxLength: this.initialItemData.maxLength || 50,
      requiredValue: this.initialItemData.requiredValue || false,
      type: this.initialItemData.type || 'xsd:string',
      valid: true,
      textRules: [
        v => !!v || 'Radio options cannot be empty',
      ],
      maxLengthRules: [
        v => (v > 0 && v % 1 ===0) || 'Max response length must be a positive integer',
      ],
    };
  },
  methods: {
    update () {
      const responseOptions = {
        'maxLength': this.maxLength,
        'requiredValue': this.requiredValue,
        'type': this.type,
      };
      this.$emit('updateOptions', responseOptions);
    },
  }
}
</script>