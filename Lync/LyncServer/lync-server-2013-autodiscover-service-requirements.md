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
ms.openlocfilehash: 4dc50b7eedf6aa815c52b44ed4c1ddb88cea5217
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a>Anforderungen für den AutoErmittlungsdienst für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-25_

Der Microsoft lync Server 2013 AutoErmittlungsdienst wird auf dem Director-und Front-End-Pool-Server ausgeführt und kann, wenn er in DNS veröffentlicht wird, von mobilen Geräten mit lync Mobile zum Auffinden von Mobilitätsdiensten verwendet werden. Bevor Mobile Geräte, auf denen lync Mobile ausgeführt wird, die automatische Ermittlung nutzen können, müssen Sie die Listen alternativer Zertifikatsantrags Teller Namen in allen Directors und Front-End-Server ändern, auf denen der AutoErmittlungsdienst ausgeführt wird. Darüber hinaus kann es erforderlich sein, die Listen Betreff alternativer Namen auf Zertifikaten zu ändern, die für externe Webdienst-Veröffentlichungsregeln für Reverse-Proxies verwendet werden.

Ausführliche Informationen zu den Einträgen für alternative Antragstellernamen, die für Directors, Front-End-Server und Reverse-Proxies erforderlich sind, finden Sie unter [Technical Requirements for Mobility in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.

Die Entscheidung, ob auf Reverseproxys alternative Antragstellernamen verwendet werden sollen, basiert darauf, ob Sie den AutoErmittlungsdienst an Port 80 oder an Port 443 veröffentlichen:

  - **Veröffentlicht auf Port 80**   keine Zertifikat Änderungen sind erforderlich, wenn die erste Abfrage an den AutoErmittlungsdienst über Port 80 erfolgt. Dies liegt daran, dass Mobile Geräte, auf denen lync läuft, extern auf den Reverseproxy auf Port 80 zugreifen und dann an Port 8080 intern an einen Director oder Front-End-Server weitergeleitet werden. Detaillierte Informationen finden Sie im Abschnitt "Anfänglicher AutoErmittlungsprozess über Port 80" weiter unten in diesem Thema.

  - **Veröffentlicht am Port 443**   die Liste der alternativen Antragstellernamen für Zertifikate, die von der Veröffentlichungsregel für externe Webdienste verwendet werden, muss ein *lyncdiscover enthalten.\< sipdomain "\> * -Eintrag für jede SIP-Domäne in Ihrer Organisation.

Das erneute Ausstellen von Zertifikaten mithilfe einer internen Zertifizierungsstelle ist in der Regel ein einfacher Prozess, für öffentliche Zertifikate, die in der Veröffentlichungsregel des Webdiensts verwendet werden, kann das Hinzufügen mehrerer alternativer alternativen Namen teuer werden. Um dieses Problem zu umgehen, unterstützen wir die anfängliche automatische Ermittlungs Verbindung über Port 80, die dann an Port 8080 auf dem Director oder Front-End-Server umgeleitet wird.

Nehmen Sie beispielsweise an, dass ein mobiler Client, auf dem lync Mobile läuft, für die Anmeldung bei lync Server 2013 mit dem automatischen Ermittlungs Feature unter Verwendung von http für die anfängliche Anforderung konfiguriert ist.

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a>Anfänglicher Auto Ermittlungsprozess für mobile Geräte mit Port 80

1.  Mobiles Gerät, auf dem lync Mobile läuft, sucht nach lyncdiscover.contoso.com mithilfe von DNS, wobei ein A-Eintrag vorhanden ist.

2.  Externe DNS gibt die IP-Adresse für die externen Webdienste an den Client zurück.

3.  Mobiles Gerät, auf dem lync http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com Mobile läuft, sendet eine Anforderung an den Reverse-Proxy

4.  Die Webveröffentlichungsregel wird die Anforderung von Port 80 extern an Port 8080 intern überbrücken, um Sie dann an einen Director oder Front-End-Server weiterzuleiten.
    
    Da es sich um eine HTTP- und keine HTTPS-Anforderung handelt, sind keine Änderungen am Zertifikat der Veröffentlichungsregel für externe Webdienste erforderlich, damit der AutoErmittlungsdienst unterstützt wird.

5.  Der AutoErmittlungsdienst gibt die externen Webdienst-URLs (im HTTPS-Format) zurück.

6.  Das Mobile Gerät, auf dem lync Mobile läuft, kann dann erneut eine Verbindung mit dem Reverseproxy an Port 443 herstellen und wird über 4443 an den Mobilitätsdienst umgeleitet, der im Home-Pool des Benutzers läuft.
    
    Da die HTTPS-Abfrage an die externe Webdienste-URL und nicht an die AutoErmittlungsdienst-URL gerichtet ist, ist sie erfolgreich, da das Zertifikat bereits Einträge für alternative Antragstellernamen der externen Webdienste-FQDNs enthält.
    
    In diesem Szenario sind zur Unterstützung der Mobilität keine Zertifikatänderungen erforderlich.
    
    <div>
    

    > [!NOTE]  
    > Wenn der Zielwebserver über ein Zertifikat verfügt, das "lyncdiscover.contoso.com" als alternativen Antragstellernamen enthält:<BR>a.&nbsp;&nbsp;&nbsp;der Webserver antwortet mit einem "Server Hello" und keinem Zertifikat.<BR>b.&nbsp;&nbsp;&nbsp;das Mobile Gerät, auf dem lync Mobile läuft, beendet die Sitzung sofort.<BR>Wenn der Zielwebserver über ein Zertifikat verfügt, das "lyncdiscover.contoso.com" als alternativen Antragstellernamen enthält:<BR>a.&nbsp;&nbsp;&nbsp;der Webserver antwortet mit einem "Server Hello" und einem Zertifikat.<BR>b.&nbsp;&nbsp;&nbsp;mobiles Gerät, auf dem lync Mobile ausgeführt wird, überprüft das Zertifikat und schließt den Hand Shake ab.

    
    </div>

Zur Unterstützung einer anfänglichen Verbindung mit dem AutoErmittlungsdienst über Port 80 auf dem Reverseproxyserver können Sie eine HTTP-Veröffentlichungsregel erstellen, die dem folgenden Beispiel einer Webveröffentlichungsregel für einen Forefront Threat Management Gateway 2010-Reverseproxy ähnelt:

1.  Erstellen Sie eine neue Webveröffentlichungsregel (beispielsweise **Lync Server-AutoErmittlung (HTTP)**).

2.  Geben Sie in **Öffentlicher Name** "lyncdiscover.contoso.com" ein.

3.  Wählen Sie auf der Registerkarte **Bridging** nur die Option zum Überbrücken von Anforderungen von Port 80 zu Port 8080 aus.

4.  Wählen Sie auf der Registerkarte **Authentifizierung** die Option **Keine Authentifizierung** und **Keine direkte Authentifizierung des Clients** aus.

5.  Commit ändert und verschiebt die Regel an den Anfang der Liste der lync-Regeln (zuerst in der Verarbeitungsreihenfolge).

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Mobilität für die Bereitstellung geteilter Domänen

Ein freigegebener SIP-Adressraum, der auch als *geteilte Domäne*bezeichnet wird, oder eine *hybridbereitstellung* ist eine Konfiguration, in der Benutzer über eine lokale Bereitstellung und eine Online Umgebung bereitgestellt werden. Das gewünschte Ergebnis besteht darin, dass ein Benutzer unabhängig davon, wo sich sein Heimatserver befindet (lokal oder Online), sich bei der Bereitstellung anmeldet und zu seinem Standort des Heimat Servers umgeleitet wird. Um dies zu erreichen, wird das Auto Ermittlungs Feature von Microsoft lync Server 2013 verwendet, um den Online Benutzer zur Online Topologie umzuleiten. Konfigurieren Sie dazu die URL (Uniform Resource Locator) der AutoErmittlung mithilfe der lync Server-Verwaltungsshell und der Cmdlets **Get-CsHostingProvider** und **CsHostingProvider**.

Sie müssen folgende bereitgestellte Attribute erfassen und aufzeichnen:

  - Geben Sie im lync Server-Verwaltungsshell
    
        Get-CsHostingProvider

  - Suchen Sie in den Ergebnissen nach dem Onlineanbieter mit dem Attribut**ProxyFQDN**, z. B. "sipfed.online.lync.com".

  - Zeichnen Sie den Wert von "ProxyFQDN" auf.

  - Aktivieren Sie den Partnerverbund in der lokalen lync Server-Systemsteuerung, sodass der Verbund mit dem Onlineanbieter zugelassen ist.

  - Aktivieren Sie den Partnerverbund für den Onlineanbieter. Standardmäßig sind alle Onlinebenutzer für den Domänenverbund aktiviert und können mit allen Domänen kommunizieren.

  - Wenn Sie gesperrte und zulässige Domänen definieren, legen Sie die Domänen fest, die Sie explizit zulassen oder sperren möchten.

  - Für den Onlineverbund müssen Sie Firewallausnahmen, Zertifikate und den DNS-Hosteinträge (A oder AAAA bei Verwendung von IPv6) planen. Außerdem müssen Sie Verbundrichtlinien konfigurieren. Ausführliche Informationen finden Sie unter [Planung für lync Server 2013 und Office Communications Server Partnerverbund](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

