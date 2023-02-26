<script>
    import { onMount } from 'svelte';
    import { createEventDispatcher } from 'svelte';
  
    let count = 0;
    const dispatch = createEventDispatcher();
  
    function increment() {
      count += 1;
      dispatch('count', count);
    }
  
    function decrement() {
      count -= 1;
      dispatch('count', count);
    }
  
    onMount(() => {
      window.addEventListener('keydown', (event) => {
        if (event.key === 'ArrowUp' && hovering) {
          increment();
        } else if (event.key === 'ArrowDown' && hovering) {
          decrement();
        }
      });
    });
  
    let hovering = false;
  
    function handleMouseEnter() {
      hovering = true;
    }
  
    function handleMouseLeave() {
      hovering = false;
    }
  </script>
  
  <div class="counter" on:mouseenter={handleMouseEnter} on:mouseleave={handleMouseLeave}>
    <h>{count}</h>
  </div>
  
  <style>
    .counter {
      cursor: pointer;
    }
  </style>