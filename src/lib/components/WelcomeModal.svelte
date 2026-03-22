<script lang="ts">
	import Modal from "$lib/components/Modal.svelte";
	import IconOmni from "$lib/components/icons/IconOmni.svelte";
	import { usePublicConfig } from "$lib/utils/PublicConfig.svelte";

	const publicConfig = usePublicConfig();

	interface Props {
		close: () => void;
	}

	let { close }: Props = $props();
</script>

<Modal closeOnBackdrop={false} onclose={close} width="!max-w-[420px] !m-4">
	<div
		class="flex w-full flex-col gap-8 bg-white bg-gradient-to-b to-transparent px-6 pb-7 dark:bg-black dark:from-white/10 dark:to-white/5"
	>
		<div
			class="relative -mx-6 grid h-48 select-none place-items-center bg-gradient-to-t from-black/5 dark:from-white/10"
		>
			<div class="flex size-full items-center justify-center bg-gradient-to-br from-gray-900 to-gray-800">
				<h2 class="text-4xl font-bold tracking-tight text-white">
					Heidi <span class="text-blue-400">AI</span>
				</h2>
			</div>
			<div
				class="absolute bottom-3 right-3 rounded-lg border border-blue-500/20 bg-blue-500/20 px-2 py-0.5 text-sm font-semibold text-blue-500"
			>
				Now with MCP!
			</div>
		</div>

		<div class="text-gray-700 dark:text-gray-200">
			<p class="text-[15px] leading-relaxed">
				Welcome to Heidi AI, your intelligent chat assistant powered by the latest AI models.
			</p>
			<p class="mt-3 text-[15px] leading-relaxed">
				<IconOmni classNames="-translate-y-px" /> Omni automatically picks the best AI model to give
				you optimal answers depending on your requests.
			</p>
			<p class="mt-3 text-[15px] leading-relaxed">
				You can also choose from any available AI models to chat with directly.
			</p>
			<p class="mt-3 text-[13px] leading-relaxed text-gray-400 dark:text-gray-500">
				Created by Aryan Bunkar
			</p>
		</div>

		<button
			class="w-full rounded-xl bg-black px-5 py-2.5 text-base font-medium text-white hover:bg-gray-800 dark:bg-white dark:text-black dark:hover:bg-gray-200"
			onclick={close}
		>
			Start chatting
		</button>
	</div>
</Modal>
