<script>
    export let n = 0;
    export let color = '#000';

    const width = 15;
    const height = 40;
</script>

<div class="lines-wrapper">
    <div class="lines">
        {#each {length: n} as _, i}
            {@const rand1 = (1 + (Math.sin(i) - 0.5) * Math.random() / 2)}
            {@const rand2 = (1 + (Math.cos(i) - 0.5) * Math.random() / 2)}
            {@const rand3 = (1 + (Math.cos(i) - 0.5) * Math.random() / 2)}
            <svg
                width={width}
                height={height}
            >
                <path
                    d="M {rand1 * width / 2} 2 Q {rand3 * width / 2} {height / 2} {rand2 * width / 2} {height - 2}"
                    stroke={color}
                />
            </svg>
        {/each}
    </div>
</div>

<style>
    .lines-wrapper {
        flex: 1;
        display: flex;
        flex-direction: row-reverse;
        justify-content: center;
        align-items: center;
        gap: 16px;
        height: 100%;
        font-family: 'Roboto', sans-serif;
        overflow: auto;
    }

    .lines {
        flex: 1;
        display: flex;
    }

    path {
        fill: none;
        stroke-width: 4;
        stroke-linecap: round;
    }
</style>