<script>
  import {
    createEventDispatcher
  } from 'svelte';
  export let value = 'de';
  const dispatch = createEventDispatcher();
  function switchLocale(event) {
    event.preventDefault();
    dispatch('locale-changed', event.target.value);
  }
</script>
<style>
  .choose-locale {
    display: flex;
    justify-content: center;
  }
  .select {
    margin: 0 1rem 1rem;
  }
</style>
<div class="choose-locale">
  <div class="select"> <select value={value} on:change={switchLocale}>
      <option value="en">English</option>
      <option value="de">Deutsch</option>
    </select> </div>
</div>
