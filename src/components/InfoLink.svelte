<script>
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();
</script>


<div>
    <button on:click="{ () => { dispatch("show-info-modal"); } }" >
        Info zur Anwendung
    </button>
</div>



<style>

    div {
        margin-top: 20px;
        text-align: center;
    }

    button {
        border: none;
        cursor: pointer;
        text-decoration: underline;
        font-size: medium;
        color: blue;
        background-color: white;
    }
</style>