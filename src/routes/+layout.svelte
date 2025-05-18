<script lang="ts">
    import "./app.css";
    const { children } = $props();
</script>

<div id="root-order-system" class="flow-root min-h-screen noto-sans-font">
    {@render children()}
</div>
