<script lang="ts">
  import {onMount} from 'svelte';

  export let icon: string = ''
  export let borderRadius: string = 'round'
  export let isOpenHover: boolean = true
  export let filled: boolean = false
  export let hoverFilled: boolean = false
  export let customizeClass: string = ''
  export let size: number = 20
  export let disabled: boolean = false
  export let overallSize: number = 40

  onMount(async () => await loadItem())

  $: text = ''

  async function loadItem() {
    const res = await fetch(`/icons/${icon}.svg`)
    text = await res.text()
  }
</script>

<i
  class="svg-icon w-10 h-10 flex items-center justify-center cursor-pointer select-none rounded-full"
  class:borderRadius={borderRadius}
  class:customizeClass={customizeClass}
  class:open-hover={isOpenHover}
  class:disabled={disabled}
  style:width={`${overallSize}px`}
  style:height={`${overallSize}px`}
>
  <span
    class="contents"
    class:icon--fill={filled}
    class:icon-hover--fill={hoverFilled}
    style:width={`${size}px`}
    style:height={`${size}px`}
  >
    {@html text}
    <slot/>
  </span>
</i>

<style lang="scss">
  .svg-icon {
    transition: var(--my-theme-trans2);

    .contents {
      display: block;
    }

    :global(svg) {
      width: 100%;
      height: 100%;
    }
  }

  .icon--fill {
    svg {
      stroke: var(--my-special-color);
      fill: var(--my-special-color);

      * {
        stroke: var(--my-special-color);
      }
    }
  }

  .icon-hover--fill:hover {
    svg {
      stroke: var(--my-special-color);
      fill: var(--my-special-color);

      * {
        stroke: var(--my-special-color);
      }
    }

    .set-svg-stroke {
      stroke: var(--my-svg-color);
    }
  }

  .disabled {
    cursor: no-drop;

    svg {
      opacity: .3 !important;
    }
  }

  .open-hover {
    &:hover {
      transition: var(--my-theme-trans2);
      background-color: var(--my-transB);

      svg {
        transition: var(--my-theme-trans2);

        * {
          transition: var(--my-theme-trans2);
          stroke: var(--my-special-color);
        }
      }
    }
  }
</style>