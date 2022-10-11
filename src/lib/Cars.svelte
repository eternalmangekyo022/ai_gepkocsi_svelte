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

<div>
    <img
        src={cars[index].src}
        alt={cars[index].name}
        width="1000"
        on:click={increment}
        draggable={false}
    />
</div>
