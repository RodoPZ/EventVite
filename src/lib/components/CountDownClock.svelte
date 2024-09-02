<script lang="ts">
    import { onMount } from 'svelte';

    let targetDate: Date = new Date('2024-09-13T00:00:00'); // Set your target date and time here
    let timeRemaining: number = targetDate.getTime() - new Date().getTime();

    let days: string = '00';
    let hours: string = '00';
    let minutes: string = '00';
    let seconds: string = '00';

    function updateCountdown(): void {
        timeRemaining -= 1000;
        days = Math.floor(timeRemaining / (1000 * 60 * 60 * 24)).toString().padStart(2, '0');
        hours = Math.floor((timeRemaining % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)).toString().padStart(2, '0');
        minutes = Math.floor((timeRemaining % (1000 * 60 * 60)) / (1000 * 60)).toString().padStart(2, '0');
        seconds = Math.floor((timeRemaining % (1000 * 60)) / 1000).toString().padStart(2, '0');
    }

    onMount(() => {
        updateCountdown();
        const interval: NodeJS.Timeout = setInterval(() => {
            updateCountdown();
            if (timeRemaining <= 0) {
                clearInterval(interval);
            }
        }, 1000);
        return () => clearInterval(interval);
    });
</script>

<div class="grid grid-cols-4 border border-primary-500 text-primary-500 p-2 min-w-72 place-items-center">
    <h3 class="h3">{days} D :</h3>
    <h3 class="h3">{hours} h :</h3>
    <h3 class="h3">{minutes} m :</h3>
    <h3 class="h3">{seconds} s</h3>
</div>
