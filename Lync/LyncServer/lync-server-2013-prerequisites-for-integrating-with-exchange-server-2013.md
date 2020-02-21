---
title: 'Lync Server 2013: Voraussetzungen für die Integration in Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3ea70be8c4d431b6231b1cf8e8dc252581643b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Voraussetzungen für die Integration von Microsoft lync Server 2013 und Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-04-22_

Bevor Sie Microsoft lync Server 2013 und Microsoft Exchange Server 2013 integrieren können, müssen Sie sicherstellen, dass alle erforderlichen Schritte ausgeführt wurden. Wie Sie vielleicht erwarten, kann die Integration erst stattfinden, wenn sowohl Exchange 2013 als auch lync Server 2013 vollständig installiert sind und ausgeführt werden. Ausführliche Informationen zum Installieren von Exchange finden Sie in der Dokumentation zur Exchange 2013 Planung [https://go.microsoft.com/fwlink/p/?LinkId=268539](https://go.microsoft.com/fwlink/p/?linkid=268539)und-Bereitstellung unter. Ausführliche Informationen zum Installieren von lync Server 2013 finden Sie in [https://go.microsoft.com/fwlink/p/?LinkId=254806](https://go.microsoft.com/fwlink/p/?linkid=254806)der Dokumentation zur Planung und Bereitstellung unter.

Nachdem die Serverbetriebs bereit sind, müssen Sie sowohl lync Server 2013 als auch Exchange 2013 Server-zu-Server-Authentifizierungszertifikate zuweisen. Diese Zertifikate ermöglichen lync Server und Exchange zum Austausch von Informationen und zur Kommunikation miteinander. Wenn Sie Exchange 2013 installieren, wird ein selbstsigniertes Zertifikat mit dem Namen Exchange Server Authentifizierungszertifikat für Sie erstellt. Dieses Zertifikat, das sich im Zertifikatspeicher des lokalen Computers befindet, sollte für die Server-zu-Server-Authentifizierung in Exchange 2013 verwendet werden. Ausführliche Informationen zum Zuweisen von Zertifikaten in Exchange 2013 finden Sie unter "Konfigurieren des Nachrichtenflusses und des [https://go.microsoft.com/fwlink/p/?LinkId=268540](https://go.microsoft.com/fwlink/p/?linkid=268540)Client Zugriffs" unter.

Für lync Server 2013 können Sie ein vorhandenes lync Server Zertifikat als Server-zu-Server-Authentifizierungszertifikat verwenden. Beispielsweise kann Ihr Standardzertifikat auch als OAuthTokenIssuer-Zertifikat verwendet werden. Lync Server 2013 können Sie ein beliebiges Webserverzertifikat als Zertifikat für die Server-zu-Server-Authentifizierung verwenden, vorausgesetzt:

  - Das Zertifikat enthält den Namen der SIP-Domäne im Betrefffeld.

  - Dasselbe Zertifikat ist als "OAuthTokenIssuer"-Zertifikat auf allen Front-End-Servern konfiguriert.

  - Das Zertifikat ist mindestens 2.048 Bit lang.

Ausführliche Informationen zu Server-zu-Server-Authentifizierungszertifikaten für Microsoft lync Server 2013 finden Sie unter [Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Microsoft lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).

Nachdem die Zertifikate zugewiesen wurden, müssen Sie den AutoErmittlungsdienst auf Exchange 2013 konfigurieren. In Exchange 2013 konfiguriert der AutoErmittlungsdienst Benutzerprofile und bietet Zugriff auf Exchange-Dienste, wenn sich Benutzer am System anmelden. Die Benutzer geben im AutoErmittlungsdienst ihre E-Mail-Adresse und ihr Kennwort ein, und der Dienst stellt ihnen im Gegenzug folgende Informationen bereit:

  - Verbindungsinformationen für die interne und externe Konnektivität mit Exchange 2013.

  - Den Standort des Postfachservers des Benutzers.

  - URLs für Outlook-Features wie etwa Frei/Gebucht-Informationen, Unified Messaging und das Offlineadressbuch.

  - Servereinstellungen für Outlook Anywhere.

Der AutoErmittlungsdienst muss konfiguriert werden, bevor Sie lync Server 2013 und Exchange 2013 integrieren können. Sie können überprüfen, ob der AutoErmittlungsdienst konfiguriert wurde, indem Sie den folgenden Befehl aus dem Exchange-Verwaltungsshell ausführen und den Wert der parameterautodiscoverserviceinternaluri-Eigenschaft überprüfen:

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

Ist dieser Wert leer, müssen Sie dem AutoErmittlungsdienst einen URI zuweisen. Dieser URI sieht in der Regel so aus:

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

Sie können den URI für den AutoErmittlungsdienst zuweisen, indem Sie einem Befehl ähnlich folgendem ausführen:

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

Ausführliche Informationen zum AutoErmittlungsdienst finden Sie unter "Understanding the Auto Ermittlungs [https://go.microsoft.com/fwlink/p/?LinkId=268542](https://go.microsoft.com/fwlink/p/?linkid=268542)Service" unter.

Nachdem Sie den AutoErmittlungsdienst konfiguriert haben, müssen Sie die lync Server Konfigurationseinstellungen für OAuth ändern. Dadurch wird sichergestellt, dass lync Server weiß, wo der AutoErmittlungsdienst zu finden ist. Um die OAuth-Konfigurationseinstellungen in lync Server 2013 zu ändern, führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell aus. Wenn Sie diesen Befehl ausführen, stellen Sie sicher, dass Sie den URI für den AutoErmittlungsdienst auf Ihrem Exchange-Server angeben und dass Sie **autodiscover. svc** verwenden, um auf den Dienst Speicherort zu zeigen, statt **autodiscover. XML** (der auf die vom Dienst verwendete XML-Datei verweist):

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> Der Parameter Identity im vorangehenden Befehl ist optional; Das liegt daran, dass lync Server nur eine einzelne globale Auflistung von OAuth-Konfigurationseinstellungen haben kann. Dies bedeutet unter anderem, dass Sie die Auto Ermittlungs-URL mit dem folgenden leicht vereinfachten Befehl konfigurieren können:<BR>Gruppe-csoauthconfiguration "– ExchangeAutodiscoverUrl"https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"<BR>Wenn Sie mit der Technologie noch nicht so vertraut sind, ist "OAuth" ein Standardautorisierungsprotokoll, das von vielen wichtigen Websites verwendet wird. Bei "OAuth" werden Benutzeranmeldeinformationen und -kennwörter nicht von einem Computer zum anderen übergeben. Stattdessen basieren Authentifizierung und Autorisierung auf dem Austausch von Sicherheitstoken. Diese Token erteilen für einen bestimmte Zeitspanne Zugriff auf einen bestimmten Satz Ressourcen.



</div>

Sie müssen nicht nur den AutoErmittlungsdienst konfigurieren, sondern auch einen DNS-Eintrag für den Dienst erstellen, der auf Ihren Exchange-Server verweist. Wenn sich der AutoErmittlungsdienst beispielsweise unter autodiscover.litwareinc.com befindet, müssen Sie einen DNS-Eintrag für autodiscover.litwareinc.com erstellen, der in den vollqualifizierten Domänennamen Ihres Exchange-Servers aufgelöst wird (beispielsweise ATL-Exchange-001.litwareinc.com).

</div>

<span> </span>

</div>

</div>

</div>

