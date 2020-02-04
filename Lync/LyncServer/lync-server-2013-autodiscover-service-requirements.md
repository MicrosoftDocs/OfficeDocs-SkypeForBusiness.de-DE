---
title: 'Lync Server 2013: Anforderungen für den AutoErmittlungsdienst'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 777d70b20a51e5408fe9d9248028c3dbcaebeba2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a>Anforderungen für den AutoErmittlungsdienst für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-25_

Der Microsoft lync Server 2013-AutoErmittlungsdienst wird auf den Director-und Front-End-Pool Servern ausgeführt und kann bei Veröffentlichung in DNS von mobilen Geräten, auf denen lync Mobile ausgeführt wird, verwendet werden, um Mobilitätsdienste zu finden. Bevor Mobile Geräte, auf denen lync Mobile ausgeführt wird, die automatische Ermittlung nutzen können, müssen Sie die Listen für alternative Namen für Zertifikats Subjekte auf jedem Director-und Front-End-Server ändern, auf dem der AutoErmittlungsdienst ausgeführt wird. Darüber hinaus ist es möglicherweise erforderlich, die Listen Betreff alternativer Name auf Zertifikaten zu ändern, die für externe Webdienst Veröffentlichungsregeln für umgekehrte Proxys verwendet werden.

Details zu den Einträgen des alternativen betreffs, die für Directors, Front-End-Server und Reverse-Proxies erforderlich sind, finden Sie unter [Technische Voraussetzungen für Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) bei der Planung für Mobilität.

Die Entscheidung über die Verwendung von Listen für alternative namens Subjekte in umgekehrten Proxys basiert darauf, ob Sie den AutoErmittlungsdienst auf Port 80 oder auf Port 443 veröffentlichen:

  - **Veröffentlicht auf Port 80**   es sind keine Zertifikat Änderungen erforderlich, wenn die ursprüngliche Abfrage des AutoErmittlungsdiensts über Port 80 erfolgt. Dies liegt daran, dass Mobile Geräte, auf denen lync ausgeführt wird, auf den Reverse-Proxy auf Port 80 extern zugreifen und dann intern auf Port 8080 an einen Director oder Front-End-Server umgeleitet werden. Ausführliche Informationen finden Sie weiter unten in diesem Thema im Abschnitt "ursprünglicher Auto Ermittlungsprozess mit Port 80".

  - **Veröffentlicht auf Port 443**   die Liste der alternativen Subjektnamen für Zertifikate, die von der externen Webdienste-Veröffentlichungsregel verwendet werden, muss eine *lyncdiscover enthalten.\< sipdomain\> * -Eintrag für jede SIP-Domäne innerhalb Ihrer Organisation.

Das erneute Ausstellen von Zertifikaten unter Verwendung einer internen Zertifizierungsstelle ist in der Regel ein einfacher Vorgang, für öffentliche Zertifikate, die für die Veröffentlichungsregel des Webdiensts verwendet werden, kann das Hinzufügen mehrerer Alternativen Betreff-Namen zu kostspielig werden Um dieses Problem zu umgehen, unterstützen wir die anfängliche automatische Ermittlungs Verbindung über Port 80, die dann auf Port 8080 auf dem Director-oder Front-End-Server umgeleitet wird.

Nehmen wir beispielsweise an, dass ein mobiler Client, auf dem lync Mobile ausgeführt wird, für die Anmeldung bei lync Server 2013 mit dem automatischen Ermittlungs Feature unter Verwendung von http für die ursprüngliche Anforderung konfiguriert ist.

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a>Erster Auto Ermittlungsprozess für mobile Geräte mit Port 80

1.  Mobiles Gerät mit lync Mobile sucht lyncdiscover.contoso.com mithilfe von DNS, wobei ein A-Eintrag vorhanden ist.

2.  Externer DNS gibt die IP-Adresse für die externen Webdienste an den Client zurück.

3.  Mobiles Gerät mit lync Mobile sendet http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com eine Anforderung an den Reverse-Proxy

4.  Die Webveröffentlichungsregel überbrückt die Anforderung von Port 80 extern zu Port 8080 intern, wodurch Sie an einen Director oder Front-End-Server weitergeleitet wird.
    
    Da es sich bei der Anforderung um http und nicht um HTTPS handelt, sind keine Änderungen an dem Zertifikat in der Veröffentlichungsregel für externe Web Services erforderlich, um den AutoErmittlungsdienst zu unterstützen.

5.  Der AutoErmittlungsdienst gibt die URLs des externen Webdiensts (im HTTPS-Format) zurück.

6.  Das Mobile Gerät mit lync Mobile kann dann erneut eine Verbindung mit dem Reverse Proxy auf Port 443 herstellen und wird über 4443 an den Mobilitätsdienst weitergeleitet, der im Home-Pool des Benutzers ausgeführt wird.
    
    Da es sich bei der HTTPS-Abfrage um die URL des externen Webdiensts und die AutoErmittlungsdienst-URL handelt, ist Sie erfolgreich, da das Zertifikat bereits Einträge für alternative Namen für externe Webdienste enthält, die vollständig qualifizierte Domänennamen (FQDNs) sind.
    
    In diesem Szenario sind keine Zertifikat Änderungen erforderlich, um die Mobilität zu unterstützen.
    
    <div>
    

    > [!NOTE]  
    > Wenn der Zielwebserver über ein Zertifikat verfügt, das keinen übereinstimmenden Wert für "lyncdiscover.contoso.com" als "Subject Alternative Name"-Listenwert aufweist:<BR>a.&nbsp;&nbsp;&nbsp;Web Server antwortet mit einem "Server Hello" und ohne Zertifikat.<BR>b.&nbsp;&nbsp;&nbsp;mobiles Gerät, auf dem lync Mobile ausgeführt wird, beendet sofort die Sitzung.<BR>Wenn der Zielwebserver über ein Zertifikat verfügt, das lyncdiscover.contoso.com als Namen Listenwert für Subjekt Alternativen enthält:<BR>a.&nbsp;&nbsp;&nbsp;Web Server antwortet mit einem "Server Hello" und einem Zertifikat.<BR>b.&nbsp;&nbsp;&nbsp;auf einem mobilen Gerät mit lync Mobile wird das Zertifikat überprüft und der Handshake abgeschlossen.

    
    </div>

Wenn Sie eine anfängliche Verbindung mit dem AutoErmittlungsdienst mithilfe von Port 80 auf dem Reverse-Proxy Server unterstützen möchten, können Sie eine HTTP-Veröffentlichungsregel ähnlich wie in diesem Beispiel für eine Forefront Threat Management Gateway 2010 Reverse Proxy Web-Veröffentlichungsregel erstellen:

1.  Erstellen Sie eine neue Webveröffentlichungsregel (beispielsweise die **lync Server-AutoErmittlung (http)**).

2.  Geben Sie in **Öffentlicher Name**lyncdiscover.contoso.com ein.

3.  Wählen Sie auf der Registerkarte **Bridging** nur die Option aus, um Anforderungen von Port 80 auf Port 8080 zu überbrücken.

4.  Wählen Sie auf der Registerkarte **Authentifizierung** die Option **keine Authentifizierung**aus, und der **Client kann sich nicht direkt authentifizieren**.

5.  Übernehmen Sie Änderungen, und verschieben Sie die Regel an den Anfang der Liste der lync-Regeln (zunächst in der Verarbeitungsreihenfolge).

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Mobilität für die Bereitstellung von geteilten Domänen

Ein freigegebener SIP-Adressraum, auch bekannt als " *Split-Domain*" oder eine *hybridbereitstellung* , ist eine Konfiguration, in der Benutzer über eine lokale Bereitstellung und eine Online Umgebung bereitgestellt werden. Das gewünschte Ergebnis besteht darin, dass Sie einen Benutzer haben, unabhängig davon, wo sich der Home-Server befindet (lokal oder Online), um sich bei der Bereitstellung anzumelden und an den Standort Ihres Home-Servers weitergeleitet zu werden. Um dies zu erreichen, wird das Feature AutoErmittlung von Microsoft lync Server 2013 verwendet, um den Online Benutzer zur Online Topologie umzuleiten. Dies erfolgt durch die Konfiguration des Uniform Resource Locator (URL) für die AutoErmittlung mithilfe der lync Server-Verwaltungsshell und der Cmdlets **Get-CsHostingProvider** und **CsHostingProvider**.

Sie müssen die folgenden bereitgestellten Attribute sammeln und aufzeichnen:

  - Geben Sie in der lync Server-Verwaltungsshell
    
        Get-CsHostingProvider

  - Suchen Sie in den Ergebnissen den Onlineanbieter mit dem Attribut **ProxyFQDN**. Beispiel: sipfed.online.lync.com

  - Aufzeichnen des Werts des ProxyFQDN

  - Aktivieren der Föderation in der lokalen lync Server-Systemsteuerung, wodurch die Föderation mit dem Onlineanbieter zugelassen wird

  - Aktivieren Sie den Verbund für den Onlineanbieter. Standardmäßig sind alle Online Benutzer für den Domänen Verbund aktiviert und können mit allen Domänen kommunizieren.

  - Wenn Sie blockierte und zulässige Domänen definieren, ermitteln Sie die Domänen, die explizit zugelassen oder explizit blockiert werden.

  - Für die Online-Föderation müssen Sie Firewall-Ausnahmen, Zertifikate und DNS-Host (A oder AAAA, wenn Sie IPv6 verwenden) planen. Darüber hinaus müssen Sie Verbund Richtlinien konfigurieren. Ausführliche Informationen finden Sie unter [Planen von lync Server 2013 und Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

