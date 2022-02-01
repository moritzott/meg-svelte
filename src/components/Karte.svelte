<div class="karte">
    <slot></slot>
</div>

<style>
    .karte {
        max-width: 320px;
        border: 1px solid #dee2e6;
        border-radius: 5px;
        margin: auto;
    }

    @media screen and (max-width: 400px) {
        .karte {
        max-width: 280px;
        border: 1px solid #dee2e6;
        border-radius: 5px;
        margin: auto;
        }
    }
</style>