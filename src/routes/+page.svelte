<script lang="ts">

</script>

<main class="index-content h-screen overflow-auto">
    <header class="heading inline-flex justify-center">
	<h1 class="heading-text tracking-tight">Ordesius</h1>
    </header>
    <br class="artificial-gap"/>
    <nav class="buttons inline-flex justify-center items-center">
	<a href="/manage" class="index-btn">Manage Orders</a>
	<a href="/order" class="index-btn">Take Order</a>
    </nav>
</main>

<style>
    .index-content{
	--grid-px:minmax(auto,1fr);
	--grid-py:minmax(auto,1fr);
	--middle-gap:minmax(10px, 5vh);
	display: grid;
	grid-template-areas:
	    ". . ."
	    ". heading ."
	    ". artificial-gap ."
	    ". buttons ."
	    ". . ."
	    ;
	grid-template-rows: 
	    var(--grid-py)
	    [heading] minmax(0, min-content)
	    [artificial-gap] var(--middle-gap)
	    [buttons] minmax(0, min-content)
	    var(--grid-py)
	    ;
	grid-template-columns: 
	    var(--grid-px)
	    [heading] minmax(max-content,auto)
	    [artificial-gap] minmax(0,auto)
	    [buttons] minmax(0,auto)
	    var(--grid-px)
	    ;
	background-color:#FCE08A;
    }
    .index-btn{
	font-size:calc(0.86em + 0.86vmin);
	font-weight: bold;
    }
    .heading{
	grid-area:heading;
    }
    .heading-text{
	font-size:calc(5em + 5vmin);
	color:#E46400;
    }
    .artificial-gap{
	grid-area: artificial-gap;
    }
    .buttons{
	grid-area: buttons;
	column-gap:calc(8px + 2vw);
    }
    .index-btn{
	--absolute-padding:1px;
	--px:calc(1vw + var(--absolute-padding));
	--py:calc(1.3vh + var(--absolute-padding));
	border: 0px solid transparent;
	border-radius:14px;
	padding:var(--py) var(--px);
	background-color: #FF8500;
	color:white;
    }
    .index-btn:hover{
	color:#541610;
	outline:2px solid orangered;
	outline-offset:1px;
    }
</style>
