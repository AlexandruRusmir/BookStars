<script>
    import { onMount } from 'svelte';

    export let endTime;

    let daysRemaining = 0;
    let hoursRemaining = 0;
    let minutesRemaining = 0;
    let secondsRemaining = 0;
    const countDown = () => {
        const targetTimestamp = endTime;
        let currentTimestamp = Math.floor(Date.now() / 1000);
        let secondsLeft = targetTimestamp - currentTimestamp;

        let days = Math.floor(secondsLeft / 86400);
        secondsLeft = secondsLeft % 86400;

        let hours = Math.floor(secondsLeft / 3600);
        secondsLeft = secondsLeft % 3600;

        let minutes = Math.floor(secondsLeft / 60);
        secondsLeft = secondsLeft % 60;

        daysRemaining = days;
        hoursRemaining = hours;
        minutesRemaining = minutes;
        secondsRemaining = secondsLeft;
    }

    onMount(() => {
        setInterval(countDown, 1000)
    })
</script>

<body>
    <div class="row mx-5 text-center countdown-timer-box">
        <div class="col-3">
            <p>Days:</p>
            <p class="mt-2">{daysRemaining}</p>
        </div>
        <div class="col-3">
            <p>Hours:</p>
            <p class="mt-2">{hoursRemaining}</p>
        </div>
        <div class="col-3">
            <p>Minutes:</p>
            <p class="mt-2">{minutesRemaining}</p>
        </div>
        <div class="col-3">
            <p>Seconds:</p>
            <p class="mt-2">{secondsRemaining}</p>
        </div>
    </div>
</body>

<style>
    .countdown-timer-box {
        font-size: 24px;
        font-weight: 600;
    }
</style>