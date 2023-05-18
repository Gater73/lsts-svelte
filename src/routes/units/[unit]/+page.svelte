<script lang="ts">
    import { page } from '$app/stores';
    import { onMount } from 'svelte';
  
    export let items = [];
    const unit = $page.params.unit;
    console.log(unit);
    
    const headings: string[] = ["ID", "Nome", "Quantidade"];
  
    // Load data when the component is mounted
    onMount(async () => {
      await loadItems();
    });
  
    async function loadItems() {
      try {
        const response = await fetch(`http://127.0.0.1:8888/api/${unit}`);
        const data = await response.json();
        if (data && data.length > 0) {
          items = data;
        }
      } catch (error) {
        console.error('Error loading data:', error);
      }
    }
  </script>

<main>
    <section class="top">
        <h1 class="table__title">{ unit }</h1>
        <h1 class="table__title">Remédios</h1>

        {#if items.length > 0}
        <table id="table" class="table">
        <tbody>
            <tr class="table__header">
                <!-- {% for header in headings %} -->
                {#each headings as header}
                    <th class="table__cell"> {header} </th>
                {/each}
                <!-- {% endfor %} -->
            </tr>
            <!-- {% for row in data %} -->
            {#each items as item}
            <tr class="table__row">
                <!-- {% for cell in row %} -->
                <!-- {#each row as cell}  -->
                <!-- <td {% if loop.index == middle_column %}class="middle-column table__cell"{% else %}class="table__cell"{% endif %}>{{ cell }}</td> -->
                <td class="table__cell">{item._id}</td>
                <td class="table__cell">{item.name}</td>
                <td class="table__cell">{item.quant}</td>
                <!-- {% endfor %} -->
                <!-- {/each}  -->
            </tr>
            {/each}
            <!-- {% endfor %} -->
        </tbody>
        </table>
        {:else}
        <h1 class="table__title">Erro ao conectar ao banco de dados!</h1>
        {/if}
    </section>
    <section class="about-us">
        <article>
            <h2>AVISO!</h2>
            <p>O LSTS foi criado com o intuito de solucionar a necessidade da população em terem maior acesso as informações relacionadas ao estoque de medicamentos das farmácias do SUS, mas por enquanto os medicamentos e quantidades descritos na tabela acima são totalmente fícticios, estando o projeto em FASE DE TESTE!</p>
        </article>
    </section>
</main>