<script lang="ts">
    type ManageButtonProps = {
	text : string,
	href : string,
	imgUrl : string,
	alt? : string
    };
    const manageButtons : Array<ManageButtonProps> = [
	{ 
	    text : "Create Menu",
	    href : "/manage/create",
	    imgUrl : "/add-circle.svg"
	}
    ];
</script>

{#snippet ManageButton(content : ManageButtonProps)}
    <a href={content.href} class="manage-btn">
	<div class="manage-btn-img-wrapper">
	    <img src={content.imgUrl} alt={content.alt ?? ""} class="manage-btn-img"/>
	</div>
	<span class="manage-btn-text">{content.text}</span>
    </a>
{/snippet}
<header class="manage-header flex items-center gap-x-2 px-7 pt-10 pb-8">
    <nav class="prev px-2">
	<a href=".." class="prev-button text-2xl text-yellow-600 hover:text-yellow-900 hover:underline underline-offset-2">↩ Home</a>
    </nav>
    <h1 class="text-4xl font-semibold ml-4 tracking-tight">Manage Orders</h1>
</header>
<section class="manage-section flex flex-row flex-wrap gap-[2vmin] px-8 pt-4">
    {#each manageButtons as manageBtn, index(index)}
	{#key index}
	    {@render ManageButton(manageBtn)}
	{/key}
    {/each}
</section>
<style>
.manage-btn {
    display:inline-grid;
    aspect-ratio: 1;
    grid-template-areas: 
	"img"
	"text"
	;
    grid-template-rows: [img] minmax(68%,1fr) [text] fit-content(32%);
    justify-items: center;
    border:1px double #60606074;
    border-radius:10px;
    padding:10px 6px;
    max-width:max(100px, 25vw);
    min-width:15vmin;
    box-sizing: content-box;
}
.manage-btn:hover{
    transition:box-shadow ease-in-out 100ms;
    box-shadow:4px 4px 7px -1px #B4B4B48A;
}
.manage-btn > .manage-btn-img-wrapper {
    grid-area:img;
    display:inline-flex;
    justify-content:center;
    align-items: center;
    aspect-ratio: 1;
    padding:4px;
}
.manage-btn > .manage-btn-img-wrapper > .manage-btn-img {
    flex:1;
    aspect-ratio: 1;
    object-fit: fill;
}
.manage-btn > .manage-btn-text {
    grid-area:text;
    display:inline-flex;
    flex-flow:column;
    justify-content:flex-end;
    align-items: center;
    font-size:1.1em;
    font-weight: 600;
    letter-spacing: -0.5px;
    padding:2px 3px;
    color:#444444;
}
</style>
