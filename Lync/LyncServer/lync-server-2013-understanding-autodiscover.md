---
title: Grundlegendes zur AutoErmittlung
TOCTitle: Grundlegendes zur AutoErmittlung
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945654(v=OCS.15)
ms:contentKeyID: 52056468
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grundlegendes zur AutoErmittlung

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Der Lync Server 2013-AutoErmittlungsdienst ist ein Feature, das ursprünglich in Microsoft Lync Server 2010 als Teil des kumulativen Updates für Lync Server 2010 vom November 2011 eingeführt wurde. Dieses kumulative Update stellte nicht nur Korrekturen bereit, sondern bot auch Unterstützung für Lync Mobile- und Lync 2013-Clients.

In Lync Server 2013 ist der AutoErmittlungsdienst wichtig für den Betrieb externer und interner mobiler Clients, und die AutoErmittlung wird auch auf neue Clients ausgedehnt, z. B. auf die vor kurzem eingeführte Windows Store-App für Lync für Windows 8. Darüber hinaus wird die AutoErmittlung auch von den Lync 2013-Desktopclients verwendet. Die AutoErmittlung wird in Lync Server anhand der erforderlichen DNS-Einträge (Domain Name System) **lyncdiscover.\<domäne\>** und **lyncdiscoverinternal.\<domäne\>** erkannt. Zudem wird in neueren Versionen des Lync 2010- und Lync 2013-Desktopclients die AutoErmittlung gegenüber den DNS-SRV-Einträgen bevorzugt. Die DNS-SRV-Einträge werden nur verwendet, wenn "lyncdiscover.\<domäne\>" oder "lyncdiscoverinternal.\<domäne\>" nicht aufgelöst werden oder von ihnen keine Antwort zurückgegeben wird. Die Windows Store-App für Lync für Windows 8 und Lync Mobile verwendet ausschließlich die AutoErmittlung und verweist nicht auf die herkömmlichen DNS-SRV-Einträge.

In Lync Server 2013 wird die AutoErmittlung erweitert, um dem Client mitzuteilen, welche Elemente, Features und Kommunikationsmethoden dem Client zur Verfügung stehen. Die Informationen werden über eine vom Client gesendete Anforderung kommuniziert, und der Lync Server-Webdienst antwortet mit einer klar definierten Antwort in Form eines AutoErmittlung-Antwortdokuments. Darin ist aufgelistet, was genau für den Client verfügbar ist und wie diese Features angesprochen werden können.

Im Folgenden wird ein typisches AutoErmittlung-Antwortdokument von einem Lync-Webdienst aufgegliedert und jede darin enthaltene Zeile erläutert. So ist es am einfachsten, das AutoErmittlung-Antwortdokument zu interpretieren und zu verstehen, wie die Webdienste dem Client anhand dieses Dokuments die zur Verfügung stehenden Features mitteilen.


> [!NOTE]
> Bei den folgenden Angaben wird angenommen, dass sich der Benutzer durch Beantworten einer Authentifizierungsanfrage bereits beim Homeserver authentifiziert hat.




> [!NOTE]
> Der Lync-AutoErmittlung-Webdienst ist in den <STRONG>Microsoft Office-Protokollen</STRONG> im Abschnitt zu den <STRONG>Offenen Spezifikationen</STRONG> der MSDN Library (<STRONG>Microsoft Developer Network</STRONG>) definiert. Ausführliche Informationen finden Sie im Dokument mit den vollständigen Spezifikationen zum Lync-AutoErmittlung-Webdienstprotokoll unter: <A class=uri href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?linkid=273839</A>. Informationen zur Authentifizierung finden Sie auf der Seite "OC Authentication Web Service Protocol" unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?linkid=279015</A>.



## Die AutoErmittlung-Antwort vom Lync Server-Webdienst

Die nach dem Senden einer AutoErmittlung-Anforderung zurückgegebene Antwort ist bei internen und externen Clients gleich. Es kann Änderungen bei den standortabhängigen Parametern geben. Wenn eine Clientanforderung empfangen wird, aber der tatsächliche Pool nicht mit dem kontaktierten Pool identisch ist, wird für diesen Benutzer der Home-Pool des Benutzers festgelegt. Ein Kollege, dessen Konto sich zwar in einem anderen Pool befindet, der sich aber vom gleichen Büro aus anmeldet, würde eine etwas andere Antwort erhalten. In der Antwort wird auf den richtigen Front-End-Server oder Front-End-Pool für diesen Benutzer verwiesen.

Beispiel für ein AutoErmittlung-Antwortdokument:

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

## Details zum AutoErmittlung-Antwortdokument

Das AutoErmittlung-Antwortdokument kann in einem von zwei Formaten vorliegen. Das Standardformat ist ein JSON-Dokument (JavaScript Object Notation). Das andere Format ist ein XML-Dokument (eXtensible Markup Language). In diesem Beispiel wird das XML-Format verwendet. Die Anforderung und Antwort sind vorhersagbar, da das Dokument ein definiertes Schema hat, das das Format bestimmt. In der ersten Zeile der Anforderung oder Antwort wird das verwendete Schema beschrieben:

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

Die Definition **AccessLocation="External"** gibt an, dass die Anforderung von einem externen Benutzer gestellt wurde.

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

   &nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

"SipServerInternalAccess" und "SipServerExternalAccess" werden derzeit nicht verwendet. Diese Einträge sind für die zukünftige Verwendung reserviert.

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

   &nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

"SipClientInternalAccess" und "SipClientExternalAccess" beschreiben den vollqualifizierten Domänennamen (FQDN) und Port, die von einem internen oder externen Client für den Zugriff auf den definierten SIP-Server verwendet werden. Der Lync-Desktopclient und die Windows Store-App für Lync verwenden diese Einträge basierend auf ihrem Standort (intern oder extern), um den Director oder Front-End-Server zu finden.

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

   &nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

Die `Autodiscover`-Verweise enthalten die Diensteinstiegspunkte für den AutoErmittlungsdienst. Das Tokenattribut enthält den Namen des Diensts und "href" ist eine URL, die für den Client definiert, wo der Dienst zu finden ist. Clients in einem externen Netzwerk verwenden `External/Autodiscover`. Der AutoErmittlungsdienst wird im Rahmen des Bereitstellungsprozesses installiert. `Internal/Autodiscover` wird derzeit nicht verwendet und ist für die zukünftige Verwendung reserviert.

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

   &nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

Die `AuthBroker`-Verweise enthalten die Diensteinstiegspunkte für den internen und externen Authentifizierungsbrokerdienst, in diesem Fall: sip.svc. Das Tokenattribut enthält den Namen des Diensts und "href" ist eine URL, die für den Client definiert, wo der Dienst zu finden ist. Clients im internen Netzwerk verwenden `Internal/AuthBroker`. Clients in einem externen Netzwerk verwenden `External/AuthBroker`. Der Authentifizierungsbrokerdienst wird im Rahmen des Bereitstellungsprozesses der internen Lync Server 2013-Bereitstellungswebdienste installiert.

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

   &nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

Das `WebScheduler`-Token verweist auf die URLs, die für den Clientzugriff auf die webbasierte Planung für Lync Server-Konferenzen vorgesehen sind. Derzeit wird nur `External/WebScheduler` verwendet. Der Web Scheduler wird im Rahmen des Bereitstellungsprozesses der internen Lync Server 2013-Bereitstellungswebdienste installiert.

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

   &nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx` und `External/Mcx` geben den Ort der Mobilitätsdienste an, die mit dem kumulativen Update für Lync Server 2010 vom November 2011 eingeführt wurden. Diese Verweise werden weiterhin von Lync 2010 Mobile auf allen unterstützten Geräten verwendet. Der Mcx-Dienst wird als Teil des Bereitstellungsprozesses der internen Lync Server 2013-Bereitstellungswebdienste installiert.

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

   &nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

   &nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Internal/Ucwa**, **External/Ucwa** und **Ucwa** bieten eine Möglichkeit für Clients, auf die Unified Communications Web Application Programming Interface (UCWA-API oder einfach UCWA) zuzugreifen. Die virtuellen Verzeichnisse `Internal/Ucwa` und `External/Ucwa` sind Zugriffspunkte, die für eine zukünftige Featureerweiterung reserviert sind und werden derzeit nicht verwendet. Das virtuelle Verzeichnis `Ucwa` wird für Microsoft Lync Mobile (eingeführt mit Lync Server 2013) auf allen unterstützten Geräten verwendet. Der UCWA-Dienst wird als Teil des Bereitstellungsprozesses der internen Lync Server 2013-Bereitstellungswebdienste installiert.

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

   &nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

   &nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`, **External/XFrame** und **XFrame** bieten Zugriff für UCWA-basierte Serveranwendungen. XFrame wird im Rahmen des Bereitstellungsprozesses der internen Lync Server 2013-Bereitstellungswebdienste installiert.

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

Das `Self`-Token verweist auf Informationen, die für den Client, der die Anforderung stellt, spezifisch sind (Benutzerantworttyp). Diese Anforderung wurde von einem externen Client gestellt, und dieser AutoErmittlung-Verweis bezieht sich auf den Benutzerteil des AutoErmittlungsdiensts.

## Siehe auch

#### Weitere Ressourcen

[Systemanforderungen für Komponenten für den Zugriff durch externe Benutzer für Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Planen der AutoErmittlung in Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)

