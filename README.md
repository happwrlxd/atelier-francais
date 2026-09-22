# Atelier Français

Site de aprendizado de francês para quem fala português. Código completo, estático e independente de frameworks. Não precisa de conta, API, banco de dados, instalação de pacotes ou processo de compilação.

## Abrir no computador

1. Extraia o ZIP inteiro.
2. Abra a pasta `atelier-francais`.
3. Dê dois cliques em `index.html`.

Mantenha os arquivos e a pasta `assets` juntos. Não abra o HTML ainda dentro do ZIP. As aulas, exercícios e a transcrição funcionam localmente. O comportamento do progresso em `file://` varia entre navegadores; com hospedagem HTTP/HTTPS ele fica associado ao endereço do site. Vozes francesas podem precisar de instalação e/ou conexão.

Opcional, para desenvolvimento com Node.js: execute `npm start` nessa pasta e abra `http://localhost:4173`. Não é necessário `npm install`.

## Publicar no GitHub Pages, passo a passo

1. Entre no GitHub e crie um repositório público, por exemplo `atelier-francais`.
2. No repositório, clique em **Add file → Upload files**.
3. Entre na pasta extraída e envie **o conteúdo dela**, incluindo a pasta `assets`. O `index.html` deve ficar na raiz do repositório, não dentro de uma segunda pasta `atelier-francais`.
4. Clique em **Commit changes** para salvar os arquivos.
5. Vá a **Settings → Pages**.
6. Em **Build and deployment → Source**, escolha **Deploy from a branch**.
7. Em **Branch**, selecione `main` e `/(root)`. Clique em **Save**.
8. Aguarde a publicação. A própria página de configurações exibirá o endereço do site. Confira a aba **Actions** se a publicação apresentar falha.

O endereço costuma seguir o formato `https://SEU-USUARIO.github.io/atelier-francais/`. Substitua os exemplos pelo seu usuário e pelo nome real do repositório; o endereço exibido pelo GitHub é a referência definitiva.

Para incluir no seu portfólio existente, coloque os arquivos em uma pasta como `frances/` e adicione um link para ela. Os caminhos são relativos e a navegação usa fragmentos (`#aula/sons`), por isso funciona em subpastas sem regras especiais de redirecionamento.

**Envie arquivos extraídos, não o ZIP.** Se o site mostrar uma página de repositório ou o README, confira se o `index.html` está no diretório escolhido em Pages.

Documentação oficial consultada em 22/09/2026: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## O que está incluído

- 22 aulas em português, cobrindo os assuntos do PDF e fundamentos de gramática.
- 156 expressões revisadas, com tradução e botões de leitura em francês.
- 44 questões com feedback e explicações.
- Revisão geral aleatória, revisão por aula e cartões de memória.
- Busca em francês ou português, sem exigir acentos.
- Consulta e busca nas 70 páginas do documento original.
- PDF original completo, sem modificação de seus bytes.
- Fontes externas, referências por aula e tabela de correções do guia.
- Layout adaptável, navegação por teclado e opção de impressão de aulas.
- Progresso salvo localmente neste navegador.

## Arquivos

| Arquivo | Função |
| --- | --- |
| `index.html` | Estrutura inicial, navegação e metadados |
| `styles.css` | Aparência e comportamento responsivo |
| `app.js` | Aulas, navegação, exercícios, áudio, busca e progresso |
| `conteudo.js` | Conteúdo das 22 aulas, expressões e perguntas |
| `guia.js` | Transcrição integral por página |
| `assets/guia-original.pdf` | Documento enviado, preservado |
| `.nojekyll` | Sinaliza publicação estática no GitHub Pages |
| `package.json` | Comandos opcionais de desenvolvimento |
| `dev-server.mjs` | Servidor local opcional, sem dependências |
| `VERIFICACAO.md` | Verificações e limites conhecidos |

## Personalizar

- **Cores:** altere as variáveis `--navy`, `--blue`, `--lime` etc. no início de `styles.css`.
- **Nome do site:** edite a marca e o título em `index.html`, além das referências em `app.js`.
- **Aulas:** edite os objetos em `conteudo.js`. Cada aula tem identificador único, seções, expressões e perguntas.
- **Perguntas:** `answer` é o índice da opção correta, começando por zero.
- **Referências:** `sourceMap` em `app.js` contém os links; `corrections` contém as observações editoriais.
- **Áudio:** `utterance.rate` em `app.js` controla a velocidade. O site escolhe uma voz `fr-FR` ou outra voz `fr` disponível.

Se adicionar/remover aulas ou expressões, atualize também os totais visíveis atualmente definidos no HTML e no início das telas em `app.js`.

## Conteúdo, áudio e privacidade

As explicações e questões são uma adaptação didática original em português. O PDF de origem contém erros, terminologia antiga e português europeu. A consulta integral preserva essas características e as sinaliza; as aulas usam exemplos revisados. A tabela de correções não equivale a uma revisão editorial completa de todas as entradas do PDF.

O percurso é introdutório, não um currículo certificado nem garantia de nível A1/A2. Há variação regional no francês. As fontes externas apoiam temas específicos; nenhuma organização citada é parceira ou certificadora deste site.

O áudio é síntese de voz do dispositivo, não gravação de professor. Sem uma voz francesa instalada/disponível, o site explica que a reprodução não está disponível. Não há reconhecimento de fala ou avaliação automática da pronúncia. Alguns provedores de voz podem processar o texto pela rede conforme o sistema do visitante.

O progresso usa a chave `atelier-francais-v1` no `localStorage`. Não há cadastro, rastreamento, telemetria ou envio do progresso a um servidor. Os botões de conclusão registram que você terminou a leitura; não dependem da pontuação do exercício. A pontuação das rodadas é temporária e reinicia ao sair da revisão.

O site usa fontes locais do sistema: não depende de Google Fonts, CDNs ou imagens externas. Abrir referências externas e certas vozes pode exigir internet. Não há service worker; uma versão hospedada não promete funcionar offline após a primeira visita.

O documento original acompanha o pacote como material fornecido pelo usuário. Os direitos do documento e das fontes externas continuam com seus respectivos titulares. Não se atribui licença de terceiros ao PDF.

## Verificação opcional de sintaxe

Com Node.js instalado, execute `npm run check`. A hospedagem não precisa de Node.js.
