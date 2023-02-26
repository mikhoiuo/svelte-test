<script>
    import { createEventDispatcher } from 'svelte';
  
    const dispatch = createEventDispatcher();
    let name = '';
  
    function handleInput(event) {
      name = event.target.value;
    }
  
    function handleSubmit() {
      if (name.trim()) {
        dispatch('submit', name);
        name = '';
      }
    }
  </script>
  
  <div>
    <input type="text" value={name} on:input={handleInput} on:keydown={event => {
      if (event.key === 'Enter') {
        handleSubmit();
      }
    }}/>
  </div>
  
  <style>
    div {
      background-color: #F9F3F2;
      font-family: Karla, arial, helvetica;
      font-size: 11px;
      color: #6F6A68;
      cursor: url('http://static.tumblr.com/vmteopo/yYInjhg6e/small_black_cursor.png'), default;
    }
  
    input {
      background-color: #F9F3F2;
      border-style: hidden;
      width: 100%
    }
  </style>
  