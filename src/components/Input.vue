<script>
import {
  computed, ref,
} from 'vue';

export default {
  props: {
    name: {
      type: String,
      default: null,
    },
    id: {
      type: String,
      default: null,
    },
    autocomplete: {
      type: String,
      default: null,
    },
    placeholder: {
      type: String,
      default: null,
    },
    icon: {
      type: [String, Array],
      default: null,
    },
    type: {
      type: String,
      default: 'text',
    },
    modelValue: {
      type: [String, Number, Boolean, Array, Object],
      default: '',
    },
    required: Boolean,
    borderless: Boolean,
    transparent: Boolean,
  },
  emits: ['update:modelValue', 'right-icon-click'],
  setup(props, { emit }) {
    const computedValue = computed({
      get: () => props.modelValue,
      set: (value) => {
        emit('update:modelValue', value);
      },
    });

    const computedType = computed(() => props.type);

    const inputElClass = computed(() => {
      const base = [
        'px-3 py-2 max-w-full focus:ring focus:outline-none border-gray-400 rounded w-full',
        computedType.value === 'textarea' ? 'h-24' : 'h-12',
        props.borderless ? 'border-0' : 'border',
        props.transparent ? 'bg-transparent' : 'bg-white',
      ];

      if (props.icon) {
        base.push('pl-10');
      }

      return base;
    });

    const controlIconH = computed(() => (props.type === 'textarea' ? 'h-full' : 'h-12'));

    const inputEl = ref(null);

    return {
      computedValue, computedType, inputElClass, controlIconH, inputEl,
    };
  },
};
</script>

<template>
  <div class="relative">
    <textarea
      v-if="computedType === 'textarea'"
      :id="id"
      v-model="computedValue"
      :class="inputElClass"
      :name="name"
      :placeholder="placeholder"
      :required="required"
    />
    <input
      v-else
      :id="id"
      ref="inputEl"
      v-model="computedValue"
      :name="name"
      :autocomplete="autocomplete"
      :required="required"
      :placeholder="placeholder"
      :type="computedType"
      :class="inputElClass"
    >
    <fa-icon
      v-if="icon"
      :icon="icon"
      :h="controlIconH"
    />
  </div>
</template>
