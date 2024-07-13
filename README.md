# git-rebase


No Git, `rebase` é um comando utilizado para aplicar commits de uma branch em outra de uma forma linear. Isso é feito ao mover ou reescrever o histórico de commits de uma branch sobre outra. Existem dois cenários principais onde o rebase pode ser usado:

1. **Rebase Interativo (`git rebase -i`)**: Permite modificar commits existentes em uma branch, como editar mensagens de commit, reordenar commits, combinar commits (squash) ou mesmo remover commits. Isso é útil para limpar e organizar o histórico de commits antes de mesclá-los com a branch principal.

2. **Rebase Normal (`git rebase <branch>`)**: Muda a base dos commits da branch atual para outro commit. Por exemplo, se você está trabalhando em uma branch chamada `feature` e quer atualizar sua base com a branch `main`, você pode usar `git rebase main` enquanto está na branch `feature`. Isso aplica os commits da `feature` sobre os commits mais recentes da `main`, criando um histórico linear e evitando merges adicionais.

### Exemplo de Uso do Rebase Normal:

```sh
# Supondo que você esteja na branch "feature" e queira rebasa-la sobre "main"
git checkout feature
git rebase main
```

### Exemplo de Uso do Rebase Interativo:

```sh
# Supondo que você queira fazer um rebase interativo nos últimos 3 commits
git rebase -i HEAD~3
```

Durante o rebase interativo, um editor de texto será aberto com uma lista dos commits que podem ser modificados. Você pode então escolher ações como `pick`, `squash`, `edit`, etc.

### Vantagens do Rebase:
- **Histórico Limpo**: Mantém o histórico de commits linear e mais fácil de entender.
- **Facilita a Integração**: Resolve conflitos antes da integração, evitando commits de merge complexos.

### Cuidados ao Usar Rebase:
- **Histórico Reescrito**: Muda o hash dos commits, o que pode causar problemas se a branch já foi compartilhada com outros desenvolvedores.
- **Conflitos**: Pode ser necessário resolver conflitos manualmente durante o processo de rebase.

Rebase é uma ferramenta poderosa, mas deve ser usada com cuidado, especialmente em branches que já foram compartilhadas com outros desenvolvedores.
