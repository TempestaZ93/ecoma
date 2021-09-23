<script>
    import { Router, Route } from "svelte-routing";
    import Header from './components/layout/Header.svelte';
    import Footer from './components/layout/Footer.svelte';
    import About from './components/pages/About.svelte';
    import Contact from './components/pages/Contact.svelte';
    import { _, dir, setupI18n, locale, isLocaleLoaded } from './services/i18n';
    import FrameworkGrid from './components/frameworks/FrameworkGrid.svelte';
    import LocaleSwitcher from './components/controllers/LocaleSwitcher.svelte';

    $: if (!$isLocaleLoaded) {
        setupI18n({ withLocale: 'en' });
    }

    $: { document.dir = $dir; }
</script>

<!-- Material Icons -->
<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/icon?family=Material+Icons"
/>
<!-- Roboto -->
<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/css?family=Roboto:300,400,500,600,700"
/>
<!-- Roboto Mono -->
<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/css?family=Roboto+Mono"
/>

<style>
    main { padding: 0 1rem; }
</style>

{#if $isLocaleLoaded}
<Router>
    <Header />
    <div class="container">
    <Route path="/contact" component={Contact} />
    <Route path="/about" component={About} />
    </div>
</Router>
    <LocaleSwitcher
        value={$locale}
        on:locale-changed={e => setupI18n({ withLocale: e.detail }) }
    />

    <main role="main">
        <FrameworkGrid />
    </main>

    <Footer />
{:else}
    <p>Loading...</p>
{/if}
