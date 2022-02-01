<script>
	import Ueberschrift from "./components/Ueberschrift.svelte";
	import Untertitel from "./components/Untertitel.svelte";
	import InfoLink from "./components/InfoLink.svelte";
	import InfoModal from "./components/InfoModal.svelte";
	import Karte from "./components/Karte.svelte";
	import Formular from "./components/Formular.svelte";
	import ResultModal from "./components/ResultModal.svelte";


	let mail;

	let showInfoModal = false;
	const toggleShowInfoModal = () => {
		showInfoModal = !showInfoModal;
	};

	let showResultModal = false;
	const toggleShowResult = () => {
		showResultModal = !showResultModal;
	};

	const createMailDraft = (event) => {
		const newMail = event.detail;
		mail = newMail;

		toggleShowResult();
	};

</script>

<main>
	<Ueberschrift />
	<Untertitel />
	<Karte>
		<Formular on:create-mail-from-input={ createMailDraft } />
	</Karte>

	{#if showResultModal}
		<ResultModal mail={mail} on:close-restult-modal={ toggleShowResult } />
	{/if}

	<InfoLink on:show-info-modal={ toggleShowInfoModal } />
	{#if showInfoModal }
		<InfoModal on:close-info-modal={ toggleShowInfoModal } />
	{/if }

</main>

<style>

</style>