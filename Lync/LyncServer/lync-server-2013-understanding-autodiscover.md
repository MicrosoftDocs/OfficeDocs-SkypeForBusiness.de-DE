---
title: 'Lync Server 2013: Grundlegendes zu AutoErmittlung'
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
ms.openlocfilehash: d9d885654f9222ce3d3e9fb7b03e9b388f0ca0a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a>Grundlegendes zu AutoErmittlung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-06-03_

Der lync Server 2013-AutoErmittlungsdienst ist ein Feature, das ursprünglich in Microsoft lync Server 2010 als Teil des kumulativen Updates für lync Server 2010: November 2011 eingeführt wurde. Dieses kumulative Update hat nicht nur Korrekturen, sondern auch Unterstützung für lync Mobile-und lync 2013-Clients bereitgestellt.

In lync Server 2013 ist der AutoErmittlungsdienst ein integraler Bestandteil des Vorgangs externer und interner mobiler Clients, und die AutoErmittlung wird auch auf neue Clients ausgedehnt, wie etwa die kürzlich eingeführte lync Windows Store-App für Windows 8. Die AutoErmittlung wird auch von den lync 2013-Desktop Clients verwendet. AutoErmittlung wird in lync Server durch die erforderlichen DNS-Einträge (Domain Name System) **lyncdiscover\< . Domäne\> ** und **lyncdiscoverinternal.\< Domäne\>** aus. Darüber hinaus bevorzugen neuere Versionen des lync 2010-und lync 2013-Desktop Clients die AutoErmittlung über die DNS-SRV-Einträge (Domain Name System), wobei nur DNS-SRV-Einträge verwendet werden, wenn lyncdiscover. \<Domäne\> oder lyncdiscoverinternal. \<die\> Domäne reagiert nicht oder wird nicht aufgelöst. Die lync Windows Store-App für Windows 8 und lync Mobile verwendet die AutoErmittlung ausschließlich und bezieht sich nicht auf die herkömmlichen DNS-SRV-Einträge.

In lync Server 2013 wird die AutoErmittlung erweitert, um dem Client zu kommunizieren, welche Elemente, Features und Kommunikationsmethoden dem Client zur Verfügung stehen. Die Informationen werden über eine Anforderung kommuniziert, die vom Client gesendet wird, und die lync Server-Webdienste antwortet mit einer klar definierten Antwort, mit der der Name der für den Client verfügbaren Namen benannt wird, und wie Sie diese Features im Format der AutoErmittlung kontaktieren können. Antwortdokument.

Die beste Methode, um das Antwortdokument für die AutoErmittlung zu verstehen, einschließlich der Art und Weise, wie die Webdienste Features an Clients über dieses Dokument übermitteln, besteht darin, jede Zeile in einer typischen Antwort des lync Web Service-Antwortdokuments für die automatische Erkennung zu analysieren und zu definieren.

<div class="">


> [!NOTE]  
> In den Details, die Folgen, hat sich der Benutzer bereits auf dem Stammserver authentifiziert, indem er auf eine Authentifizierungsanforderung reagiert.



</div>

<div class="">


> [!NOTE]  
> Der lync-Auto Ermittlungs-Webdienst ist in den <STRONG>Microsoft Office-Protokollen</STRONG> im Abschnitt <STRONG>Open Specifications</STRONG> der <STRONG>Microsoft Developer Network</STRONG> (MSDN)-Bibliothek definiert. Ausführliche Informationen finden Sie im vollständigen Spezifikationsdokument "lync autodiscover Web Service Protocol" unter <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>:. Details zur Authentifizierung finden Sie unter "OC Authentication Web Service Protocol" unter <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>.



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>Die Antwort auf die AutoErmittlung des lync Server-Webdiensts

Die Antwort, die beim Senden der Auto Ermittlungsanforderung zurückgegeben wird, ist für einen internen oder externen Client identisch. Einige Parameter, die Standort abhängig sind, können sich ändern. Wenn eine Clientanforderung empfangen wird, der tatsächliche Pool aber nicht mit der Kontaktperson ist, wird der Benutzerpool für diesen Benutzer festgesetzt. Ein Kollege, dessen Benutzerkonto sich in einem anderen Pool befindet, sich aber vom gleichen Office aus anmeldet, würde eine etwas andere Antwort erhalten. Die Antwort gibt den richtigen Front-End-Server oder Front-End-Pool für diesen Benutzer an.

Ein Beispiel für ein Antwortdokument für die AutoErmittlung:

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

## <a name="autodiscover-response-document-details"></a>Details des Auto Ermittlungs Antwortdokuments

Das Antwortdokument für die AutoErmittlung kann in einem von zwei Formaten vorliegen. Das Standardformat ist eine JSON (JavaScript Object Notation). Das andere Format ist das XML-Dokument (Extensible Markup Language). Der XML-Code wird für dieses Beispiel verwendet. Die Anforderung und Antwort sind vorhersehbar, da das Dokument über ein definiertes Schema verfügt, das das Format bestimmt. Die Zeile im Dokument, die das verwendete Schema beschreibt, ist die erste Zeile in der Anforderung oder Antwort:

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

Die Definition von **Zugriffsort = "extern"** gibt an, dass die Anforderung von einem externen Benutzer vorgenommen wurde.

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

SipServerInternalAccess und SipServerExternalAccess werden zurzeit nicht verwendet. Diese Einträge sind für die spätere Verwendung reserviert.

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess und SipClientExternalAccess beschreiben den vollqualifizierten Domänennamen und-Port, den ein interner oder externer Client für den Zugriff auf den festgelegten SIP-Server verwendet. Der lync-Desktop Client und die lync Windows Store-App verwenden diese Einträge basierend auf Ihrem Standort (intern oder extern), um den Director oder Front-End-Server zu finden.

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

Die `Autodiscover` Verweise enthalten die Dienst Einstiegspunkte für den AutoErmittlungsdienst. Das Token-Attribut enthält den Namen des Diensts, und die href-Eigenschaft ist eine URL, die für den Client definiert, in dem der Dienst gefunden werden kann. Clients in einem externen Netzwerk verwenden `External/Autodiscover`. Der AutoErmittlungsdienst wird als Teil des Bereitstellungsprozesses installiert. `Internal/Autodiscover`wird derzeit nicht verwendet und ist für die spätere Verwendung reserviert.

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

Die `AuthBroker` Verweise enthalten die Dienst Einstiegspunkte für den internen und den externen Authentifizierungsbroker Dienst, in diesem Fall SIP. svc. Das Token-Attribut enthält den Namen des Diensts, und die href-Eigenschaft ist eine URL, die für den Client definiert, in dem der Dienst gefunden werden kann. Clients im internen Netzwerk mit Verwendung `Internal/AuthBroker`. Clients in einem externen Netzwerk verwenden `External/AuthBroker`. Der AuthBroker-Dienst wird als Teil des Bereitstellungsprozesses ihrer internen lync Server 2013-Bereitstellungs Webdienste installiert.

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

Das `WebScheduler` Token verweist auf die URLs für den Clientzugriff auf die webbasierte Planung für lync Server-Konferenzen. Derzeit wird nur die `External/WebScheduler` verwendet. Der Webplaner wird im Rahmen des Bereitstellungsprozesses ihrer internen lync Server 2013-Bereitstellungs Webdienste installiert.

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx`und `External/Mcx` sind die Speicherorte der Mobilitätsdienste, die im kumulativen Update für lync Server 2010: November 2011 eingeführt wurden. Diese Verweise werden weiterhin von lync 2010 Mobile auf allen unterstützten Geräten verwendet. Der MCX-Dienst wird als Teil des Bereitstellungsprozesses ihrer internen lync Server 2013-Bereitstellungs Webdienste installiert.

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Internal/Ucwa**, **External/Ucwa** und **Ucwa** bieten Clients einen Mittel für den Zugriff auf die Unified Communications Web Application-Programmierschnittstelle (Ucwa-API oder einfach Ucwa). `Internal/Ucwa`und `External/Ucwa` virtuelle Verzeichnisse sind Zugriffspunkte, die für zukünftige Funktionserweiterungen reserviert sind und nicht verwendet werden. Das `Ucwa` virtuelle Verzeichnis wird für Microsoft lync Mobile (eingeführt mit lync Server 2013) auf allen unterstützten Geräten verwendet. Der UCWA-Dienst wird als Teil des Bereitstellungsprozesses ihrer internen lync Server 2013-Bereitstellungs Webdienste installiert.

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`, **External/Xframe** und **Xframe** bieten Zugriff auf UCWA-basierte Serveranwendungen. Xframe wird als Teil des Bereitstellungsprozesses ihrer internen lync Server 2013-Bereitstellungs Webdienste installiert.

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

Das `Self` Token bezieht sich auf spezifische Informationen für den Client (Benutzer Antworttyp), der die Anforderung vornimmt. Der Client, der diese Anforderung gestellt hat, war extern, und dieser autodiscover-Verweis bezieht sich auf den Benutzer Teil des AutoErmittlungsdiensts.

</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Systemanforderungen für Komponenten für den Zugriff durch externe Benutzer für Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Planen der AutoErmittlung in lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

