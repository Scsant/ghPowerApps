# ghPowerApps

Repositório para projetar e desenvolver sistemas com Microsoft Power Apps. As
instruções e skills para GitHub Copilot ficam em `.github/`; a colaboração com
Canvas Apps usa o servidor Canvas Authoring MCP oficial da Microsoft, conectado
a uma sessão de coautoria aberta no Power Apps Studio.

## Objetivos

- Criar soluções Power Apps orientadas a requisitos e necessidades reais.
- Usar o Canvas Authoring MCP para inspecionar, validar e sincronizar Canvas Apps
  com a sessão de coautoria ativa.
- Usar o agente GitHub Copilot para apoiar o ciclo de desenvolvimento, mantendo
  as alterações revisáveis e a documentação atualizada.
- Validar o comportamento da solução antes de disponibilizá-la.

## Preparar o ambiente

1. Use o GitHub Copilot em um host compatível com plugins e MCP, como o VS Code
   com Copilot Chat no modo Agent.
2. Instale o plugin oficial **Canvas Apps**, da Microsoft, pelo marketplace de
   plugins/agentes do VS Code. O plugin vem do repositório
   [microsoft/power-platform-skills](https://github.com/microsoft/power-platform-skills);
   prefira o marketplace para receber atualizações, em vez de copiar o plugin
   para este repositório.
3. Instale o .NET 10 SDK ou posterior e confirme que `dotnet --list-sdks` lista
   uma versão 10 ou superior.
4. Crie ou abra o Canvas App no ambiente Power Platform pretendido. No Power
   Apps Studio, habilite **Settings > Updates > Coauthoring** e mantenha a aba
   aberta durante o trabalho.
5. No Copilot, execute a skill `configure-canvas-mcp` do plugin Microsoft e
   informe a URL da sessão do Studio quando solicitado. Confirme a conexão
   pedindo ao agente para listar os controles disponíveis.

O Canvas Authoring MCP depende da sessão local aberta no Studio e da autenticação
do usuário autorizado. Não compartilhe URLs de sessão, tokens ou credenciais em
commits, prompts públicos ou logs. O servidor não cria o registro inicial do app
nem habilita a coautoria.

> A configuração local do Canvas Authoring MCP não conecta uma sessão do Power
> Apps Studio ao GitHub Copilot coding agent hospedado. Para editar o app via
> coautoria, use um host local compatível com MCP e o plugin oficial.

## Fluxo de desenvolvimento

1. Descrever o problema, os usuários, os dados envolvidos e os critérios de
   aceitação.
2. Confirmar o app e ambiente pretendidos e verificar que a conexão
   `canvas-authoring` está ativa.
3. Sincronizar e revisar o estado atual do app antes de editar; preservar as
   alterações locais existentes.
4. Pedir ao Copilot um plano pequeno e implementar em etapas, usando o MCP para
   validar as mudanças.
5. Revisar a solução no Studio, testar fluxos principais e casos de erro e
   atualizar a documentação. Publicar somente quando solicitado explicitamente.

## Segurança e validação

- Nunca armazenar credenciais, tokens ou segredos no repositório.
- Não presumir acesso ou autorização para alterar aplicativos, dados ou
  ambientes; usar apenas os recursos disponibilizados e aprovados.
- Não sincronizar se isso puder sobrescrever trabalho local não revisado.
- Revisar as alterações produzidas pelo agente e validar a solução no ambiente
  Power Apps antes de publicá-la.

## Estado atual

O repositório fornece instruções para o Copilot em
`.github/copilot-instructions.md` e uma skill de coautoria Canvas App em
`.github/skills/power-apps-canvas-coauthoring/`. Ainda não contém um app Power
Apps, ferramentas de build ou testes automatizados; adicione-os conforme os
requisitos da primeira solução.
