<script>
  import '../app.css'
</script>

<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous">
  <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Noto+Sans+SC:wght@400&display=swap">
  <link rel="stylesheet" type="text/css" href="https://fonts.font.im/css?family=Barlow|Roboto+Mono|Titillium+Web">
</svelte:head>

<div class="app">
  <main>
    <slot />
  </main>
</div>

<style lang="postcss">
  :root {
    --my-special-color: #482dff;
    --color-secondary: rgb(111 114 185);
    --my-sidebar-width: 300px;

    --my-text-bodyC: #08102b;

    --my-special-primary: #0070f0;
    --my-special-secondary: #9455d3;
    --my-special-success: #41B375;
    --my-special-warning: #f5a524;
    --my-special-danger: #f31260;

    --my-widget-tac: #989b9f;

    --my-theme-trans1: all .1s ease;
    --my-theme-trans2: all .2s ease;
    --my-theme-trans3: all .3s ease;
    --my-theme-trans4: all .4s ease;
    --my-theme-trans15: all 1.5s ease;
  }

  :global(body.dark) {
    --my-text-base-color: #343435;
    --my-fill-color: #ffffff;
    --my-str-color: #e6e6e6;

    --my-bg-base-color: #fffdfc;
    --my-bg-mild: #fffdfc;
    --my-mobile-bg: #fffdfc;

    --my-special-color: #0070f0;
    --my-special-default: #d4d4d8;

    --my-shadow: 0 10px 30px -5px rgba(0, 0, 0, .3);
    --my-shallow-shadow: 0 5px 35px rgba(0, 0, 0, .1);
    --my-border-color: #e6e6e6;
    --my-box-bg: #fffdfc;
    --my-dark-border: transparent;

    --my-svg-color: #292d32;

    --my-disable-color: #7b7a7a;
    --my-scrollbar-bg: #d7d7d9;
    --my-scrollbar-bg-hover: #a5a4a6;
    --my-scrollbar-color: #fdfcff;
    --my-transB: rgba(0, 0, 0, .05);
    --my-darkT: rgba(0, 0, 0, .03);
    --my-darkBs: #fffdfc;
    --my-darkTa: var(--color-secondary);
    --my-waveB: #C6DAFC;
  }

  :global(body.light) {
    --my-text-base-color: #fffdfc;
    --my-fill-color: #2d2d30;
    --my-str-color: #404045;

    --my-bg-base-color: #1e1e1e;
    --my-bg-mild: #252526;
    --my-mobile-bg: #2d2d30;

    --my-special-color: #41B375;
    --my-special-default: #3f3f46;

    --my-shadow: 0 10px 30px -5px rgba(0, 0, 0, .5);
    --my-shallow-shadow: 0 5px 35px rgba(0, 0, 0, .07);
    --my-border-color: #404040;
    --my-box-bg: #2d2d30;
    --my-dark-border: rgba(255, 255, 255, .15);

    --my-svg-color: #d5d3d3;

    --my-disable-color: #5c5c5c;
    --my-scrollbar-bg: #171717;
    --my-scrollbar-bg-hover: #141414;
    --my-scrollbar-color: #1e1e1e;
    --my-transB: #2d2d30;
    --my-darkBs: #252526;
    --my-darkT: #252526;
    --my-darkTa: #989b9f;
    --my-waveB: #343435;
  }

  :global(body) {
    background-color: var(--my-bg-base-color);
    color: var(--my-text-base-color);
    font-family: 'Barlow', 'Noto Sans SC', sans-serif;
    overflow-x: hidden;
    font-size: 14px;
    transition: all .2s;
  }

  button, input, optgroup, select, textarea {
    color: inherit;
    font-family: inherit;
    font-size: 100%;
    font-weight: inherit;
    line-height: inherit;
    margin: 0;
    padding: 0;
    background-color: transparent;
    border: none;
    outline: none;
  }

  ::selection {
    color: #fff;
    background: var(--my-special-color);
  }

  ::-webkit-scrollbar {
    width: 4px;
    height: 3px;
    background-color: var(--my-scrollbar-color);
  }

  ::-webkit-scrollbar-thumb {
    background-color: var(--my-scrollbar-bg);
    border-radius: 4px;

    &:hover {
      background-color: var(--my-scrollbar-bg-hover);
    }
  }

  hr {
    color: var(--my-border-color);
  }

  i {
    font-style: normal;
  }

  :global(.set-svg-stroke) {
    stroke: var(--my-special-color);
  }

  :global(svg *) {
    stroke: var(--my-svg-color);
  }
</style>