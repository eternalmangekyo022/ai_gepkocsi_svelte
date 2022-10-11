<script lang="ts">
    let height = 5;
    let interval: NodeJS.Timer;

    const shrink = (): void => {
        if (interval) clearInterval(interval);
        interval = setInterval(() => {
            height -= 0.25;
            if (height === 5) {
                clearInterval(interval);
                interval = null;
            }
        }, 0.000001);
    };

    const spread = (): void => {
        if (interval) clearInterval(interval);
        interval = setInterval(() => {
            height += 0.25;
            if (height === 15) {
                clearInterval(interval);
                interval = null;
            }
        }, 0.000001);
    };
</script>

<div class="bg-black w-full absolute" style={`height: ${height}rem;`}>
    <button
        class="flex flex-col justify-around w-10 h-8 absolute mt-5 ml-10"
        on:click={height === 15 ? shrink : spread}
    >
        <div class="w-full bg-white h-1">&zwnj;</div>
        <div class="w-full bg-white h-1">&zwnj;</div>
        <div class="w-full bg-white h-1">&zwnj;</div>
    </button>
    <img
        src="https://www.svgrepo.com/show/202022/question.svg"
        width="50"
        draggable={false}
        class="rounded-full cursor-pointer bg-white absolute top-5 right-10"
        alt=""
    />
</div>
