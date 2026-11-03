---
title: Aplique configurações a vários aplicativos de uma vez
deprecated: false
hidden: false
metadata:
  keywords:
    - App Settings
    - Advertisers
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Platform essentials
    - Agencies
    - pm-guy-riesenberg
  created_at: '2026-09-09T09:10:13Z'
  edited_at: '2026-09-24T00:19:32Z'
  id: 50696362899089
  locale: pt
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/pt/articles/50696362899089
---
> **At a glance:** Aplique a mesma alteração de configuração a vários aplicativos de uma vez, em vez de repeti-la para cada aplicativo individualmente.

## Sobre as configurações em massa de aplicativos

Agora você pode aplicar as mesmas alterações de configuração a vários aplicativos de uma só vez usando as configurações em massa de aplicativos na página Configurações do aplicativo. Isso permite que você faça uma alteração uma vez e a aplique a outros aplicativos elegíveis em uma única operação.

Para acessar as Configurações do Aplicativo, no menu lateral, selecione **Settings** > **App Settings**. Ou, em **My Apps**, selecione um aplicativo e abra as Configurações do Aplicativo.

## Aplique uma configuração a vários aplicativos

> 📘 **Importante!**
>
> Um aplicativo é elegível para uma alteração em massa se a configuração se aplicar à plataforma desse aplicativo, se ele ainda não tiver o valor que você está aplicando, se qualquer pré-requisito necessário já estiver em vigor e se você tiver acesso de gerenciamento às Configurações do aplicativo. Consulte **Características e limitações** abaixo para ver os critérios completos de cada configuração.

**Para aplicar uma alteração de configuração a vários aplicativos:**

1. Abra as Configurações do aplicativo cujo ajuste você quer alterar e altere um ajuste (botão de alternância, menu suspenso ou controle deslizante).

   <Image alt="Screenshot 2026-09-16 at 14.31.44.png" src="https://files.readme.io/8a1abce58e1e8da4af5899e2e03a2a7fe9e6e9b8e9a04c240585bfd3e7934126-50944987863825.png" width="2557px" />
2. Ao lado do campo alterado, clique em **Aplicar a aplicativos adicionais**.

   <Image alt="aap.png" src="https://files.readme.io/0f2144ca43c6db7ffe9967df5c2b2f2fe3e8cffdbefa77167ed9262a61511774-50945027652113.png" width="612px" />
3. Pesquise pelo nome do aplicativo ou pelo ID do aplicativo e selecione os aplicativos que devem receber a mesma alteração. Os aplicativos que não são compatíveis com essa alteração continuam visíveis, mas aparecem acinzentados. Passe o cursor sobre um deles para ver o motivo.

   <Image alt="Screenshot 2026-09-16 at 14.32.32.png" src="https://files.readme.io/95c79ce8c176e4a0836661a119ca12b1268b8874181d4fd78c96113e5339d6c9-50945018039953.png" width="1304px" />
4. Clique fora da lista para fechá-la e confirmar sua seleção. O botão **Aplicar a aplicativos adicionais** é substituído por um selo que mostra o número de aplicativos selecionados; clique nele a qualquer momento para alterar sua seleção.

   <Image alt="ssa.png" src="https://files.readme.io/b93174999053cdbbf5591eb215e6cd10becbd2d1bcb699ff286a8b1523f8a8f0-50944987865361.png" width="1238px" />
5. Repita essas etapas para quantas configurações forem necessárias.
6. Na parte inferior da página, clique em **Salvar alterações** (se você não selecionou nenhum aplicativo adicional) ou em **Revisar & salvar** (depois que você incluir aplicativos em uma alteração em massa). Qualquer um dos botões mostra o número total de alterações entre parênteses.

   <Image alt="Screenshot 2026-09-16 at 14.33.32.png" src="https://files.readme.io/6dfb050b984932023455af9022364b37534af276d7bb117ddb05ad0fc25d936c-50945018041489.png" width="2269px" />
7. Se você incluiu aplicativos adicionais, revise os valores anteriores e posteriores de cada aplicativo na tela **Revisar antes de salvar**. O valor atual de cada aplicativo é usado como base. Você pode remover qualquer alteração do lote antes de confirmar.

   <Image alt="Screenshot 2026-09-16 at 14.33.38.png" src="https://files.readme.io/c22f67575fc8ac9cbd868c923b5addfe8c70529ee1183fa7231f080d1b54d18c-50945018042385.png" width="1286px" />
8. Clique em **Confirmar & salvar**. Isso salva o aplicativo em que você começou junto com todos os aplicativos adicionais do lote, em uma única operação.

> 📘 **Importante!**
>
> Para Aggregated Advanced Privacy, você sempre verá uma etapa de confirmação antes que a alteração entre em vigor. Para a atribuição de reengajamento, você verá essa etapa de confirmação apenas ao aplicar a alteração em massa.

> 🚧 **Importante:**
>
> Todos os aplicativos do lote são atualizados juntos, de uma só vez. O resultado será um destes:
>
> 1. Sucesso, e todos os aplicativos são atualizados.
> 2. Falha, e nenhum aplicativo é atualizado.
>    1. Se o salvamento falhar, você poderá tentar novamente.

## Especificações e limitações

| Caraterística | Descrição |
| --- | --- |
| <span id="supported-settings-ships-first"></span>Configurações com suporte (disponíveis agora) | <ul><li>Privacidade avançada agregada (somente iOS)</li><li>Atribuição de reengajamento (iOS, Android)</li><li>Tempo mínimo entre conversões de reengajamento (iOS, Android)</li><li>Atribuição de SEO (iOS, Android para ativar; qualquer plataforma para desativar)</li><li>Mascarar endereços IP (todas as plataformas, exceto web)</li><li>Evento de usuário fidelizado (iOS, Android)</li><li>Tempo mínimo entre sessões (iOS, Android)</li></ul> |
| <span id="supported-settings-coming-soon"></span>Configurações compatíveis (Em breve) | Essas configurações ainda não são compatíveis com alterações em massa. Em breve você poderá<ul><li>Janela de reatribuição (mobile, em dias; web, em segundos — não combinados em uma única ação)</li><li>Modelagem probabilística (todas as plataformas; exige que o fingerprinting já esteja ativado)</li><li>Fuso horário (todas as plataformas)</li><li>Moeda (todas as plataformas)</li><li>Mensuração de desinstalação (o iOS exige que um certificado P12 já tenha sido carregado; o Android exige que o Firebase já esteja configurado)</li><li>Detecção de reinstalação (iOS, Android)</li></ul> |
| <span id="not-supported"></span>Não suportado | Autenticação do SDK (chave de desenvolvedor), país da loja de aplicativos, alterar nome do aplicativo, upload do certificado de desinstalação do iOS, ID do projeto do Firebase e configurações de assentos de agência e parceiro. |
| <span id="why-an-app-might-be-grayed-out"></span>Por que um aplicativo pode aparecer acinzentado | Um aplicativo em cinza não é elegível para essa alteração nesta tentativa específica. Um dos seguintes motivos será exibido:<ul><li>**Incompatibilidade de plataforma:** a configuração não existe na plataforma desse aplicativo.</li><li>**Já definido:** o aplicativo já tem o valor que você está aplicando.</li><li>**Pré-requisito ausente:** por exemplo, o modelo probabilístico exige que o fingerprinting já esteja ativado.</li><li>**Período de espera:** o fuso horário não pode ser alterado novamente em até dois dias após uma alteração anterior. A dica de ferramenta mostra a data em que ficará disponível novamente.</li><li>**Sem permissão:** você não tem acesso de gerenciamento às Configurações do aplicativo para esse aplicativo.</li></ul> |
| <span id="limits"></span>Limites | Não existe um limite prático para o número de aplicativos que você pode incluir em uma alteração em massa. |

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/app-settings">Configurações do aplicativo</Anchor>

<div data-zendesk-anchors="about-bulk-app-settings=sobre-as-configura%C3%A7%C3%B5es-em-massa-de-aplicativos h_01N1A2B3C4D5E6F7G8H9J0K1L2=sobre-as-configura%C3%A7%C3%B5es-em-massa-de-aplicativos apply-a-setting-to-multiple-apps=aplique-uma-configura%C3%A7%C3%A3o-a-v%C3%A1rios-aplicativos h_02N1A2B3C4D5E6F7G8H9J0K1L2=aplique-uma-configura%C3%A7%C3%A3o-a-v%C3%A1rios-aplicativos h_01M25MDHN4Q2TDAZHPGSXQFQKR=importante h_01M22PVGBQT0V9BSE1Y37V0KB8=importante-1 h_01M22PVGBQQAFHMR7XDYB2BMXN=importante-2 traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_03N1A2B3C4D5E6F7G8H9J0K1L2=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01M22PVGBQ8BZN09TZ2S4A70SW=consulte-tamb%C3%A9m" />
