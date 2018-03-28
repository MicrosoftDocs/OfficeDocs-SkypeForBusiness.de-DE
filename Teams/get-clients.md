---
title: Beziehen von Clients für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/27/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
localization_priority: Normal
description: Hier erfahren Sie, wie Sie die verschiedenen verfügbaren Microsoft Teams-Clients für Web, Desktop (Windows und Mac) und mobile Betriebssysteme (Android, iOS und Windows Phone) verwenden.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61bfc43321433a06eba8196b732f8f12dded0d8d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
<a name="get-clients-for-microsoft-teams"></a>Beziehen von Clients für Microsoft Teams 
===========================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Microsoft Teams-Clients sind für Web, Desktop (Windows und Mac) und mobile Betriebssysteme (Android, iOS und Windows Phone) verfügbar. Alle diese Clients erfordern eine aktive Internetverbindung. Ein Offlinemodus wird nicht unterstützt.

<a name="web-client"></a>Webclient 
----------

WebClient ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) ist ein vollständiger, funktionsfähige Client, der aus einer Vielzahl von Browsern verwendet werden kann. Webclient unterstützt Anruf- und Besprechungen mithilfe von WebRTC, damit es kein Plugin ist oder herunterladen, die zum Ausführen von Teams in einem Webbrowser. Der Browser muss für Drittanbieter-Cookies konfiguriert werden. 

[!INCLUDE [browser-support](includes/browser-support.md)]

Der Webclient führt die Erkennung des Clientbrowsers Version beim Herstellen einer Verbindung mit [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) und eine nicht unterstützte Browserversion erkannt wird, blockieren Sie den Zugriff auf die Weboberfläche und wird empfohlen, dass der Benutzer den Desktopclient oder mobilen app herunterladen.

<a name="desktop-client"></a>Desktop-client
--------------

Der Microsoft-Teams Desktopclient ist eine eigenständige Anwendung und derzeit kein Bestandteil von Office Pro Plus. Teams ist für Windows (7 +), 32-Bit- und 64-Bit-Versionen und Mac OS (10.10. +) verfügbar. Unter Windows-Teams erfordert .NET Framework 4.5 oder höher. Das Installationsprogramm Teams bietet es für Sie installieren, wenn Sie nicht vorhanden ist. 

Desktop-Clients unterstützen Echtzeitkommunikation (Audio-, Video- und Content Freigabe) Team Besprechungen, Gruppe aufrufende und privaten Angebot Anrufe.

Desktop-Clients können heruntergeladen und installiert werden durch Endbenutzer direkt aus [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) Wenn sie die entsprechenden lokalen Berechtigungen verfügen (Administratorrechte ist nicht erforderlich, den Teams-Client auf einem PC zu installieren, aber sind erforderlich für Mac).

IT-Administratoren können ihre bevorzugte Methode für die Verteilung der Installationsdateien an die Computer in ihrer Organisation auswählen, beispielsweise System Center Configuration Manager (Windows) oder Casper Suite (MacOS). Wenn Sie die MSI-Paket für Windows-Verteilung erhalten möchten, finden Sie unter [Installieren von Microsoft-Teams verwenden MSI-Datei](msi-deployment.md).

> [!NOTE]
> Die Verteilung des Clients über diese Mechanismen ist nur für die anfängliche Installation von Microsoft Team-Clients gedacht, nicht für zukünftige Updates.


#### <a name="windows"></a>Windows

Für die Microsoft Teams-Installation unter Windows können Installationsprogramme mit 32-Bit- und 64-Bit-Architektur heruntergeladen werden. Die Architektur sollte mit der des Betriebssystems übereinstimmen und wird beim Onlinedownload standardmäßig ausgewählt.



> [!NOTE]
> Die Architektur (32-Bit oder 64-Bit) von Microsoft Teams ist unabhängig von der Architektur der installierten Office-Version.

Der Windows-Client wird im Ordner „AppData“ im Profil des Benutzers bereitgestellt. Durch die Bereitstellung im lokalen Profil des Benutzers kann der Client installiert werden, ohne dass erhöhte Rechte erforderlich sind. Der Windows-Client wird an den folgenden Speicherorten installiert:

-   %appdata%\\local\\Microsoft\\Teams

-   %appdata%\\roaming\\Microsoft\\Teams

Wenn Benutzer erstmals mit dem Microsoft Teams-Client einen Anruf einleiten, sehen sie möglicherweise eine Warnung mit den Einstellungen der Windows-Firewall, in der sie aufgefordert werden, die Kommunikation zuzulassen. Die Benutzer können angewiesen werden, diese Meldung zu ignorieren, da der Anruf auch dann funktioniert, wenn die Warnung geschlossen wird.

![Screenshot des Dialogfelds „Windows-Sicherheitshinweis“](media/Get_clients_for_Microsoft_Teams_image3.png)


> [!NOTE]
> Die Konfiguration der Windows-Firewall wird auch dann geändert, wenn die Eingabeaufforderung durch Auswählen von „Abbrechen“ geschlossen wird. Zwei eingehende Regeln für „teams.exe“ werden mit der Aktion „Blockieren“ für die Protokolle TCP und UDP erstellt.

#### <a name="mac"></a>Mac

Microsoft stellt auch eine DMG-Installationsdatei für Mac OS X-Computer bereit. Zum Installieren des Mac-Clients ist Administratorzugriff erforderlich. Der Mac OS X-Client wird im Ordner „/Applications“ installiert.


<a name="mobile-clients"></a>Mobile Clients
--------------

Die mobilen Microsoft Teams-Apps sind für Android, iOS und Windows Phone verfügbar und richten sich an Benutzer, die sich unterwegs an chatbasierten Unterhaltungen beteiligen möchten. Peer-zu-Peer-Audioanrufe sind ebenfalls möglich. Sie finden die mobilen Apps im jeweiligen mobilen Store: Google Play, Apple App Store und Microsoft Store.

Unterstützte mobile Plattformen für mobile Microsoft Teams-Apps:

-   **Android**: 4.4 oder höher

-   **iOS**: 10.0 oder höher

-   **Windows Phone**: Windows 10 Mobile

Mobile Apps werden nur über den jeweiligen App Store für ihre mobile Plattform verteilt und aktualisiert. Sie können nicht über MDM-Lösungen (Mobile Device Management, mobile Geräteverwaltung) verteilt oder quergeladen werden.


| | | |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Get_clients_for_Microsoft_Teams_image4.png)      |Entscheidungspunkt         |Gelten Einschränkungen, die Benutzer daran hindern, den entsprechenden Microsoft Teams-Client auf ihren Geräten zu installieren?         |
|![Symbol für „Nächste Schritte“](media/Get_clients_for_Microsoft_Teams_image5.png)     |Nächste Schritte         |Wenn Ihre Organisation Softwareinstallationen einschränkt, stellen Sie sicher, dass dieser Prozess mit Microsoft Teams kompatibel ist. Hinweis: Administratorrechte sind zum Installieren von Clients auf einem PC nicht erforderlich, auf einem Mac jedoch sind sie erforderlich.         |


  <span id="_Hlk477176062" class="anchor"></span>  Entscheidungspunkt   Gelten Einschränkungen, die Benutzer daran hindern, den entsprechenden Microsoft Teams-Client auf ihren Geräten zu installieren?

<a name="client-update-management"></a>Verwaltung von Clientupdates
------------------------

Clients werden zurzeit automatisch vom Microsoft Teams-Dienst aktualisiert, ohne dass der Eingriff eines IT-Administrators erforderlich ist. Wenn ein Update verfügbar ist, lädt der Client das Update automatisch herunter, und wenn sich die App seit einiger Zeit im Leerlauf befindet, wird der Updateprozess gestartet.

<a name="client-side-configurations"></a>Clientseitige Konfigurationen
---------------------------

Zurzeit sind keine unterstützten Optionen zum Konfigurieren des Clients durch den Mandantenadministrator, PowerShell, Gruppenrichtlinienobjekte oder die Registrierung verfügbar.

<a name="notification-settings"></a>Benachrichtigungseinstellungen
----------------------------

Zurzeit sind keine Optionen verfügbar, mit denen IT-Administratoren clientseitige Benachrichtigungseinstellungen konfigurieren können. Alle Benachrichtigungsoptionen werden von den Benutzern festgelegt. Die folgende Abbildung zeigt die Standardclienteinstellungen.

![Screenshot der Benachrichtigungseinstellungen](media/Get_clients_for_Microsoft_Teams_image6.png)
