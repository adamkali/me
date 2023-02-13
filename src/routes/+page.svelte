<script lang="ts">
	import DiReact from 'svelte-icons/di/DiReact.svelte';
	import DiGo from 'svelte-icons/di/DiGo.svelte';
	import DiRust from 'svelte-icons/di/DiRust.svelte';
	import DiPython from 'svelte-icons/di/DiPython.svelte';
	import DiVim from 'svelte-icons/di/DiVim.svelte';
	import DiDotnet from 'svelte-icons/di/DiDotnet.svelte';
	import axios from 'axios';

	import '../app.css';
	import Icon from './Icon.svelte';

	export let expShow: boolean;
	export let skillShow: boolean;
	export let learningShow: boolean;

	$: expShow = false;
	export const onExpMouseHover = () => {
		expShow = !expShow;
	};

	$: skillShow = false;
	export const onSklMouseHover = () => {
		skillShow = !skillShow;
	};

	$: learningShow = false;
	export const onLearnMouseHover = () => {
		learningShow = !learningShow;
	};
</script>

<div
	class="flex h-screen w-screen flex-col justify-start bg-gradient-to-tr from-gray-900 to-zinc-600 px-96 text-2xl text-slate-400"
>
	<div class="flex flex-col justify-center pt-2 pb-16 text-justify align-middle">
		<div class="pb-4 text-6xl">Hi, I'm Adam</div>
		<span>
			I am a Full Stack Software Engineer. My hobbies include: playing table top roleplaying games,
			making software for my table top roleplaying games, and spending more time at work so that I
			can't play my table top roleplaying games. I am a hard worker, that enjoys everything about
			software. I like to use Neovim for all my software development needs, and enjoy learning the
			tools that I use to make my life easier. Also check out my configs:
			<div class="flex flex-row">
				<div class="pr-8 hover:animate-pulse">
					<a
						href="https://github.com/adamkali/LuaNeovimConfig"
						class="max-w-fit rounded-lg bg-gray-900 px-4 text-cyan-300"
					>
						Neovim
					</a>
				</div>
				<div class="pr-8 hover:animate-pulse">
					<a
						href="https://github.com/adamkali/WeztermConfig"
						class="max-w-fit rounded-lg bg-gray-900 px-4 text-cyan-300"
					>
						Wezterm
					</a>
				</div>
				<div class="pr-8 hover:animate-pulse">
					<a
						href="https://github.com/adamkali/arch-bootstrap/tree/main/config/leftwm/themes/vapor"
						class="max-w-fit rounded-lg bg-gray-900 px-4 text-cyan-300"
					>
						LeftWM
					</a>
				</div>
			</div>
		</span>
	</div>
	<div class="flex flex-row justify-center">
		<div
			class="me-section group"
			on:mouseenter={() => {
				onSklMouseHover();
			}}
			on:mouseleave={() => {
				onSklMouseHover();
			}}
		>
			<div class="pb-6 text-center text-3xl group-hover:text-indigo-400">What I Use</div>
			<div class="grid grid-rows-6 gap-4">
				<a href="http://www.rust-lang.org">
					<div
						class="grid grid-cols-3 rounded-xl text-lg transition-all duration-300 ease-out hover:bg-gray-300/30 hover:text-orange-400 hover:ease-in"
					>
						<div class="h-24"><DiRust /></div>
						<div class="text-center align-middle text-3xl"><p>Rust</p></div>
						<div class="whitespace-pre-wrap">
							<span class="flex-wrap">A Blazingly Fast Language for the Modern World</span>
						</div>
					</div>
				</a>
				<a href="https://dotnet.microsoft.com/en-us/">
					<div
						class="grid grid-cols-3 rounded-xl text-lg transition-all duration-300 ease-out hover:bg-gray-300/30 hover:text-indigo-400 hover:ease-in"
					>
						<div class="h-24"><DiDotnet /></div>
						<div class="text-center align-middle text-3xl"><p>.Net</p></div>
						<div class="whitespace-pre-wrap"><p>Make Applications that Scale</p></div>
					</div>
				</a>
				<a href="https://reactjs.org/">
					<div
						class="grid grid-cols-3 rounded-xl text-lg transition-all duration-300 ease-out hover:bg-gray-300/30 hover:text-cyan-400 hover:ease-in"
					>
						<div class="h-24"><DiReact /></div>
						<div class="text-center align-middle text-3xl">React</div>
						<div class="whitespace-pre-wrap"><p>The Intuitve Frontend Framework</p></div>
					</div>
				</a>
				<a href="https://neovim.io/">
					<div
						class="grid grid-cols-3 rounded-xl text-lg transition-all duration-300 ease-out hover:bg-gray-300/30 hover:text-lime-400 hover:ease-in"
					>
						<div class="h-24"><DiVim /></div>
						<div class="text-center align-middle text-3xl">Neovim</div>
						<div class="whitespace-pre-wrap"><p>The Endgame Text Editor</p></div>
					</div>
				</a>
				<a href="https://www.python.org/">
					<div
						class="grid grid-cols-3 rounded-xl text-lg transition-all duration-300 ease-out hover:bg-gray-300/30 hover:text-yellow-400 hover:ease-in"
					>
						<div class="h-24"><DiPython /></div>
						<div class="text-center align-middle text-3xl">Python</div>
						<div class="whitespace-pre-wrap"><p>My Go To Scripting Language</p></div>
					</div>
				</a>
				<a href="https://go.dev/">
					<div
						class="grid grid-cols-3 rounded-xl text-lg transition-all duration-300 ease-out hover:bg-gray-300/30 hover:text-sky-400 hover:ease-in"
					>
						<div class="h-24"><DiGo /></div>
						<div class="text-center align-middle text-3xl">Golang</div>
						<div class="whitespace-pre-wrap"><p>The Natural Concurrent Language</p></div>
					</div>
				</a>
			</div>
		</div>
		<div
			class="me-section group mx-8"
			on:mouseenter={() => {
				onExpMouseHover();
			}}
			on:mouseleave={() => {
				onExpMouseHover();
			}}
		>
			<div class="pb-6 text-center text-3xl group-hover:text-indigo-400">What I am Doing</div>
			<div class="decoration-none grid grid-rows-3 text-ellipsis text-lg">
				<a href="https://v5.efilemadeeasy.com">
					<div
						class="rounded-xl p-4 transition-all duration-300 ease-out hover:bg-gray-300/30 hover:text-blue-900 hover:ease-in"
					>
						<span class="font-bold">Full Stack Engineer | eFileMadeEasy</span>
						<p>
							Lead Engineer on the eFileMadeEasy Microsoft Word Add-in, Full Stack Engineer for
							<span class="max-w-fit rounded-lg bg-gray-900 px-4 text-cyan-300">eFileMadeEasy</span
							>.
						</p>
					</div>
				</a>
				<a href="https://github.com/fdehau/tui-rs">
					<div
						class="rounded-xl p-4 transition-all duration-300 ease-out hover:bg-gray-300/30 hover:text-blue-900 hover:ease-in"
					>
						<span class="flex flex-row font-bold"> Contributer | tui-rs-revival </span>
						<p>
							A fork revival of the unmaintained
							<span class="max-w-fit rounded-lg bg-gray-900 px-4 text-cyan-300"> tui-rs </span>. A
							fabulous crate for making intelligent tui applications in rust.
						</p>
					</div>
				</a>
				<a href="https://github.com/adamkali/MiraculousKingdom">
					<div
						class="rounded-xl p-4 transition-all duration-300 ease-out hover:bg-gray-300/30 hover:text-blue-900 hover:ease-in"
					>
						<span class="font-bold">Developer | Miraculous Kingdom</span>
						<p>
							A table top roleplaying game, based around the idea of political intrigue and
							backstabbing made popular by recent popular shows like Game of Thrones or House of
							Cards. (Click the box to check the pre-alpha ruleset)
						</p>
					</div>
				</a>
			</div>
		</div>
		<div class="me-section group">
			<div class="pb-6 text-center text-3xl group-hover:text-indigo-400">Check Out What I Love</div>
			<div class="flex flex-col">
				<a
					class="rounded-xl p-4 transition-all duration-300 ease-out hover:bg-gray-300/30 hover:text-blue-900 hover:ease-in"
					href="https://jellyfin.org"
				>
					<img src="https://jellyfin.org/images/logo.svg" />
				</a>
				<a
					class="flex flex-row rounded-xl p-4 transition-all duration-300 ease-out hover:bg-gray-300/30 hover:text-blue-900 hover:ease-in"
					href="https://www.photoprism.app"
				>
					<img
						src="https://secure.gravatar.com/avatar/e0ee421cf83fc2240825cda2b5139f64.jpg?s=120&r=g&d=404"
					/>
					<div class="justify-center align-middle text-5xl">Photoprism</div>
				</a>
				<a
					class="rounded-xl p-4 transition-all duration-300 ease-out hover:bg-gray-300/30 hover:text-blue-900 hover:ease-in"
					href="https://tauti.app"
				>
					<img src="https://tauri.app/img/index/header_dark.svg" />
				</a>
				<a
					class="rounded-xl p-4 transition-all duration-300 ease-out hover:bg-gray-300/30 hover:text-blue-900 hover:ease-in"
					href="https://tailwindcss.com"
				>
					<img
						src="https://tailwindcss.com/_next/static/media/tailwindcss-logotype-white.e0b2bd6155fa0bed8e24ff6b28f4a911.svg"
					/>
				</a>
				<a
					class="rounded-xl p-4 transition-all duration-300 ease-out hover:bg-gray-300/30 hover:text-blue-900 hover:ease-in"
					href="https://svelte.dev"
				>
					<img
						src="https://github.com/sveltejs/branding/blob/master/svelte-horizontal.png?raw=true"
					/>
				</a>
			</div>
		</div>
	</div>
</div>
