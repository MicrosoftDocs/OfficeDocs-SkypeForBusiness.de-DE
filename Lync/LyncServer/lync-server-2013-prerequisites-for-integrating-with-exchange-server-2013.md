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
ms.openlocfilehash: 1a381f765c9c91e9c5e218d66320d542a11bf878
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Voraussetzungen für die Integration von Microsoft lync Server 2013 und Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-04-22_

Bevor Sie Microsoft lync Server 2013 und Microsoft Exchange Server 2013 integrieren können, müssen Sie sicherstellen, dass alle erforderlichen Schritte abgeschlossen sind. Wie Sie vielleicht erwarten, kann die Integration erst dann erfolgen, wenn Exchange 2013 und lync Server 2013 vollständig installiert sind und ausgeführt werden. Details zur Installation von Exchange finden Sie in [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539)der Dokumentation zur Planung und Bereitstellung von Exchange 2013 unter. Details zur Installation von lync Server 2013 finden Sie in [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806)der Dokumentation zur Planung und Bereitstellung unter.

Nachdem die Server eingerichtet und ausgeführt wurden, müssen Sie Server-zu-Server-Authentifizierungszertifikate sowohl für lync Server 2013 als auch Exchange 2013 zuweisen. Mithilfe dieser Zertifikate können lync Server und Exchange Informationen austauschen und miteinander kommunizieren. Wenn Sie Exchange 2013 installieren, wird ein selbstsigniertes Zertifikat mit dem Namen Microsoft Exchange Server auth-Zertifikat für Sie erstellt. Dieses Zertifikat, das sich im Zertifikatspeicher des lokalen Computers befindet, sollte für die Server-zu-Server-Authentifizierung in Exchange 2013 verwendet werden. Details zum Zuweisen von Zertifikaten in Exchange 2013 finden Sie unter "Konfigurieren des Nachrichtenflusses und des Client [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540)Zugriffs" unter.

Für lync Server 2013 können Sie ein vorhandenes lync Server-Zertifikat als Server-zu-Server-Authentifizierungszertifikat verwenden. Beispielsweise kann Ihr Standardzertifikat auch als OAuthTokenIssuer-Zertifikat verwendet werden. Mit lync Server 2013 können Sie ein beliebiges Webserverzertifikat als Zertifikat für die Server-zu-Server-Authentifizierung verwenden, vorausgesetzt, dass:

  - Das Zertifikat enthält den Namen der SIP-Domäne im Feld „Betreff“.

  - Dasselbe Zertifikat ist als „OAuthTokenIssuer“-Zertifikat auf allen Front-End-Servern konfiguriert.

  - Das Zertifikat hat eine Länge von mindestens 2048 Bits.

Details zu Server-zu-Server-Authentifizierungszertifikaten für Microsoft lync Server 2013 finden Sie unter [Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Microsoft lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).

Nachdem die Zertifikate zugewiesen wurden, müssen Sie den AutoErmittlungsdienst in Exchange 2013 konfigurieren. In Exchange 2013 konfiguriert der AutoErmittlungsdienst Benutzerprofile und bietet Zugriff auf Exchange-Dienste, wenn Benutzer sich am System anmelden. Die Benutzer geben im AutoErmittlungsdienst ihre E-Mail-Adresse und ihr Kennwort ein, und der Dienst stellt ihnen im Gegenzug folgende Informationen bereit:

  - Verbindungsinformationen für interne und externe Verbindungen zu Exchange 2013.

  - Den Standort des Postfachservers des Benutzers.

  - URLs für Outlook-Features wie etwa Frei/Gebucht-Informationen, Unified Messaging und das Offlineadressbuch.

  - Servereinstellungen für Outlook Anywhere.

Der AutoErmittlungsdienst muss konfiguriert sein, bevor Sie lync Server 2013 und Exchange 2013 integrieren können. Sie können überprüfen, ob der AutoErmittlungsdienst konfiguriert wurde, indem Sie den folgenden Befehl aus der Exchange-Verwaltungsshell ausführen und den Wert der AutoDiscoverServiceInternalUri-Eigenschaft überprüfen:

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

Wenn dieser Wert leer ist, müssen Sie dem AutoErmittlungsdienst einen URI zuweisen. Dieser URI sieht in der Regel so aus:

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

Sie können den URI für den AutoErmittlungsdienst zuweisen, indem Sie einen Befehl wie den folgenden ausführen:

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

Details zum AutoErmittlungsdienst finden Sie unter "Grundlegendes zum Auto Ermittlungs [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542)Dienst" unter.

Nachdem der AutoErmittlungsdienst konfiguriert wurde, müssen Sie die lync Server OAuth-Konfigurationseinstellungen ändern. Dadurch wird sichergestellt, dass lync Server weiß, wo der AutoErmittlungsdienst zu finden ist. Führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell aus, um die OAuth-Konfigurationseinstellungen in lync Server 2013 zu ändern. Wenn Sie diesen Befehl ausführen, stellen Sie sicher, dass Sie den URI für den AutoErmittlungsdienst angeben, der auf Ihrem Exchange-Server ausgeführt wird, und dass Sie **autodiscover. svc** verwenden, um auf den Dienst Speicherort zu verweisen, anstatt auf **autodiscover. XML** (der auf die vom Dienst verwendete XML-Datei verweist):

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> Der Parameter Identity im vorhergehenden Befehl ist optional; Das liegt daran, dass lync Server Ihnen nur eine einzige globale Sammlung von OAuth-Konfigurationseinstellungen ermöglicht. Das bedeutet unter anderem, dass Sie die URL für den AutoErmittlungsdienst mit diesem etwas einfacheren Befehl konfigurieren können:<BR>Satz-CsOAuthConfiguration – ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"<BR>Wenn Sie mit der Technologie noch nicht so vertraut sind, ist „OAuth“ ein Standardautorisierungsprotokoll, das von vielen wichtigen Websites verwendet wird. Bei „OAuth“ werden Benutzeranmeldeinformationen und -kennwörter nicht von einem Computer zum anderen übergeben. Stattdessen basieren Authentifizierung und Autorisierung auf dem Austausch von Sicherheitstokens. Diese Tokens erteilen für einen bestimmte Zeitspanne Zugriff auf einen bestimmten Satz von Ressourcen.



</div>

Zusätzlich zum Konfigurieren des AutoErmittlungsdiensts müssen Sie auch einen DNS-Eintrag für den Dienst erstellen, der auf Ihren Exchange-Server verweist. Wenn sich der AutoErmittlungsdienst beispielsweise unter autodiscover.litwareinc.com befindet, müssen Sie einen DNS-Eintrag für autodiscover.litwareinc.com erstellen, der in den vollqualifizierten Domänennamen Ihres Exchange-Servers aufgelöst wird (beispielsweise ATL-Exchange-001.litwareinc.com).

</div>

<span> </span>

</div>

</div>

</div>

