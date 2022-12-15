<template>
  <div class="info border-l-4 p-4 mb-4 mt-4" :class="`info-${type}`">
    <div class="flex items-start">
      <div class="flex-shrink-0">
        <component :is="icon" class="info-icon mt-px w-6 h-6" />
      </div>
      <div class="flex-grow ml-2 overflow-auto info-content">
        <slot />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    type: {
      type: String,
      default: 'info',
      validator (value) {
        return ['darkorange, lightorange, validation'].includes(value)
      }
    }
  },
  computed: {
    icon () {
      return ({
        // darkorange: 'IconInformationNumber',
        // lightorange: 'IconInformationNumber',
      })[this.type]
    }
  }
}
</script>

<style>

/* DarkOrange */

.info-darkorange {
  background: #e0a486;
  border-left-color: #e15a16;
}
.info-darkorange code {
  @apply bg-blue-200 shadow-none border-0 text-current;
}
.info-darkorange .info-icon {
  color: black;
}
.info-darkorange .info-content {
  @apply text-black;
}
.dark-mode .info-darkorange {
  background: #e15a16;
  border-left-color: #e0a486;
}
.dark-mode .info-darkorange code {
  @apply bg-blue-800;
}

.dark-mode .info-darkorange .info-icon{
  color: black;
}

.dark-mode .info-darkorange .info-content{
  color: black;
}

/* DarkOrange */

.info-lightorange {
  background: #f4d992;
  border-left-color: #F7B50A;
}
.info-lightorange code {
  @apply bg-blue-200 shadow-none border-0 text-current;
}
.info-lightorange .info-icon {
  color: black;
}
.info-lightorange .info-content {
  @apply text-black;
}
.dark-mode .info-lightorange {
  background: #F7B50A;
  border-left-color: #f4d992;
}
.dark-mode .info-lightorange code {
  @apply bg-blue-800;
}

.dark-mode .info-lightorange .info-icon{
  color: black;
}

.dark-mode .info-lightorange .info-content{
  color: black;
}

/* Validation */

.info-validation {
    background: #bae0b1;
  border-left-color: #46c929ff;
}
.info-validation  code {
  @apply bg-green-200 shadow-none border-0 text-current;
}
.info-validation .info-icon {
  @apply text-green-400;
}
.info-validation .info-content {
  @apply text-black;
}
.dark-mode .info-validation {
  border-left-color: #bae0b1;
  background: #46c929ff;
}
.dark-mode .info-validation code {
  @apply bg-green-800;
}
.dark-mode .alinfoert-validation .alert-content {
  @apply text-green-300;
}



</style>
