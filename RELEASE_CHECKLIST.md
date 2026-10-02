# Checklist de publicação do SaySell para Windows

Esta checklist define verificações para uma publicação futura. Ela não atesta que um build já foi testado ou que o atualizador está configurado.

## Antes de publicar

- [ ] Gerar o build a partir de uma revisão identificada do código-fonte privado, mantendo o registro dessa revisão fora deste repositório.
- [ ] Usar uma versão superior à última publicada no mesmo canal; manter a versão do aplicativo, a tag da release e os metadados consistentes. Uma correção deve receber uma nova versão.
- [ ] Testar o instalador em Windows, incluindo instalação, abertura do aplicativo e desinstalação.
- [ ] Antes de anunciar atualização automática, conferir o destino público `MRsRIQUE/saysell-releases` na configuração do aplicativo e testar o fluxo completo de uma versão anterior para a nova. Não incluir credenciais de publicação no aplicativo.
- [ ] Revisar o conteúdo dos artefatos e das notas públicas. Não publicar código-fonte proprietário avulso, credenciais, arquivos `.env`, chaves, logs com dados privados, relatórios de auditoria interna ou diretórios de trabalho.
- [ ] Registrar nas notas da release se o instalador possui assinatura Authenticode verificada. Na ausência de assinatura, informar isso claramente.

## Arquivos da release

- [ ] Anexar o instalador Windows `.exe` verificado.
- [ ] Anexar o `latest.yml` e os `.blockmap` correspondentes, quando gerados e exigidos pela configuração de empacotamento/atualização.
- [ ] Usar arquivos produzidos pelo mesmo build, preservando nomes e referências. Conferir versão, tamanho e hashes nos metadados.
- [ ] Disponibilizar checksums dos artefatos para conferência de integridade, deixando claro que eles não substituem assinatura nem protegem contra um publicador comprometido.
- [ ] Conferir todos os Assets e as notas antes de tornar a release pública. Não substituir silenciosamente os arquivos de uma versão já distribuída.

## Depois de publicar

- [ ] Conferir os downloads públicos sem autenticação e comparar os arquivos baixados com os artefatos verificados.
- [ ] Testar novamente a instalação e, quando configurada, a atualização automática com os arquivos efetivamente publicados.
- [ ] Somente anunciar os recursos e testes que foram confirmados. Se houver falha, interromper a divulgação e preparar uma nova versão corrigida.

Referências técnicas: [atualizações com electron-builder](https://www.electron.build/docs/features/auto-update/) e [configuração de publicação](https://www.electron.build/publish/).
