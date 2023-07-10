<template>
  <div class="greetings">
    <h1 class="green">Workshop - Git Flow</h1>
    <h3>
      Como gerenciar versionamento de projetos Git usando Git Flow.
      <br>
      <ul>
        <li>
          <a href="https://www.atlassian.com/br/git/tutorials/learn-git-with-bitbucket-cloud" target="_blank"
            rel="noopener">Aprenda o Git com Bitbucket Cloud</a>
        </li>
        <li>
          <a href="https://www.atlassian.com/br/git/tutorials/comparing-workflows/gitflow-workflow" target="_blank"
            rel="noopener">Fluxo de trabalho de Gitflow</a>.
        </li>
      </ul>
    </h3>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {

  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}</style>
