<script>
    import { onMount } from 'svelte';
    import { afterUpdate } from 'svelte';
    import Counter from './Counter.svelte'
    import Input from './Input.svelte';
  
    let submissions = [];
  
    function handleSubmission(event) {
      submissions = [...submissions, event.detail];
    }
  </script>
  
  <style>
    .submission {
      margin-top: 5px;
      padding: 5px;
      border: 1px solid #E6CAC2;
    }
          div {
      background-color: #F9F3F2;
      font-family: Karla, arial, helvetica;
      font-size: 11px;
      color: #6F6A68;
      cursor: url('http://static.tumblr.com/vmteopo/yYInjhg6e/small_black_cursor.png'), default;
      }
      i {
      font-family: Karla, arial;
      font-size: 11px;
      color: #EBAD99;
      text-decoration: italic;
  }
  h {
      font-family: Karla;
      font-size: 14px;
      color: #EAAA96;
      text-decoration: bold;
  }
  h2 {
      font-family: Roboto Mono;
      font-size: 14px;
      color: #EAAA96;
  }
  div.tsukinaga {
      background: #f9ede9;
      width: auto;
      height: auto;
      margin-left: auto;
      margin-right: auto;
      padding-top: 15px;
      padding-right: 25px;
      padding-bottom: 15px;
      padding-left: 25px;
      border-right: 1px solid #F9C2B0;
      border-left: 1px solid #F9C2B0;
      border-bottom: 1px solid #F9C2B0;
      box-shadow: 10px 10px #E7DCD9;
  }
  div.leo {
      background: #f9ede9;
      width: 300px;
      height: auto;
      margin-right: auto;
      margin-left: auto;
      padding-top: auto;
      padding-right: 25px;
      padding-bottom: 15px;
      padding-left: 25px;
      border-style: solid;
      border-width: 1px;
      border-color: #F9C2B0;
      margin-top: auto;
      box-shadow: 10px 10px #E7DCD9;
  }
  ::-webkit-scrollbar {
      width: 6px;
      height: auto;
      background: #FAF6F6;
  }
  ::-webkit-scrollbar-corner {
      background: transparent;
  }
  ::-webkit-scrollbar-thumb:vertical {
      background: #F9C2B0;
      width: 4px;
      border: 1px solid #F9F3F2;
  }
  ::-webkit-scrollbar-thumb:horizontal {
      background: #F9C2B0;
      height: 6px !important;
  }
  ::-webkit-scrollbar-increment {
      width: 6px;
      height: 6px;
      background-color: #F9F3F2;
  }
  </style>
  
  <div class="leo">
    <i>  <center><h2>
      silly stats
    </h2>
          <h>up arrow +1, down arrow -1</h></center></i>
  
  </div>
  
  <div class="tsukinaga">
    <Input on:submit={handleSubmission}></Input>
    {#each submissions as submission}
      <div class="submission">{submission}<Counter></Counter></div>
    {/each}
  </div>
  