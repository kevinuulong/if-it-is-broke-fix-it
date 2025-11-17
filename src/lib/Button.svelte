<script>
    let { children, type = "primary", icon, ...rest } = $props();

    const isIconButton = icon && !children;
</script>

{#if rest.href !== undefined}
    <a class={[type, { icon, "icon-button": isIconButton }]} {...rest}>
        {@render children?.()}
        {#if icon}
            {@html icon}
        {/if}
    </a>
{:else}
    <button class={[type, { icon, "icon-button": isIconButton }]} {...rest}>
        {@render children?.()}
        {#if icon}
            {@html icon}
        {/if}
    </button>
{/if}

<style>
    button,
    a {
        display: inline-flex;
        padding: 7px 10px;
        align-items: center;
        gap: 10px;
        border-radius: 3px;

        height: 36px;

        font-family: "Noto Sans";
        font-size: 16px;
        font-style: normal;
        font-weight: 400;
        line-height: normal;

        border: none;
        box-sizing: border-box;
    }

    .icon-button {
        width: 36px;
        height: 36px;
        padding: 0;

        justify-content: center;
    }

    .primary {
        color: var(--Primary-White, #fff);
        background: var(--Primary-UC-Red, #e00122);

        &:hover,
        &:focus {
            background-color: color-mix(
                in srgb,
                var(--Primary-UC-Black) 10%,
                var(--Primary-UC-Red)
            );
        }
    }

    .secondary {
        color: var(--Primary-UC-Black);
        background: var(--Secondary-Grey, #f3f3f3);

        &:hover,
        &:focus {
            background-color: color-mix(
                in srgb,
                var(--Primary-UC-Black) 10%,
                var(--Secondary-Grey)
            );
        }
    }

    .tertiary {
        color: var(--Primary-UC-Black);
        background: transparent;

        &:hover,
        &:focus {
            background-color: color-mix(
                in srgb,
                var(--Primary-UC-Black) 10%,
                transparent
            );
        }
    }

    .link {
        color: var(--Primary-UC-Red);
        background: transparent;

        &:hover,
        &:focus {
            background-color: color-mix(
                in srgb,
                var(--Primary-UC-Black) 10%,
                transparent
            );
        }
    }
</style>
