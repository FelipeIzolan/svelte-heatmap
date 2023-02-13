<rect
    data-date={stringifyDate(date)}
    data-value={value}
    on:click={click}
    fill={color}
    height={size}
    rx={radius}
    width={size}
    x={x}
    y={y}
/>

<script>
import { stringifyDate } from '../utils/date';

export let click;
export let color;
export let date;
export let radius;
export let size;
export let value;
export let x;
export let y;
</script>
