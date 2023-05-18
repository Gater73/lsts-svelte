<header>
    <div class="logo-top">
        <a href="/"><img src="/images/logo lsts.jpg" alt="project logo"></a>
    </div>
    <form action="" method="" class="searcher">
        <input type="text" onclick="window.location.href = '/units';" placeholder="Busque Aqui..." name="q">
        <button type="submit"><img src="/images/search.png" alt="lupa"></button>
    </form>
    <nav class="menu-itens">
        <a href="/">仚 Home</a> <!-- 仚 Home -->
        <a href="/about">⎎ Sobre Nós</a> <!-- ⎎ Sobre Nós -->
        <a href="/units">✚ Remédios</a> <!-- ✚ Remédios -->
    </nav>
    <div class="menu-bar">
        <div class="bar"></div>
        <div class="bar"></div>
        <div class="bar"></div>
    </div>
</header>

<slot />

<footer>
    <p>&copy;Todos os direitos reservados </p>
</footer>