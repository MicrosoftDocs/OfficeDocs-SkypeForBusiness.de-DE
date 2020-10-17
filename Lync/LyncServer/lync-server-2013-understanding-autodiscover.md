---
title: 'Lync Server 2013: Understanding AutoErmittlung'
description: 'Lync Server 2013: Understanding AutoErmittlung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 295aba4bffbe5d17070702203cfd933284cb12c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547351"
---
# <a name="understanding-autodiscover-in-lync-server-2013"></a>Grundlegendes zur AutoErmittlung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-06-03_

Der lync Server 2013 AutoErmittlungsdienst ist ein Feature, das ursprünglich in Microsoft lync Server 2010 als Teil des kumulativen Updates für lync Server 2010: November 2011 eingeführt wurde. Dieses kumulative Update hat zusätzlich zu Korrekturen Unterstützung für lync Mobile und lync 2013 Clients bereitgestellt.

In lync Server 2013 ist der AutoErmittlungsdienst ein integraler Bestandteil des Betriebs externer und interner mobiler Clients, und die AutoErmittlung wird auch auf neue Clients ausgedehnt, beispielsweise auf die kürzlich eingeführte lync Windows Store-App für Windows 8. Die AutoErmittlung wird auch von den lync 2013-Desktop Clients verwendet. Die AutoErmittlung wird in lync Server durch die erforderlichen DNS-Einträge (Domain Name System) **lyncdiscover erkannt. \<domain\> ** und **"lyncdiscoverinternal". \<domain\> **. Darüber hinaus bevorzugen neuere Versionen der lync 2010 und lync 2013 Desktop Clients die AutoErmittlung über die DNS-SRV-Einträge (Domain Name System), wobei DNS-SRV-Einträge nur bei lyncdiscover verwendet werden.\<domain\> oder "lyncdiscoverinternal".\<domain\> reagiert nicht oder wird nicht aufgelöst. Die lync Windows Store-App für Windows 8 und lync Mobile verwendet die AutoErmittlung ausschließlich und bezieht sich nicht auf die herkömmlichen DNS-SRV-Einträge.

In lync Server 2013 wird die AutoErmittlung erweitert, um dem Client mitzuteilen, welche Elemente, Features und Kommunikationsmethoden dem Client zur Verfügung stehen. Die Informationen werden über eine vom Client gesendete Anforderung kommuniziert, und die lync Server-Webdienste antwortet mit einer klar definierten Antwort, die den Namen für den Client bereitstellt, und wie diese Features im Format des Antwortdokuments für die AutoErmittlung kontaktiert werden.

Die beste Möglichkeit zum Verständnis des Antwortdokuments für die AutoErmittlung, einschließlich der Kommunikation der Webdienste mit Clients über dieses Dokument, besteht darin, die einzelnen Leitungen in einer typischen Antwort aus dem lync-Webdienst-Antwortdokument für die automatische Erkennung zu analysieren und zu definieren.

<div class="">


> [!NOTE]  
> In den folgenden Details hat sich der Benutzer bereits beim Stammserver authentifiziert, indem er auf eine Authentifizierungsanforderung antwortet.



</div>

<div class="">


> [!NOTE]  
> Der lync autodiscover-Webdienst ist in den <STRONG>Microsoft Office-Protokollen</STRONG> im Abschnitt <STRONG>Open Specifications</STRONG> der MSDN-Bibliothek ( <STRONG>Microsoft Developer Network</STRONG> ) definiert. Ausführliche Informationen finden Sie im vollständigen Spezifikationsdokument "lync autodiscover-Webdienstprotokoll" unter: <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A> . Ausführliche Informationen zur Authentifizierung finden Sie unter "OC Authentication-Webdienstprotokoll" unter <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A> .



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>Die Antwort des lync Server-Webdienst-AutoErmittlungsdiensts

Die beim Senden der Auto Ermittlungsanforderung zurückgegebene Antwort ist für einen internen oder externen Client identisch. Einige Parameter, die Standort fähig sind, können sich ändern. Wenn eine Clientanforderung empfangen wird, der tatsächliche Pool jedoch nicht mit dem Kontakt aufgenommen wurde, wird der Home-Pool des Benutzers für diesen Benutzer festgelegt. Ein Kollege, dessen Benutzerkonto sich in einem anderen Pool befindet, sich aber vom gleichen Büro aus einloggt, würde eine etwas andere Antwort erhalten. Die Antwort gibt die richtige Front-End-Server oder Front-End-Pool für diesen Benutzer an.

Ein Beispiel für ein Auto Ermittlungs Antwortdokument:

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

<div>

## <a name="autodiscover-response-document-details"></a>Details zum Auto Ermittlungs Antwort-Dokument

Das Antwortdokument der AutoErmittlung kann in einem von zwei Formaten vorliegen. Das Standardformat ist ein JavaScript Object Notation (JSON). Das andere Format ist XML-Dokument (Extensible Markup Language). In diesem Beispiel wird der XML-Code verwendet. Die Anforderung und die Antwort sind vorhersehbar, da das Dokument über ein definiertes Schema verfügt, das das Format bestimmt. Die im Dokument beschriebene Textfolge, die das verwendete Schema beschreibt, ist die erste in der Anforderung oder Antwort:

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

Die Definition von **Zugriffsort = "extern"** gibt an, dass die Anforderung von einem externen Benutzer gestellt wurde.

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

SipServerInternalAccess und SipServerExternalAccess werden derzeit nicht verwendet. Diese Einträge sind für die zukünftige Verwendung reserviert.

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess und SipClientExternalAccess beschreiben den vollqualifizierten Domänennamen und den Port, der von einem internen oder externen Client für den Zugriff auf den definierten SIP-Server verwendet wird. Der lync-Desktop Client und die lync Windows Store-App verwenden diese Einträge basierend auf Ihrem Standort (intern oder extern), um den Director oder Front-End-Server zu finden.

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

Die `Autodiscover` Verweise enthalten die Dienst Einstiegspunkte für den AutoErmittlungsdienst. Das Token-Attribut enthält den Namen des Diensts, und der href ist eine URL, die für den Client definiert, in dem der Dienst gefunden werden kann. Clients in einem externen Netzwerk verwenden die `External/Autodiscover` . Der AutoErmittlungsdienst wird als Teil des Bereitstellungsprozesses installiert. `Internal/Autodiscover` wird derzeit nicht verwendet und ist für die zukünftige Verwendung reserviert.

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

Die `AuthBroker` Verweise enthalten die Dienst Einstiegspunkte für den internen und den externen Authentifizierungsbroker-Dienst, in diesem Fall "SIP. svc". Das Token-Attribut enthält den Namen des Diensts, und der href ist eine URL, die für den Client definiert, in dem der Dienst gefunden werden kann. Clients im internen Netzwerk werden mit verwendet `Internal/AuthBroker` . Clients in einem externen Netzwerk verwenden die `External/AuthBroker` . Der AuthBroker-Dienst wird als Teil des Bereitstellungsprozesses ihrer internen lync Server 2013-Bereitstellungs-Webdienste installiert.

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

Das `WebScheduler` Token verweist auf die URLs für den Clientzugriff auf die webbasierte Planung für lync Server Konferenzen. Derzeit wird nur der `External/WebScheduler` verwendet. Der WebScheduler wird als Teil des Bereitstellungsprozesses ihrer internen lync Server 2013-Bereitstellungs-Webdienste installiert.

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx` und `External/Mcx` sind die Speicherorte der Mobilitätsdienste, die im kumulativen Update für lync Server 2010 eingeführt wurden: November 2011. Diese Verweise werden weiterhin von lync 2010 Mobile auf allen unterstützten Geräten verwendet. Der MCX-Dienst wird als Teil des Bereitstellungsprozesses ihrer internen lync Server 2013-Bereitstellungs-Webdienste installiert.

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Interne/Ucwa**, **External/Ucwa** und **Ucwa** bieten Clients einen Mittel für den Zugriff auf die Unified Communications-Webanwendungs-Programmierschnittstelle (Ucwa-API oder einfach Ucwa). `Internal/Ucwa` und `External/Ucwa` virtuelle Verzeichnisse sind Zugriffspunkte, die für die zukünftige Funktionserweiterung reserviert sind und nicht verwendet werden. Das `Ucwa` virtuelle Verzeichnis wird für Microsoft lync Mobile (mit lync Server 2013 eingeführt) auf allen unterstützten Geräten verwendet. Der UCWA-Dienst wird als Teil des Bereitstellungsprozesses ihrer internen lync Server 2013-Bereitstellungs-Webdienste installiert.

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`, **External/Xframe** und **Xframe** bieten Zugriff für UCWA-basierte Serveranwendungen. Xframe wird als Teil des Bereitstellungsprozesses ihrer internen lync Server 2013-Bereitstellungs-Webdienste installiert.

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

Das `Self` Token bezieht sich auf spezifische Informationen für den Client (Benutzer Antworttyp), der die Anforderung macht. Der Client, der diese Anforderung gestellt hat, war extern, und dieser Verweis auf die AutoErmittlung bezieht sich auf den Benutzer Teil des AutoErmittlungsdiensts.

</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[System Anforderungen für Komponenten für den Zugriff durch externe Benutzer für lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Planen der AutoErmittlung in lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

