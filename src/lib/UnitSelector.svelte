<script>
    const units = [ "UPASUL", "UPALESTE" ];
</script>

<main>
    <h1 class="top-instruction">Selecione a Unidade de Saúde para a consulta:</h1>
     <section class="medicine">
        <img style="border-radius: 15px; border-color: rgba(207, 0, 0, 0.836); border-style: solid; filter: drop-shadow(0 0 0.75rem crimson);"src="/images/medicine-capsules01.png" alt="foto de remédios">
    </section>
    <section style="align-items: center; filter: drop-shadow(0 0 0.75rem crimson);">
        <!--{% for i in unidades %} -->
        {#each units as unit}
        <h1 style="color: white;">-</h1>
        <a href="#" style="cursor: pointer; font-size: 30px;" class="table__title" onclick="window.location.href = '/units/{unit}';">{unit}</a>
        {/each}
    </section>
</main>