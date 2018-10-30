---
title: Voraussetzungen für die Integration von Microsoft Lync Server 2013 und Microsoft Exchange Server 2013
TOCTitle: Voraussetzungen für die Integration von Microsoft Lync Server 2013 und Microsoft Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49890989
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Voraussetzungen für die Integration von Microsoft Lync Server 2013 und Microsoft Exchange Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Bevor Sie Microsoft Lync Server 2013 und Microsoft Exchange Server 2013 integrieren können, müssen Sie sicherstellen, dass alle zur Vorbereitung erforderlichen Schritte ausgeführt worden sind. Die Integration kann erwartetermaßen erst stattfinden, nachdem Exchange 2013 und Lync Server 2013 beide vollständig installiert und in Betrieb genommen worden sind. Ausführliche Informationen zum Installieren von Exchange finden Sie in der Planungs- und Bereitstellungsdokumentation zu Exchange 2013 unter [http://go.microsoft.com/fwlink/?linkid=268539\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268539%26clcid=0x407). Ausführliche Informationen zum Installieren von Lync Server 2013 finden Sie in der Planungs- und Bereitstellungsdokumentation unter [http://go.microsoft.com/fwlink/?linkid=254806\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=254806%26clcid=0x407).

Nachdem die Server in Betrieb genommen worden sind, müssen Sie sowohl Lync Server 2013 als auch Exchange 2013 Server-zu-Server-Authentifizierungszertifikate zuweisen. Mithilfe dieser Zertifikate können Lync Server und Exchange Informationen austauschen und miteinander kommunizieren. Wenn Sie Exchange 2013 installieren, wird ein selbstsigniertes Zertifikat namens "Microsoft Exchange Server Auth Certificate" erstellt. Dieses Zertifikat, das sich im Zertifikatspeicher des lokalen Computers befindet, sollten Sie für die Server-zu-Server-Authentifizierung in Exchange 2013 verwenden. Ausführliche Informationen zum Zuweisen von Zertifikaten in Exchange 2013 finden Sie im Artikel "Konfigurieren der Nachrichtenübermittlung und des Clientzugriffs" unter [http://go.microsoft.com/fwlink/?linkid=268540\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268540%26clcid=0x407).

Für Lync Server 2013 können Sie ein vorhandenes Lync Server-Zertifikat als Server-zu-Server-Authentifizierungszertifikat verwenden. Beispielsweise können Sie auch das Standardzertifikat als "OAuthTokenIssuer"-Zertifikat verwenden. Lync Server 2013 lässt die Verwendung eines beliebigen Webserverzertifikats als Zertifikat für die Server-zu-Server-Authentifizierung zu, vorausgesetzt, folgende Kriterien sind erfüllt:

  - Das Zertifikat enthält den Namen der SIP-Domäne im Betrefffeld.

  - Dasselbe Zertifikat ist als "OAuthTokenIssuer"-Zertifikat auf allen Front-End-Servern konfiguriert.

  - Das Zertifikat ist mindestens 2.048\&nbsp;Bit lang.

Ausführliche Informationen zu Server-zu-Server-Authentifizierungszertifikaten für Microsoft Lync Server 2013 finden Sie unter [Zuweisen eines Zertifikats für die Server-zu-Server-Authentifizierung zu Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).

Nachdem die Zertifikate zugewiesen worden sind, müssen Sie den AutoErmittlungsdienst in Exchange 2013 konfigurieren. In Exchange 2013 konfiguriert der AutoErmittlungsdienst Benutzerprofile und gibt Zugriff auf Exchange-Dienste, wenn Benutzer sich am System anmelden. Die Benutzer geben im AutoErmittlungsdienst ihre E-Mail-Adresse und ihr Kennwort ein, und der Dienst stellt ihnen im Gegenzug folgende Informationen bereit:

  - Verbindungsinformationen für die interne und externe Anbindung an Exchange 2013.

  - Den Standort des Postfachservers des Benutzers.

  - URLs für Outlook-Features wie etwa Frei/Gebucht-Informationen, Unified Messaging und das Offlineadressbuch.

  - Servereinstellungen für Outlook Anywhere.

Der AutoErmittlungsdienst muss konfiguriert werden, bevor Lync Server 2013 und Exchange 2013 integriert werden können. Sie können feststellen, ob der AutoErmittlungsdienst konfiguriert worden ist, indem Sie den folgenden Befehl in der Exchange-Verwaltungsshell ausführen und den Wert der **AutoDiscoverServiceInternalUri**-Eigenschaft überprüfen:

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

Ist dieser Wert leer, müssen Sie dem AutoErmittlungsdienst einen URI zuweisen. Dieser URI sieht in der Regel so aus:

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

Sie können den URI für den AutoErmittlungsdienst zuweisen, indem Sie einem Befehl ähnlich folgendem ausführen:

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

Ausführliche Informationen zum AutoErmittlungsdienst finden Sie im Artikel "Grundlegendes zum AutoErmittlungsdienst" unter [http://go.microsoft.com/fwlink/?linkid=268542\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268542%26clcid=0x407).

Nach dem Konfigurieren des AutoErmittlungsdiensts müssen Sie die "OAuth"-Konfigurationseinstellungen von Lync Server ändern. Dadurch wird sichergestellt, dass Lync Server "weiß", wo der AutoErmittlunsdienst zu finden ist. Zum Ändern der "OAuth"-Konfigurationseinstellungen in Lync Server 2013 führen Sie in der Lync Server-Verwaltungsshell den folgenden Befehl aus. Geben Sie beim Ausführen dieses Befehls unbedingt den URI zu dem AutoErmittlungsdienst an, der auf dem Exchange-Server ausgeführt wird, und verwenden Sie zum Verweisen auf den Dienstspeicherort **autodiscover.svc** und nicht **autodiscover.xml** (letzteres zeigt auf die vom Dienst verwendete XML-Datei):

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc


> [!NOTE]
> Der <STRONG>Identity</STRONG>-Parameter im obigen Befehl ist optional. Der Grund hierfür ist, dass Lync Server nur eine einzige, globale Auflistung von "OAuth"-Konfigurationseinstellungen zulässt. Das bedeutet unter anderem, dass Sie die URL für den AutoErmittlungsdienst mithilfe dieses etwas einfacheren Befehls konfigurieren können:<BR><STRONG>Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</STRONG><BR>Wenn Sie mit der Technologie noch nicht so vertraut sind, ist "OAuth" ein Standardautorisierungsprotokoll, das von vielen wichtigen Websites verwendet wird. Bei "OAuth" werden Benutzeranmeldeinformationen und -kennwörter nicht von einem Computer zum anderen übergeben. Stattdessen basieren Authentifizierung und Autorisierung auf dem Austausch von Sicherheitstoken. Diese Token erteilen für einen bestimmte Zeitspanne Zugriff auf einen bestimmten Satz Ressourcen.



Sie müssen nicht nur den AutoErmittlungsdienst konfigurieren, sondern auch einen DNS-Eintrag für den Dienst erstellen, der auf Ihren Exchange-Server zeigt. Wenn der AutoErmittlungsdienst sich beispielsweise unter **autodiscover.litwareinc.com** befindet, müssen Sie einen DNS-Eintrag für **autodiscover.litwareinc.com** erstellen, der zum vollqualifizierten Domänennamen Ihres Exchange-Servers aufgelöst wird (z.\&nbsp;B. **atl-exchange-001.litwareinc.com**).

