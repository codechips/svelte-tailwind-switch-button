<script>
  import Switch from './Switch.svelte';

  let uno = false;
  let dos = true;
  let tres = false;
  let quatro = true;

  $: values = { uno, dos, tres, quatro };
</script>

<div class="flex items-center justify-center flex-grow h-screen">
  <div class="max-w-xl">
    <h1 class="text-2xl font-semibold text-gray-700">
      Accessible switch toggle with svelte.js + tailwind.css
    </h1>
    <p class="mt-5 text-xl text-gray-600">
      Web accessibility is very important. These toggle switches are
      <strong>accessible</strong>
      . You can try tabbing to them from the text input field. Let's make the
      web better together.
    </p>
    <div class="mt-5">
      <input
        type="text"
        class="w-full p-2 border border-gray-200"
        placeholder="Tab from here to go to the next switch button"
        id="text"
      />
    </div>
    <div class="flex justify-between mt-5">
      <Switch bind:checked="{uno}" id="uno" text="uno" />
      <Switch bind:checked="{dos}" id="dos" text="dos" />
      <Switch bind:checked="{tres}" id="tres" text="tres" />
      <Switch
        bind:checked="{quatro}"
        disabled="{true}"
        id="quatro"
        text="quatro"
      />
    </div>
    <div class="mt-5">
      <pre class="p-4 font-mono bg-teal-100">{JSON.stringify(values)}</pre>
    </div>
  </div>
</div>
