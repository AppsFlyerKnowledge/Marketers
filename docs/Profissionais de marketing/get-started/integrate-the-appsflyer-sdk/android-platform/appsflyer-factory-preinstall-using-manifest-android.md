---
title: Pré-instalação de fábrica da AppsFlyer usando manifesto (Android)
metadata:
  keywords:
    - Android
    - Pre-Install
    - Attribution
    - Metrics
    - Advertisers
    - Agencies
    - af_pre_install_name
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2014-10-13T11:14:04Z'
  edited_at: '2026-08-19T00:12:45Z'
  id: 207032166
  locale: pt
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/pt/articles/207032166
---
> **Visão geral:** Atribuir instalações de aplicativos aos fabricantes de dispositivos para aplicativos adicionados aos dispositivos antes de saírem da fábrica. **Observação**: Ver <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#preload-campaigns">todos os outros métodos de atribuição de pré-carregamento</Anchor>.

![pre-install-intro-breakdown.png](https://files.readme.io/7932a58ca1cab28601110b0c0e8a11471e71174316bd5786689af288aac37ae7-49929278893585.png)

## Introdução

### O que é uma campanha de pré-instalação?

As campanhas de pré-instalação permitem que os proprietários de aplicativos alcancem vastos públicos sem terem de efetuar campanhas online.

Nas campanhas de pré-instalação, os proprietários de aplicativos podem solicitar aos fabricantes de dispositivos que pré-instalem seus aplicativos nos dispositivos antes de saírem da fábrica.

As campanhas de pré-instalação também podem ser uma colaboração com fontes de media de terceiros, que trabalham com vários fabricantes em nome dos proprietários de aplicativos.

> 🚧 **Importante!**
>
> A AppsFlyer conta uma instalação quando um aplicativo é iniciado pela primeira vez. Dessa forma, o número de pré-instalações apresentadas é o número de usuários que inicializam seu aplicativo e não o número de dispositivos que têm o aplicativo pré-instalado.

### Vantagens de registar instalações de campanhas de pré-instalação

Ao atribuir campanhas de pré-instalação, você pode medir o:

* número de usuários que inicializam seu aplicativo pré-instalado
* número de usuários de aplicativos que cada fabricante traz
* LTV de cada usuário e determinar qual o fabricante que traz os usuários mais valiosos

### Como posso medir as campanhas de pré-instalação?

Existem quatro formas de medir as campanhas de pré-instalação. Para mais informações, consulte a [seção Configuração](/docs/appsflyer-factory-preinstall-using-manifest-android#configuração) deste artigo.

### Visualizar dados de pré-instalação

As pré-instalações aparecem no painel da AppsFlyer sob a fonte de mídia atribuída, assim como qualquer outro evento de instalação. No entanto, o nome da sua campanha é sempre **Pré-instalação**.

> 📘 **Observação**
>
> Pode especificar diferentes nomes de campanha para pré-instalações com o [método da API do SDK](/docs/appsflyer-factory-preinstall-using-manifest-android#sdk-api-method).

> 📘 **Observação**
>
> A partir de 24 de maio de 2022:
>
> * Match\_type para campanhas de pré-instalação de fábrica é apresentado como `preload_conf` nos relatórios de dados brutos.
> * A AppsFlyer exibe em painéis de controle a ad network que impulsionou o pré-carregamento e as ad networks que contribuíram para o primeiro lançamento de aplicativos. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#preload-campaigns">campanhas de pré-carregamento</Anchor>.

## Configuração

Selecione um dos seguintes métodos para medir as campanhas de pré-instalação.

| Nome do método | Requer vários APKs? | Garante a atribuição de pré-instalação? | Requer ação por parte da fonte de mídia ou do fabricante? |
| --- | --- | --- | --- |
| Propriedades do sistema | Não | Sim | Sim |
| API do SDK | Sim | Não | Não |
| Nome no arquivo do manifesto | Sim | Não | Não |
| Trajetória | Não | Não | Sim |

<div id="system-properties-method-recommended" />

<Accordion title="Método das propriedades do sistema (recomendado)">

Utilizar a versão do SDK `V4.0+`.

Este método é recomendado porque é o mais robusto de todos; no entanto, considere que, para todas as instalações de aplicações subsequentes, a fonte de mídia de pré-instalação é sempre atribuída. Isto é independente do fato de a instalação ser nova ou ser uma reinstalação. 

O método das propriedades do sistema requer ações tanto do lado do programador como do lado do fabricante.

#### Desenvolvedor

É necessário fornecer o APK ao fabricante ou à fonte do suporte. O APK predefinido é fornecido. Este método não requer um APK separado.

Criar um arquivo chamado `pre_install.appsflyer`. No arquivo, adicione um par chave-valor:

`<package_name>=<media_source>`

Por exemplo:

`com.appsflyer.sampleapp=huawei`

**Para especificar parâmetros de pré-instalação adicionais:**

No arquivo **pre\_install.appsflyer**, passe os parâmetros adicionais no formato JSON. Por exemplo:

```json
com.appsflyer.sampleapp={"pid":"huawei", "c":"special_campaign","af_adset":"some_adset"}
```

> 🚧 **Importante!**
>
> Observe o seguinte comportamento ao usar esta opção:
>
> * Em dados brutos, defina Channel (Canal) como "Pre-install" (Pré-instalação)
> * Se o parâmetro `pid` não estiver presente no JSON, a fonte de mídia aparece como "Nenhum" nos dados brutos
> * Na configuração JSON, se o parâmetro `c` não estiver presente, o nome da campanha é definido como "Pré-instalação"
> * Se o JSON estiver mal formado, a cadeia de caracteres passada é tratada como o nome da fonte de mídia

Quando tiver o arquivo pre\_install.appsflyer, entregue-o à fonte de mídia ou ao fabricante junto com o APK.

#### Fabricante

O fabricante coloca o ***pre\_install.appsflyer*** num caminho de arquivo à sua escolha. As permissões do arquivo **pre\_install.appsflyer** devem ser definidas para 744.

O fabricante edita então o arquivo de propriedades do sistema para apontar para o arquivo ***pre\_install.appsflyer*** . Para fazer isso, o fabricante precisa adicionar um par chave-valor às propriedades do sistema.

> 📘 **Observação**
>
> São necessárias permissões de raiz para esta etapa. As permissões de raiz também são necessárias para testar a configuração de pré-instalação. Consulte a [seção Testes](/docs/appsflyer-factory-preinstall-using-manifest-android#testar-a-configuração-de-pré-instalação) para obter mais informações.

**Adicionar um par chave-valor às propriedades do sistema Android:**

```bash
adb shell su
setprop ro.appsflyer.preinstall.path /data/pre_install.appsflyer
```

Um método alternativo é obter o arquivo system-properties do sistema de arquivos android, editá-lo e enviá-lo de volta:

```bash
adb root
adb remount
adb pull /system/build.prop
echo ro.appsflyer.preinstall.path=/data/pre_install.appsflyer >> build.prop
adb push build.prop /system/build.prop
adb shell chmod 644 /system/build.prop
adb reboot
```

#### Vantagens

Não é necessário manter APKs diferentes para cada fonte de mídia ou fabricante. Não é necessário efetuar alterações e adicionar caminhos ao aplicativo no Google Play. Os fabricantes podem usar caminhos personalizados e não existem dependências entre vários aplicativos pré-instalados executados em diferentes dispositivos.

Este método garante a atribuição a campanhas de pré-instalação e fontes de mídia. Mesmo que um usuário atualize o aplicativo antes de o iniciar ou instale o aplicativo depois de clicar num anúncio, a pré-instalação continua a ser atribuída à fonte ou ao fabricante do suporte de pré-instalação.

#### Desvantagens

Alguma responsabilidade é transferida para a fonte ou o fabricante do suporte. Os desenvolvedores devem se certificar de que o fabricante ou a fonte de mídia toma as medidas necessárias. Além disso, este método pode ser um pouco mais difícil de testar para o programador de aplicativos.

</Accordion>

<div id="sdk-api-method" />

<Accordion title="Método da API do SDK">

O método da API do SDK fornece uma maneira nativa de especificar o nome do fabricante ou da fonte de mídia à qual a pré-instalação é atribuída.

Para usar este método, adicione a seguinte chamada de método na classe AFApplication antes de inicializar o SDK:

`setPreinstallAttribution(String mediaSource, String campaign, String siteId)`

#### Ao trabalhar com uma fonte de mídia

```java
AppsFlyerLib.getInstance().setPreinstallAttribution("MEDIA_SOURCE_NAME", "CAMPAIGN_NAME", "123"); AppsFlyerLib.getInstance().init(AF_DEV_KEY , conversionListener , getApplicationContext());
```

#### Ao trabalhar com um fabricante

```java
AppsFlyerLib.getInstance().setPreinstallAttribution(android.os. Build.MANUFACTURER, "CAMPAIGN_NAME", "123"); AppsFlyerLib.getInstance().init(AF_DEV_KEY , conversionListener , getApplicationContext());
```

> 📘 **Observação**
>
> * O parâmetro da fonte de mídia é obrigatório.
> * A propriedade `android.os. Build.MANUFACTURER` contém o nome do fabricante, tal como configurado pelo sistema operacional. O uso desta propriedade não garante que você obterá o nome do fabricante no mesmo formato em todos os dispositivos desse fabricante. Certifique-se de que esta propriedade contém o nome do fabricante, como previsto.
> * Os parâmetros `campaign` e `siteId` são facultativos, mas são exigidos pelo método `setPreinstallAttribution`. Se não quiser especificar `campaign` e `siteId`, passe null em ambos.

#### Vantagens

O método da API do SDK permite obter o nome do fabricante de forma programática. Independentemente do fabricante, o método SDK obtém o nome diretamente do dispositivo. Isto significa que pode manter um APK para todos os fabricantes com os quais colabora.

O método `setPreinstallAttribution` permite especificar o nome da campanha. Você pode separar cada fabricante ou fonte de mídia em campanhas diferentes, em vez de ter todas elas definidas na campanha "Pré-instalação".

#### Desvantagens

Se você estiver trabalhando diretamente com os fabricantes, terá de manter duas versões do seu APK, uma para os fabricantes e outra para o Google Play. Em ambos os casos, é necessário mais do que um APK.

Se estiver trabalhando com várias fontes de mídia que comunicam com o fabricante em seu nome, é necessário manter um APK separado para cada fonte de mídia.

Em alguns casos, a instalação pode não ser atribuída à fonte de mídia de pré-instalação:

* Se um usuário com um novo dispositivo atualizar o aplicativo pré-instalado diretamente a partir do Google Play sem o inicializar primeiro, a instalação é considerada orgânica.
* Se um usuário com um novo dispositivo atualizar o aplicativo a partir do Google Play depois de clicar num anúncio, a instalação é atribuída à fonte de mídia que apresenta o anúncio.

> 👍 **Dica**
>
> Você pode implementar a lógica no aplicativo para garantir que a instalação é contada como pré-instalação, mesmo que os cenários acima ocorram. Tanto o APK da Play Store como o APK destinado à pré-instalação devem conter essa lógica.
>
> **Exemplo:**
>
> * Você sabe que os aplicativos são pré-instalados nos dispositivos de um determinado fabricante e modelo. Estes dispositivos também estão funcionando com um determinado operador.
> * Quando o aplicativo é inicializado, é possível verificar estas condições. Se estas condições forem cumpridas, a instalação é registada como pré-instalação. Uma vez que a lógica também existe no APK da Play Store, a instalação é registrada como pré-instalação, mesmo que o usuário atualize o aplicativo antes de inicializá-lo.

</Accordion>

<div id="name-in-manifest-file-method" />

<Accordion title="Nome no método do arquivo de manifesto">

O nome no método de manifesto requer que você adicione uma etiqueta de metadados ao arquivo de manifesto do aplicativo. É necessário repetir esta etapa para cada fonte de mídia ou fabricante com que você trabalha.

Adicione uma tag de metadados antes da tag de fechamento do aplicativo:

```html Markup
...
    <meta-data android:name="AF_PRE_INSTALL_NAME" android:value="market_name"/>
  </application>
</manifest>
```

Quando o aplicativo é inicializado pela primeira vez, o SDK da AppsFlyer detecta esta tag de metadados no arquivo de manifesto e atribui a instalação de forma correspondente.

#### Vantagens

O nome no método de manifesto é considerado um método fácil para atribuir campanhas de pré-instalação. Só há uma tag a adicionar ao manifesto. Além disso, a fonte de mídia ou o fabricante não tem de fazer nada para permitir a medição da campanha.

#### Desvantagens

Uma vez que a tag de metadados especifica a fonte de mídia ou o nome do fabricante, é necessário manter diferentes conjuntos de APKs, um para cada fonte de mídia ou fabricante.

Em alguns casos, a instalação pode não ser atribuída à fonte de mídia de pré-instalação:

* Se um usuário com um novo dispositivo atualizar o aplicativo pré-instalado diretamente a partir do Google Play sem o inicializar primeiro, a instalação é considerada orgânica.
* Um usuário com um novo dispositivo instala o aplicativo a partir do Google Play depois de clicar num anúncio, a instalação é atribuída à fonte de mídia que apresenta o anúncio.

</Accordion>

<div id="pathway-method" />

<Accordion title="Método de caminho">

> 📘 **Observação**
>
> Compatível com a versão 4.5.0 ou posterior do SDK.

Este método requer que tanto o programador como o fabricante executem algumas ações no seu lado.

#### Desenvolvedor

O método de caminho possibilita especificar um caminho para um arquivo que contém o nome da fonte de mídia ou do fabricante. Há três etapas que devem ser concluídas:

1. Criar um arquivo que contenha um par chave-valor. O arquivo deve se chamar ***pre\_install.appsflyer***. No arquivo, especifique o par chave-valor no formato `<PACKAGE_NAME>`=`<MEDIA_SOURCE>` Por exemplo, `com.appsflyer.sampleapp=my_media_source`.  

   #### Passagem de parâmetros adicionais de pré-instalação

   É possível especificar parâmetros adicionais de pré-instalação no arquivo usando JSON. Por exemplo, você pode adicionar o seguinte par chave-valor no arquivo **pre\_install.appsflyer**:

   ```json
   com.appsflyer.sampleapp={"pid":"huawei", "c":"special_campaign","af_adset":"some_adset"}
   ```

   > 🚧 **Importante!**
   >
   > É importante levar em consideração os seguintes comportamentos ao usar esta opção:
   >
   > 1. Define "Pre-install" como af\_channel
   > 2. Se o pid não estiver presente no JSON, a Fonte de Mídia aparece como "Nenhum".
   > 3. Na configuração JSON, se c não estiver presente, o nome da campanha é definido como "Pré-instalação"
   > 4. Se o JSON estiver mal formado, a cadeia de caracteres passada é tratada como o nome da fonte de mídia


   Quando tiver o arquivo pre\_install.appsflyer, entregue-o à fonte de mídia ou ao fabricante junto com o APK.
2. Fale com a fonte ou o fabricante do suporte de dados e chegue em um acordo com eles sobre o caminho para colocar o arquivo. O caminho recomendado é "/data/local/tmp/pre\_install.appsflyer".
3. Uma vez acordado um caminho, especifique-o no arquivo do manifesto. Coloque o seguinte trecho antes da tag de fechamento do aplicativo:  

   ```html Markup
   Etapa 1<meta-data android:name="AF_PRE_INSTALL_PATH" 
         android:value="/data/local/temp/pre_install.appsflyer" />:
   ```

#### Fabricante

O fabricante deve colocar o arquivo no caminho acordado. As permissões do arquivo pre\_install.appsflyer devem ser definidas para 744.

Quando o aplicativo é inicializado, o SDK procura no arquivo de manifesto, vê o caminho especificado e procura o arquivo nesse local. Quando o encontra, atribui a instalação de acordo com a fonte de mídia especificada na mesma.

#### Vantagens

A AppsFlyer busca o arquivo **pre\_install.appsflyer** em dois caminhos predefinidos:

```bash
/data/local/tmp/pre_install.appsflyer OR 
/etc/pre_install.appsflyer
```

Alguns fabricantes preferem colocar o arquivo num caminho não predefinido. Nesse caso, pode especificar este caminho não predefinido no arquivo de manifesto.

> 🚧 **Importante!**
>
> O caminho não predefinido requer o SDK versão 4.8 ou posterior
>
> Embora sejam permitidos caminhos não predefinidos, recomendamos a implementação do [método Propriedades do sistema](/docs/appsflyer-factory-preinstall-using-manifest-android#system-properties-method-recommended).

#### Desvantagens

É necessário atualizar arquivos ***pre\_install.appsflyer*** separadamente para diferentes fontes de mídia ou fabricantes.

O fabricante poderá querer colocar o arquivo ***pre\_install.appsflyer*** num caminho não predefinido. Neste caso, é necessário manter APKS separados para cada caminho não predefinido.

Se for usado um **caminho não predefinido**, a instalação poderá não ser atribuída à origem da mídia de pré-instalação:

* Se um usuário com um novo dispositivo atualizar o aplicativo pré-instalado diretamente a partir do Google Play sem o inicializar primeiro, a instalação é considerada orgânica.
* Se um usuário com um novo dispositivo instala o aplicativo a partir do Google Play depois de clicar num anúncio, a instalação é atribuída à fonte de mídia que apresenta o anúncio.

</Accordion>

## Testar a configuração de pré-instalação

Esta seção demonstra como testar e verificar a configuração de pré-instalação.

> 🚧 **Importante!**
>
> Antes de iniciar os testes, certifique-se de que <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices">os dispositivos</Anchor> que vai usar para os testes estão na lista de permissões.
> Além disso, certifique-se de que o registo de depuração está definido como verdadeiro na classe AFApplication.
>
> ```java
> AppsFlyerLib.getInstance().setDebugLog(true);
> ```

<div id="verifying-the-configuration-in-the-app" />

<Accordion title="Verificar a configuração no aplicativo">

> 👍 **Dica**
>
> Para evitar problemas de armazenamento em cache e para obter melhores resultados, recomenda-se que limpe o projeto antes de o construir. No Android Studio, clique em ***Criar*** no menu de contexto e selecione***Limpar projeto***.

Crie seu aplicativo no Android Studio e instale-o no dispositivo de teste. Quando o aplicativo for inicializado, abra o Logcat no Android Studio e filtre por "AppsFlyer". Você deverá ver a instalação atribuída com todos os detalhes. Veja as capturas de tela abaixo como exemplo:

![pre_install_logcat.png](https://files.readme.io/072de6b33e84fe890b7aba44e250346c6e6d65b7e3c836ec4825fa6dcf00b59b-49929298940945.png)

![pre_install_logcat_2.png](https://files.readme.io/d4fc9f8f3ea5febb5c4a2a2b87ed73b3cf1639ee263214de82d2dd5f57a40fb0-49929298941073.png)

</Accordion>

<div id="verifying-the-configuration-in-the-appsflyer-dashboard" />

<Accordion title="Verificando a configuração no painel da AppsFlyer">

Se a configuração for bem sucedida, é apresentada no painel uma instalação não orgânica atribuída a um fabricante ou fonte de mídia. O evento de instalação também está listado na campanha "Pré-instalação".

Acesse sua conta da AppsFlyer e abra o painel do aplicativo que você está testando. Siga as etapas abaixo:

1. Na página de visão geral, filtre por fontes de mídia e selecione a fonte de mídia:  

   ![choose_media_source.png](https://files.readme.io/cde91cfcae8b984953d819ab9d92c573235b28858b3ee9da94017a6bc2b7422a-49929278893969.png)
2. Em ***Distribuição por campanha*** é possível ver que a instalação atribuída à "minha fonte de mídia" vem de uma campanha de Pré-instalação:  

    [![](https://files.readme.io/3e60def526507a2429137762c87ee39149c9a37ff463ce6d3945adc1c4d056bc-360002653405.png)](https://files.readme.io/3e60def526507a2429137762c87ee39149c9a37ff463ce6d3945adc1c4d056bc-360002653405.png)  
   Também é possível verificar se a instalação foi atribuída corretamente, visualizando o ***Relatório de desempenho agregado***. Nela, você pode ver a fonte de mídia e a campanha. Veja a captura de tela abaixo, em que "My Media Source" é a fonte de mídia e a campanha é pré-instalação:  

    [![](https://files.readme.io/cfc65f02299effb38af24f794ee68e865c6d4a71b8dd583b367ea23d962c27dc-49929278896657.png)](https://files.readme.io/cfc65f02299effb38af24f794ee68e865c6d4a71b8dd583b367ea23d962c27dc-49929278896657.png)
3. Repita o processo para todos os fabricantes ou fontes de mídia com os quais colabora para campanhas de pré-instalação.

</Accordion>

## Casos especiais

<div id="multiple-preinstall-apps-on-the-same-device" />

<Accordion title="Vários aplicativos pré-instalados no mesmo dispositivo">

Se tiver campanhas para vários aplicativos que estão instalados no mesmo dispositivo, você pode medir a atribuição usando cada um dos quatro métodos:

* Nome no método de manifesto - para cada aplicativo, especifique a fonte de mídia ou o fabricante no Manifest.xml de cada aplicativo.
* Método da API do SDK - para cada aplicativo, especificar a fonte de mídia ou o fabricante no método da API do SDK para pré-instalação.
* Para propriedades do sistema ou métodos de caminho, você pode especificar os aplicativos e a fonte de mídia correspondente no arquivo ***arquivo pre\_install.appsflyer***. Cada informação do aplicativo deve ser adicionada numa nova linha do arquivo. Por exemplo:

  ```bash
  com.appsflyer.tester=market_name
  com.newapp.newapp=market_name
  com.game.king=market_name
  ```

</Accordion>

<div id="sending-install-postbacks" />

<Accordion title="Envio de postbacks de instalação">

Se a fonte de mídia ou o fabricante com o qual você trabalha for um <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#your-integrated-partners">parceiro da AppsFlyer</Anchor>, você pode ativar postbacks para instalações.

Para isso, certifique-se de que o nome da fonte de mídia é equivalente ao pid da fonte de mídia conforme configurado pela AppsFlyer.

Por exemplo, se estiver trabalhando com market\_name, o seu pid é market\_name\_int. É possível ver o pid no <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#atribuição-de-click-through">link de atribuição de um parceiro integrado</Anchor>.

</Accordion>

<div id="agencies" />

<Accordion title="Agências">

Atualmente, as agências não podem ser atribuídas com pré-instalações.

Se o af\_prt (parâmetro para o nome da agência) fizer parte dos dados de pré-instalação e o usuário inicializar o aplicativo pré-instalado:

* O usuário é atribuído à fonte de mídia usada pela agência (pid=).
* O cliente pode acessar todos os dados no nível do usuário.
* O usuário NÃO é atribuído à agência.
* A agência não pode acessar aos dados no nível do usuário.

</Accordion>

<div data-zendesk-anchors="introduction=introdu%C3%A7%C3%A3o h_01J421581P06FTM7B3XG2GYB2P=introdu%C3%A7%C3%A3o what-is-a-preinstall-campaign=o-que-%C3%A9-uma-campanha-de-pr%C3%A9-instala%C3%A7%C3%A3o h_01J421581P6GYK60D5JQ9PK93N=o-que-%C3%A9-uma-campanha-de-pr%C3%A9-instala%C3%A7%C3%A3o h_01J421581PBQQ5AS3S4JPX52CF=importante benefits-of-recording-installs-from-preinstall-campaigns=vantagens-de-registar-instala%C3%A7%C3%B5es-de-campanhas-de-pr%C3%A9-instala%C3%A7%C3%A3o h_01J421581P5MS4X9BHSJ3TTWBF=vantagens-de-registar-instala%C3%A7%C3%B5es-de-campanhas-de-pr%C3%A9-instala%C3%A7%C3%A3o how-can-i-measure-preinstall-campaigns=como-posso-medir-as-campanhas-de-pr%C3%A9-instala%C3%A7%C3%A3o h_01J421581PEZZW2R244ZX9HX0R=como-posso-medir-as-campanhas-de-pr%C3%A9-instala%C3%A7%C3%A3o viewing-preinstall-data=visualizar-dados-de-pr%C3%A9-instala%C3%A7%C3%A3o h_01J421581PS1CEPK3NN7AZ0ZDE=visualizar-dados-de-pr%C3%A9-instala%C3%A7%C3%A3o h_01J421581PDE1CEXRS6BYTDV35=observa%C3%A7%C3%A3o h_01J421581PKQTX47GC62K4AB9A=observa%C3%A7%C3%A3o-1 setup=configura%C3%A7%C3%A3o h_01J421581P28NEVB44R3XTPY75=configura%C3%A7%C3%A3o h_01J421581QNSQ7W3VYFDVZ1423=system-properties-method-recommended developer=desenvolvedor h_01J421581Q8ZAPZS12PEG4VW3N=desenvolvedor h_01J421581QYRNXCP16GY8CJTKT=importante-1 manufacturer=fabricante h_01J421581QF6Y6MY28N5MR5BTM=fabricante h_01J421581QBFMVT3KPCPPFRX42=observa%C3%A7%C3%A3o-2 advantages=vantagens h_01J421581QEPAC0WZK93HH3QYP=vantagens disadvantages=desvantagens h_01J421581QCG3HARVZVECMHQ1K=desvantagens h_01J421581QQ3VJSSQ06DKZQ0BQ=sdk-api-method when-working-with-a-media-source=ao-trabalhar-com-uma-fonte-de-m%C3%ADdia h_01J421581Q6F1AD0SYXEEJB8FB=ao-trabalhar-com-uma-fonte-de-m%C3%ADdia when-working-with-a-manufacturer=ao-trabalhar-com-um-fabricante h_01J421581Q3YSNH7KXQXET7FD4=ao-trabalhar-com-um-fabricante h_01J421581QRYRWY2WJKCBHQBFG=observa%C3%A7%C3%A3o-3 advantages::d999b734=vantagens-1 h_01J421581QWHP73CA7P13WAQ7Q=vantagens-1 disadvantages::92772f7d=desvantagens-1 h_01J421581QRRFBJWZB5Z6M08BE=desvantagens-1 h_01J421581QF11R7ZXAXRP2YQYR=dica h_01J421581QJ2J54HJFTXF3G5S0=name-in-manifest-file-method advantages::3f0b06fb=vantagens-2 h_01J421581Q8WFYYFQJ45KPWZWP=vantagens-2 disadvantages::919cb3e3=desvantagens-2 h_01J421581QYC02EKB5P0FN5G3F=desvantagens-2 h_01J421581QNFT2E2P3A6MR3BB5=pathway-method h_01J421581QF43JW6A0B48SK9AE=observa%C3%A7%C3%A3o-4 developer::7c51f631=desenvolvedor-1 h_01J421581QB4TH9DMA2ANHG7RD=desenvolvedor-1 passing-additional-preinstall-parameters=passagem-de-par%C3%A2metros-adicionais-de-pr%C3%A9-instala%C3%A7%C3%A3o h_01J421581Q45AEN4GEM5ZKPYRN=passagem-de-par%C3%A2metros-adicionais-de-pr%C3%A9-instala%C3%A7%C3%A3o h_01J421581Q3MMTKPP3E8SZD13F=importante-2 manufacturer::56d9649d=fabricante-1 h_01J421581Q16AVHRCTHME67VHQ=fabricante-1 advantages::1fb76031=vantagens-3 h_01J421581QTRY13FVNQRMG0H2B=vantagens-3 h_01J421581Q0P5VQJHQ9X3VRW8N=importante-3 disadvantages::c9cae863=desvantagens-3 h_01J421581QSNNCHPC2VSF48FT3=desvantagens-3 testing-preinstall-configuration=testar-a-configura%C3%A7%C3%A3o-de-pr%C3%A9-instala%C3%A7%C3%A3o h_01J421581QYHRHF119J4YBZD23=testar-a-configura%C3%A7%C3%A3o-de-pr%C3%A9-instala%C3%A7%C3%A3o h_01J421581QW0XKZ635A194W80J=importante-4 h_01J421581QPXQDFX5G11B7GSNA=verifying-the-configuration-in-the-app h_01J421581QSZPZVZ6GGQST5FWS=dica-1 h_01J421581Q7PGHJ2HBX1ZDNJS6=verifying-the-configuration-in-the-appsflyer-dashboard special-cases=casos-especiais h_01J421581Q624TH08PX24B1P3X=casos-especiais h_01J421581QQHB8624SS6FSSA6D=multiple-preinstall-apps-on-the-same-device h_01J421581Q86AB5GTM91ARYJ23=sending-install-postbacks h_01J421581RD2WQ6SPES729GJEP=agencies" />
