<script>
    import "./../app.css";
    import Image from './../lib/images/image.png'
    import { fly } from 'svelte/transition';

</script>
<div class="text-white flex flex-row justify-between h-[100vh]">
    <div class="w-[420px] py-5 bg-[#4c6c62] px-5 h-full">
        <img src={Image} class="w-[200px] self-center ml-5"/>
        <label>Nutzer auswählen</label>
        <select class="w-full mt-3 p-3 bg-transparent hover:bg-[#FFF000] cursor-pointer">
            <option>Frida</option>
            <option>Farisa</option>
            <option>Alex</option>
        </select>
        <div class="h-12"></div>
        <label>Entwicklungen</label>
        <a href="/test" class="block px-5 py-3 hover:bg-[#FFF000] cursor-pointer">test</a>
        <a href="/stats/baseline" class="block px-5 py-3 hover:bg-[#FFF000] cursor-pointer">Baseline zeug</a>
    </div>
    <div class="flex-1 p-20">
        <slot/>
    </div>
</div>
