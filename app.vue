<template>
  <div>
    <div>test</div>
  </div>
</template>
<script setup type="module">
import { createMachine, assign } from 'xstate'

const increment = context => {
  console.log('content+', content)
  return context.count + 1
}
const decrement = context => {
  console.log('content-', content)
  return context.count - 1
}

const counterMachine = createMachine({
  id: 'counter',
  initial: 'active',
  context: {
    count: 0,
  },
  states: {
    active: {
      on: {
        INC: { actions: assign({ count: increment }) },
        DEC: { actions: assign({ count: decrement }) },
      },
    },
  },
})
</script>
