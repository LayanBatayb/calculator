<script lang="ts">
    import Divisn from "./../lib/icon/divisn.svelte";
    import Minus from "./../lib/icon/minus.svelte";
    import Backspace from "$lib/icon/backspace.svelte";

    function addToEquation(value: string) {
        equation += value;
    }

    function backspace() {
        equation = equation.substring(0, equation.length - 1);
    }
    function clear() {
        equation = "";
    }

    function solve() {
        equation = eval(equation);
    }
    let equation: string = $state("");
</script>

<svelte:head>
    <title>calculator</title>
</svelte:head>

<div
    class="bg-[#04012e] min-h-[30rem] min-w-[20rem] rounded-3xl grid grid-cols-4 gap-1 p-6 pt-12 font-semibold text-2xl shadow-2xl shadow-black"
>
    <div
        class="bg-blue-200 rounded-full col-span-4 h-16 flex items-center px-4 mb-3 text-cyan-900 text-3xl"
    >
        {equation}
    </div>
    <button onclick={() => addToEquation("/100")} class="bg-blue-50">%</button>
    <button onclick={() => backspace()} class="bg-blue-50">
        <Backspace />
    </button>

    <button onclick={() => clear()} class="bg-blue-400 text-white">C</button>
    <button onclick={() => addToEquation("-")} class="bg-blue-200">
        <Minus />
    </button>
    <button onclick={() => addToEquation("7")}>7</button>
    <button onclick={() => addToEquation("8")}>8</button>
    <button onclick={() => addToEquation("9")}>9</button>
    <button onclick={() => addToEquation("/")} class="bg-blue-200">
        <Divisn />
    </button>
    <button onclick={() => addToEquation("4")}>4</button>
    <button onclick={() => addToEquation("5")}>5</button>
    <button onclick={() => addToEquation("6")}>6</button>
    <button onclick={() => addToEquation("*")} class="bg-blue-200">×</button>
    <button onclick={() => addToEquation("1")}>1</button>
    <button onclick={() => addToEquation("2")}>2</button>
    <button onclick={() => addToEquation("3")}>3</button>
    <button onclick={() => addToEquation("+")} class="bg-blue-200">+</button>
    <button onclick={() => addToEquation(".")}>.</button>
    <button onclick={() => addToEquation("0")}>0</button>
    <button onclick={() => solve()} class="bg-blue-100 col-span-2">=</button>
</div>
