# rust-webassembly-in-asp.net-core-mvc
using webassembly (with rust ) in asp.net core mvc



1. cargo install wasm-pack
2. cargo generate --git https://github.com/rustwasm/wasm-pack-template.git --name my-project
3. in the my-project directory run the command wasm-pack build --release --target web
4. copy the files  in pkg directory to asp.net core www folder
	*.js
	*_bg.js
	*_bg.wasm
5. in _layout.cshtml
		<script type="module" src="~/samplewasm.js"></script>
6.<script type="module">
    import init from './samplewasm.js';
    import { greet } from './samplewasm.js';
    async function run() {
        await init();
        greet();
    }
    run();
</script>

7. references
	https://javascript.tutorialink.com/failed-to-load-wasm-application/
	https://levelup.gitconnected.com/using-javascript-modules-in-the-browser-2c55bfc5f5e9
