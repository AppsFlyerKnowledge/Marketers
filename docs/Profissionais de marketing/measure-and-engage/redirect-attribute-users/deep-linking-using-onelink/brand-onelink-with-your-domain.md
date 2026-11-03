---
title: Coloque sua marca no domínio do OneLink
metadata:
  keywords:
    - Marketers
    - cname
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-08-26T09:00:09Z'
  edited_at: '2026-08-19T00:33:15Z'
  id: 360002329137
  locale: pt
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/pt/articles/360002329137
---
> **At a glance:** **Resumo:** Anunciantes que usam links do OneLink podem colocar o nome da marca em seu domínio. Isso melhora a performance da campanha e aumenta a exposição da marca.

![Branded_1__3_.jpg](https://files.readme.io/20d0a59aa3e896960c9a0faaacad51a58e314073368452e07a7507e0770ca817-30192959736465.png)

## Branded domains

* Branded domains são usados para marcar links de atribuição com o nome da sua empresa e com o seu domínio. Por exemplo, como vimos na imagem anterior:
  * OneLink: abcdef.onelink.me
  * Marca abcdef.com
  * Subdomínio: um aplicativo, por exemplo
  * Branded domains implementados usando o domínio completo, com o link de atribuição sendo clique.abcdef.com
* Branded domains melhoram a performance da campanha, pois:
  * Aumentam a confiança: capitalize sua marca, garanta uma identidade consistente, remova o atrito das jornadas do usuário e melhore as taxas de CTR.
  * Permitem que você faça deep linking usando sua marca.
  * São simples de implementar e se comportam da mesma forma que OneLinks.
  * Promovem o reconhecimento da marca: sua marca se torna a cara das suas campanhas, ao contrário do que acontece com links genéricos.
  * Ative e-mails para evitar que eles sejam sinalizados como spam, pois o link pode não corresponder ao e-mail do remetente.
  * Branded domains estão incluídos nos <Anchor target="_blank" href="/marketers/pt/docs/account-management-plans-payments-and-billing">planos de assinatura</Anchor> pagos da AppsFlyer.

### Princípios de implementação

Os branded domains são implementados associando um domínio completo definido no seu Domain Name System (DNS) com um subdomínio OneLink (o destino CNAME da AppsFlyer). Isso é feito usando as configurações padrão no seu DNS e configurando um branded domain na AppsFlyer. Além disso, você precisará fazer algumas pequenas alterações no seu aplicativo para que ele seja compatível com os branded domains.

Você precisará da ajuda do administrador do DNS, que costuma ser um membro da sua equipe de TI ou o provedor de hospedagem do DNS e o desenvolvedor do aplicativo.

Múltiplos domínios podem ser associados a um único subdomínio do OneLink. Isso significa que você pode ter várias marcas que usam o mesmo subdomínio do OneLink.

### Configurando branded domains

Complete a lista de ações abaixo para configurar um branded domain.

|  | Responsabilidade | Ação | Observações |
| --- | --- | --- | --- |
| 1 | Profissional de marketing auxiliado pelo administrador do DNS | [Configurar um branded link na AppsFlyer](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer) | O administrador do DNS, que costuma ser um membro da sua equipe de TI ou o provedor de hospedagem do DNS, precisa configurar o domínio completo (também conhecido como host) e definir um registro CNAME conforme descrito no processo. |
| 2 | Desenvolvedor | [Configurar branded domains no aplicativo](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app) | Faça pequenas alterações no código do aplicativo. |
| 3 | Marketer | [Usar e testar branded domains](/docs/brand-onelink-with-your-domain#using-and-testing-branded-domains) |  |
| Conforme necessário | Marketer | [Editar e excluir branded domains](/docs/brand-onelink-with-your-domain#editing-and-deleting-branded-domains) |  |

### Procedimentos

<div id="set-up-a-branded-domain-in-appsflyer" />

<Accordion title="Configurar um branded domain na AppsFlyer">

A configuração de um branded domain consiste em associar um conjunto de domínio completo no DNS a um subdomínio OneLink na AppsFlyer, conforme descrito na imagem a seguir.

**Branded domain que direciona para servidores da AppsFlyer**

![](https://files.readme.io/b22525d9f653c3897f39f02a7beded3ad5c42d74a5487458f2ed720a20351e03-45231892701969.png)

**Antes de começar:**

* Escolha um nome de domínio completo, por exemplo, app.abcdef.com, em que  
  abcdef.com é a sua marca. O subdomínio (o aplicativo, por exemplo) também pode ser personalizado.
* Solicite que o administrador do DNS crie o domínio completo (também conhecido como host).
* Solicite que o administrador do DNS defina um registro CNAME de uma forma que o domínio  
  completo (branded domain) aponte para a URL especificada (também conhecido como host da AppsFlyer).  
  Isso está ilustrado na imagem de branded domain que aponta para os servidores da AppsFlyer (acima).

Para mapear seu domínio completo para um subdomínio do OneLink:

1. Na AppsFlyer, clique em **Engajamento** > **Branded domains**.
2. Clique **+ Novo branded domain**.
3. No campo **Branded domain**, insira seu domínio completo conforme definido no DNS. Por exemplo, **clique.abcdef.com**. Observação: não coloque um ponto após o domínio.
4. Selecione o subdomínio do OneLink na lista exibida. Se não houver lista,  
   você precisa criar um template do OneLink, que fornecerá um  
   subdomínio padrão.
5. Clique em **Próximo**.
6. Defina um registro CNAME:
   * Se o seu domínio estiver apontado corretamente para o CNAME da AppsFlyer,  
     a mensagem "CNAME da AppsFlyer encontrado" é exibida.
   * Se um CNAME não for encontrado, copie o destino CNAME da AppsFlyer e envie-o ao seu administrador do DNS para garantir que seus pontos de domínio completos sejam mapeados no destino. O administrador do DNS deve mapear seu domínio completo para um destino CNAME da AppsFlyer. Caso contrário, o branded domain é criado, mas não funciona.

     > 📘 **Note**
     >
     > **Atenção**
     >
     > O registro CNAME deve ser mapeado dentro de um período de 7 dias, começando na data de criação do branded domain e terminando na data especificada na caixa de diálogo de confirmação.  
     > Se o registro CNAME não for mapeado na data especificada, você deverá  
     > [renovar o período de 7 dias](#renove-o-período-de-7-dias-para-mapear-o-registro-cname).

7. Clique em **Concluído**. Agora você pode criar novos links baseados no template do OneLink com seu branded domain.

   > 📘 **Note**
   >
   > **Caraterística**
   >
   > * Se você já criou links com base no seu template OneLink sem o branded domain, eles ainda funcionam.
   > * Pode levar até 24 horas para que um novo branded domain comece a funcionar.


#### Renove o período de 7 dias para mapear o registro CNAME

O novo branded domain não funcionará se o registro CNAME do seu domínio completo não for mapeado para a AppsFlyer em até 7 dias após sua criação.

> 📘 **Note**
>
> **Problema**
>
> Se o registro foi mapeado após o período de 7 dias expirar, você ainda precisará renovar o período de 7 dias para que o novo branded domain funcione.

**Para renovar o período de 7 dias:**

1. Na AppsFlyer, no menu lateral, selecione **Engajamento** > **Branded domains**.
2. Acesse o branded domain que ainda não foi mapeado para a AppsFlyer, indicado pelo ícone de aviso (![alert.png](https://files.readme.io/7df53739ca5c629ec0bda789563f59717da9699986222705228f57e0d947c8de-30192946335761.png)).
3. Clique no ícone de atualização (<Image alt="refresh.png" src="https://files.readme.io/052b47c423612c1b0549f37ed6394373d37f28331e09f4c709601a7e5473bf2b-30192959741585.png" width="18px" />) para renovar o período de 7 dias.

> 📘 **Note**
>
> **Nota**
>
> Você pode excluir o branded domain clicando no ícone Excluir (<Image alt="delete-subdomain.png" src="https://files.readme.io/0029cc63db331d998182d46a63f9da9856de9b2351abd5b2d87fb2b47ae853c2-30192959748241.png" width="16px" />) se você decidir não renovar o período de 7 dias. Somente branded doamins que ainda não foram mapeados para a AppsFlyer podem ser excluídos.

#### Certificado SSL personalizado (opcional)

O SSL gerenciado pela AppsFlyer é a opção padrão e recomendada para a maioria dos clientes e não requer nenhuma ação adicional, pois a AppsFlyer lida automaticamente com a emissão e renovação do certificado. Se houver requisitos específicos de segurança ou compliance, você pode usar sua própria autoridade certificadora (certificado SSL personalizado) em vez do SSL gerenciado pela AppsFlyer. Se você escolher essa opção, será responsável por emitir, fazer o upload, manter e renovar o certificado. Se o certificado expirar e não for renovado a tempo, o serviço poderá ser interrompido.

**Para usar um certificado SSL personalizado:**

1. [Crie o branded domain](/docs/brand-onelink-with-your-domain#configurando-branded-domains).
2. Na AppsFlyer, em **Engajamento** > **Branded domains**, passe o cursor sobre o domínio desejado e selecione o ícone "Certificado SSL personalizado".

   <Image alt="Ícone de certificado SSL Newest minimal.png" src="https://files.readme.io/8b22a41fd755a3f36e8eaf4a869b107661894d81504bbfb44e1fc728b9b06751-45231876708497.png" width="1044px" />
3. Preencha o formulário com as informações do certificado.

   <Image alt="preencha o formulário para gerar o arquivo CSR file.png" src="https://files.readme.io/4327a4da0cbcc6243c9bbdbec21fe4f91d7fe701ccbffca99e629a5eadd248e8-45231876709649.png" width="722px" />
4. Clique em **Baixar CSR** para fazer download de uma cópia do formulário que você acabou de preencher. <Image alt="Download do arquivo CSR.png" src="https://files.readme.io/9a560d19e38593fbc379efc6bdb1e636e1fa34f894dca4b46a23be30019127dd-45231892701585.png" width="254px" />
5. Forneça o arquivo CSR que você acabou de baixar para a autoridade certificadora de sua escolha.
6. Assim que você receber seu novo certificado SSL, faça o upload novamente na AppsFlyer.

<Image alt="Fazer upload do novo certificado SSL para o AF.png" src="https://files.readme.io/b22525d9f653c3897f39f02a7beded3ad5c42d74a5487458f2ed720a20351e03-45231892701969.png" width="811px" />

> 📘 **Note**
>
> **Nota**
>
> Os certificados SSL têm prazo de validade. Você é responsável por renovar e fazer upload do certificado atualizado na AppsFlyer antes que o atual expire.

</Accordion>

<div id="set-up-branded-domains-in-the-app" />

<Accordion title="Configurar branded domains no aplicativo">

* Use as seguintes versões do SDK:
  * Android versão 4.10.1 e posterior
  * iOS versão 4.10.1 e posterior
  * O referral de convite de usuário (convide um amigo) requer o SDK V5.2.0 e posterior para iOS e Android

**Considerações de implementação dos branded domains do SDK**

* Quando o deep linking é feito usando branded domains, o SDK da AppsFlyer não consegue obter dados de conversão para instalações e deep linking.
* Para solucionar isso, o desenvolvedor usa as `setOneLinkCustomDomain` e `oneLinkCustomDomains` APIs do SDK para Android e iOS, respectivamente.
* Essas APIs consultam o branded link, obtendo o OneLink para o qual ele está mapeado e completando-o.

<Tabs>
<Tab title="Android iOS">

Certifique-se de atualizar o <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#adding-app-link-intent-filter-to-main-activity">intent-filter</Anchor> do manifesto para incluir o branded domain configurando o android:host.

Use essa API antes de inicializar o SDK na <Anchor target="_blank" href="https://developer.android.com/reference/android/app/Application">classe de aplicativos globais do Android.</Anchor>

**Exemplo**

```java
public class AFApplication extends Application {\n\n    @Override\n    public void onCreate() {\n    super.onCreate();\n      \n      // Set branded link domain. Não inclua https:// como parte do domínio. 
      AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com");
      AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionListener, this);
      AppsFlyerLib.getInstance().start(this, AF_DEV_KEY);

    }
}
```

Caso você tenha vários branded domains, passe todos eles para a API para garantir que você sempre receberá os dados de conversão e poderá criar um deep link para o aplicativo.

**Exemplo**

```java
AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com", 
                                                        "click.greatapp.com", 
                                                        "deals.greatapp.com");
```

</Tab>

<Tab title="Exemplo">

**Para associar domínios para Universal Links do iOS:**

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#enabling-associated-domains">Configure</Anchor> o **domínio/subdomínio do OneLink** como um domínio associado no Xcode.
* Configure o **branded domain** como um <Anchor target="_blank" href="https://developer.apple.com/documentation/security/password_autofill/setting_up_an_app_s_associated_domains">domínio associado</Anchor> no Xcode.
* Configure o link da marca para poder obter dados de conversão. Para mais instruções, clique na linguagem de programação relevante abaixo.

<Tabs>
<Tab title="Objetivo c">

Use a API no AppDelegate.m, dentro do método didFinishLaunchingWithOptions:

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    /** INICIALIZAÇÃO DO APPSFLYER **/
    [AppsFlyerLib shared].appsFlyerDevKey = @"SED_DEV_KEY";
    [AppsFlyerLib shared].appleAppID = @"123456789";
    [AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com"];
    //...
    //...
  }
```

Caso você tenha vários branded domains, passe todos eles para a API para garantir que você sempre receberá os dados de conversão e poderá criar um deep link para o aplicativo.

**Exemplo**

```objectivec
[AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com", @"click.greatapp.com"];
```

</Tab>

<Tab title="Swift">

A API deve ser usada no AppDelegate.swift, dentro do método didFinishLaunchingWithOptions:

```swift
   func application(_ application: UIApplication, didFinishLaunchingWithOptions 
        launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {
          AppsFlyerLib.shared().appsFlyerDevKey = "6CQi4Be6Zs9oNLsCusPbUL"
          AppsFlyerLib.shared().appleAppID = "340954504"
          AppsFlyerLib.shared().oneLinkCustomDomains = ["example.com"]
          //...
          //...
   }
```

Se você tiver vários branded domains, poderá passá-los para a API como um conjunto de strings. Isso garante que, independentemente do branded domain usado, você sempre receberá os dados de conversão e poderá criar um deep link para o aplicativo.

**Exemplo**

```objectivec
AppsFlyerLib.shared().oneLinkCustomDomains = ["promotion.greatapp.com", "click.greatapp.com"]
```

</Tab>
</Tabs>

</Tab>
</Tabs>

</Accordion>

<div id="using-and-testing-branded-domains" />

<Accordion title="Usar e testar branded domains">

**Pré-requisitos**:

Antes de usar e testar branded domains, complete as etapas no [workflow de branded domains](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app).

**Para criar e testar branded domains:**

1. <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crie-um-link-do-onelink">Crie um link do OneLink</Anchor> usando o template do OneLink mapeado para o branded domain.
2. Copie o link de atribuição personalizado para um editor de texto.
3. O link de atribuição personalizado é composto por um subdomínio do OneLink, OneLink ID e Link ID personalizado. Substitua o subdomínio do OneLink pelo domínio completo do branded domain. Exemplo:

| Link de atribuição personalizado | Branded domain |
| --- | --- |
| **abcdef.onelink.me**/A1bc/dc1234ef | **clique.abcdef.com**/A1bc/dc1234ef |

4. Use o branded link para <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">testar instalações e deep linking</Anchor>.
5. Se você usa relatórios de dados brutos como parte do teste, o campo de URL original será preenchido pelos branded links.

</Accordion>

<div id="editing-verifying-and-deleting-branded-domains" />

<Accordion title="Edição, verificação e exclusão de branded domains">

#### **Para editar um mapeamento do branded domain**

Você pode alterar o mapeamento de um domínio completo existente para um subdomínio diferente do OneLink. Não há necessidade de configurar um CNAME.

1. Na AppsFlyer, no menu lateral, selecione **Engajamento** > **Branded domains**.
2. Vá para o branded domain que você deseja editar.
3. Clique no ícone Editar (<Image alt="edit-subdomain.png" src="https://files.readme.io/ffe3da7d1c065a806a44c607bcf1231e06bf7e7478ca50187e57cb5ab876ae72-30192959751185.png" width="17px" />).
4. Selecione o novo subdomínio no OneLink.
5. Clique em **Próximo.** Não há necessidade de configurar um CNAME.
6. Clique em **Concluído**.

> 🚧 **Important**
>
> **Aviso**
>
> Modificar os branded domains de campanhas ativas pode alterar ou desativar a funcionalidade do link.

#### **Verifique um mapeamento de branded domain**

Depois de alterar o subdomínio do OneLink mapeado para o seu branded domain, verifique se ele está mapeado corretamente:

1. Na AppsFlyer, no menu lateral, selecione **Engajamento** > **Branded domains**.
2. Vá para o branded domain que você deseja verificar.
3. Clique no ícone Verificar (<Image alt="verify-2.png" src="https://files.readme.io/4ac94a535e9101b3e727351f67df8917c0870d6ede8ec963de8c5528893b8e2b-30192946342929.png" width="17px" />).

> 📘 **Note**
>
> **Nota**
>
> Se a verificação falhar porque o registro CNAME ainda não foi mapeado, você terá um prazo de até 7 dias para fazer isso, terminando na data especificada na caixa de diálogo.
> Se o registro CNAME não for mapeado até a data especificada, você deverá renovar o período de 7 dias.

#### **O registro CNAME do domínio não leva para a AppsFlyer**

Mudar seu registro CNAME, de uma forma que ele deixe de direcionar para a AppsFlyer, resultará na exclusão do domínio personalizado na AppsFlyer.

#### **Excluir um mapeamento de branded domain:**

Para excluir um branded domain, entre em contato com seu CSM da AppsFlyer ou envie um e-mail para hello@appsflyer.com.

</Accordion>

## Solução de problemas, características e limitações

<div id="troubleshooting" />

<Accordion title="Solução de problemas">

| Problema | Causa/solução |
| --- | --- |
| O branded domain não pôde ser mapeado para um template do OneLink | <ul><li>**Nome inválido:** Ao mapear um branded domain para um template OneLink, a AppsFlyer tenta verificar se o link de marca tem um nome de domínio válido. Um nome de domínio válido tem o formato clique.abdef.com</li><li>**O branded domain já está mapeado:** Um domínio completo só pode ser mapeado uma vez.</li></ul> |
| O branded domain não está fazendo o deep linking para o aplicativo | <ul><li>[Verifique se o branded domain é operacional](#verifique-um-mapeamento-de-branded-domain)</li><li>**Verificar CNAME**: Certifique-se de que um registro CNAME aponte do seu domínio para a AppsFlyer.</li><li>**Verifique a configuração de deep linking para o template do OneLink:** É possível que haja um problema com as configurações de deep linking do OneLink. Certifique-se de configurar o deep linking com o OneLink.</li><li>**Mapeamento do OneLink alterado:** Você pode editar o branded domain e mapeá-lo para um OneLink diferente. Se o OneLink recém-mapeado tiver configurações diferentes ou não houver configurações de deep linking, pode ser que o deep linking não funcione.</li></ul> |
| Nenhuma instalação mensurada a partir de branded domains | <ul><li>**Verifique as configurações do template do OneLink:** Certifique-se de que o subdomínio do OneLink usado para mapear o branded domain esteja associado aos aplicativos corretos.</li><li>**Subdomínio do OneLink alterado:** Se você mapear um branded domain para um template do OneLink e o subdomínio do OneLink mudar, isso poderá afetar a atribuição.</li><li>**Garantir a implementação:** Da setOneLinkCustomDomain API no aplicativo.</li></ul> |
| Nenhum reengajamento registrado nos branded domains | Certifique-se de que os seguintes itens estejam ativos e configurados:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/onelink-guide#configurando-o-onelink">Configure o deep linking usando o OneLink</Anchor>.</li><li>O aplicativo faz uso do SDK dedicado da [setOneLinkCustomDomain API](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer).</li><li><Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide#retargeting-settings">O retargeting deve estar ativado nas configurações do aplicativo</Anchor>.</li></ul> |
| Durante a configuração do branded domain, a mensagem **Este domínio não existe** é exibida | <ol><li>Entre em contato com seu administrador do DNS e peça que ele investigue.</li><li>Aguarde o administrador do DNS confirmar se o domínio foi registrado.</li><li>Clique em **Verificar novamente**.</li></ol> |
| Durante a configuração do branded domain, a mensagem **CNAME da AppsFlyer não encontrado** é exibida | <ol><li>Peça para o administrador do DNS configurar um registro CNAME de uma forma que o domínio completo (branded domain) direcione para a URL especificada (também conhecida como host da AppsFlyer). Veja o exemplo da imagem do branded link que aponta para servidores da AppsFlyer nessa seção.</li><li>Aguarde o administrador do DNS confirmar se o CNAME está ativo.</li></ol> |
| Mensagem “**você foi bloqueado**” ao carregar uma página de branded domain | Os branded domains não incluem o template ou quaisquer parâmetros. Ao usar um branded domain, você deve adicionar o template ou os parâmetros ao final da URL do domínio.<br /><br />Por exemplo, se “clique.abcdef.com” for seu branded domain, usar apenas “**clique.abcdef.com**” levará a uma mensagem avisando **que você foi bloqueado**.<br /><br />Você deve adicionar os parâmetros ou templates ao final. Por exemplo, clique.abcdef.com **/A1bc/dc1234ef** |
| Erro **err\_cert\_authority\_invalid** ao carregar uma página de branded domain | Esse erro indica que seu branded domain não possui um certificado HTTPS válido porque a autoridade certificadora não é reconhecida. Como a AppsFlyer certifica seus branded domains com o Let's Encrypt, o erro provavelmente ocorre porque o Let's Encrypt não foi reconhecido como uma autoridade certificadora (AC) válida de acordo com os registros DNS CAA (autorização da AC) do seu domínio.<br /><br />**Solução**<br />Por favor, siga estas etapas:<ol><li>Determine se o seu domínio reconhece o Let's Encrypt como AC usando serviços como <Anchor target="_blank" href="https://www.entrust.com/resources/certificate-solutions/tools/caa-lookup">este</Anchor>.</li><li>Peça aos administradores do sistema para atualizarem os registros CAA do seu domínio para incluir Let's Encrypt como uma AC autorizada.</li></ol> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Sim ✓ / Não **x** | Observações |
| --- | --- | --- |
| Acesso do usuário à conta | ✓ |  |
| Acesso de ad network | **X** |  |
| Acesso de agência | **X** | As agências não podem criar branded domains (ou links do OneLink). |
| Transparência da agência | **X** |  |
| Moeda específica do aplicativo | N/D |  |
| Fuso horário específico do aplicativo | N/D |  |
| Disponibilidade de branded domains | N/D | Os branded domains estão disponíveis apenas para os planos pagos elegíveis. Se o seu plano de assinatura expirar ou for cancelado, o acesso aos branded domains será removido e os links que usam seus branded domains deixarão de funcionar. |
| Limitação de caracteres | N/D | Ao inserir seu branded domain, o último caractere não pode ser um ponto final ("."). |
| Atualização de dados | N/D |  |
| Dados históricos | ✓ |  |
| HTTP | **X** | O protocolo HTTP não é compatível com links personalizados. Você deve usar HTTPS. |
| Dados não orgânicos | ✓ |  |
| Dados orgânicos | ✓ |  |
| Limitação de taxa | ✓ | Certificados SSL/HTTP dos branded domains são organizados pela AppsFlyer usando <Anchor target="_blank" href="https://letsencrypt.org/">Let's Encrypt</Anchor>, com uma taxa limite de 50 novos certificados por semana por domínio. |
| Limitações de tamanho | N/D |  |
| Renovação de certificado SSL/HTTP | ✓ | Seus certificados SSL/HTTP gerenciados pela AppsFlyer são renovados automaticamente. |

</Accordion>

<div data-zendesk-anchors="h_01HFM51V4PE53FQAED68V8Q834=branded-domains principles-of-implementation=princ%C3%ADpios-de-implementa%C3%A7%C3%A3o h_01HFM51V4PPJXMCSV5ZVDPT49M=princ%C3%ADpios-de-implementa%C3%A7%C3%A3o setting-up-branded-domains=configurando-branded-domains h_01HFM51V4PH58ZA4ZXHP5J6K2W=configurando-branded-domains procedures=procedimentos h_01HFM51V4PWWX7TBCHFMPR3QVB=procedimentos h_01HQ5CWGQNRBXQ6QQDADV7XCQP=set-up-a-branded-domain-in-appsflyer renew-the-day=renove-o-per%C3%ADodo-de-7-dias-para-mapear-o-registro-cname h_01HQ5CWGQNQJJ1CXDKTGZ8N9ZE=renove-o-per%C3%ADodo-de-7-dias-para-mapear-o-registro-cname custom-ssl-certificate=certificado-ssl-personalizado-opcional h_01KM0E8VHARA2JRAR2H37QM91Y=certificado-ssl-personalizado-opcional h_01HFM51V4PP0NQHVHTKB86250R=set-up-branded-domains-in-the-app h_01HFM51V4PN0FPEDNAF0Q1QS8P=using-and-testing-branded-domains h_01HQ5CWGQPZ6MEFA6MDTHYHCSA=editing-verifying-and-deleting-branded-domains edit-a-branded-domain-mapping=para-editar-um-mapeamento-do-branded-domain h_01HQ5FJZD6QMNFA45Z2C7CA3ST=para-editar-um-mapeamento-do-branded-domain verify-a-branded-domain-mapping=verifique-um-mapeamento-de-branded-domain h_01HQ5FK5XJNZ1EABJA66RMYBCN=verifique-um-mapeamento-de-branded-domain domain-cname-record-no-longer-pointing-to-appsflyer=o-registro-cname-do-dom%C3%ADnio-n%C3%A3o-leva-para-a-appsflyer h_01JSHFECXS00M6BXH8168ZWJE5=o-registro-cname-do-dom%C3%ADnio-n%C3%A3o-leva-para-a-appsflyer delete-a-branded-domain-mapping=excluir-um-mapeamento-de-branded-domain h_01JSHF5RMXXFJTXC246KKAQBSS=excluir-um-mapeamento-de-branded-domain troubleshooting-traits-and-limitations=solu%C3%A7%C3%A3o-de-problemas-caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HFM51V4PH4YM13DVXENRWF2E=solu%C3%A7%C3%A3o-de-problemas-caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HFM51V4PJNHZTD97X75WPN98=troubleshooting h_01HFM51V4QQ2TZQMJ2ATNDG91F=traits-and-limitations" />
