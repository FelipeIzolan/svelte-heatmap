<g transform={`translate(${translation}, ${monthLabelHeight})`}>
    {#each days as day}
        <Cell
            click={cellClick}
            color={day.color}
            date={day.date}
            radius={cellRadius}
            size={cellSize}
            value={day.value}
            y={day.date.getDay() * cellRect}
        />
    {/each}
</g>

<script>
import Cell from './Cell.svelte';

$: translation = cellRect * index;

export let cellRadius;
export let cellRect;
export let cellSize;
export let cellClick;
export let days;
export let index;
export let monthLabelHeight;
</script>
