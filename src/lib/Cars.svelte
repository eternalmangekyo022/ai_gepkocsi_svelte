<script lang="ts">
    let index = 0;

    type Car = {
        name: string;
        src: string;
    };

    const cars: Car[] = [
        {
            name: 'Tesla',
            src: 'https://www.picng.com/upload/tesla_car/png_tesla_car_23352.png',
        },
        {
            name: 'Bugatti',
            src: 'https://www.pngmart.com/files/10/Bugatti-Veyron-Transparent-Background.png',
        },
        {
            name: 'Lamborghini',
            src: 'https://assets.stickpng.com/images/580b585b2edbce24c47b2c83.png',
        },
    ];

    const increment = (): void => {
        index = index === cars.length - 1 ? 0 : index + 1;
    };

    const decrement = (): void => {
        index = index === 0 ? cars.length - 1 : index - 1;
    };
</script>

<div class="relative w-[50vw] h-[30rem]">
    <img
        class="absolute w-[800px] left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2"
        src={cars[index].src}
        alt={cars[index].name}
        width="700"
        draggable={false}
    />
    <img
        draggable={false}
        on:click={decrement}
        src="https://www.svgrepo.com/show/335907/left-c.svg"
        class="absolute top-1/2 -translate-y-1/2 left-10 cursor-pointer"
        alt=""
    />
    <img
        draggable={false}
        on:click={increment}
        src="https://www.svgrepo.com/show/335932/right-c.svg"
        class="absolute top-1/2 -translate-y-1/2 right-10 cursor-pointer"
        alt=""
    />
</div>
