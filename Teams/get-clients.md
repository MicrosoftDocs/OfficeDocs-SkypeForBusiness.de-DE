---
title: "Beziehen von Clients für Microsoft Teams | Microsoft-Support"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Hier erfahren Sie, wie Sie die verschiedenen verfügbaren Microsoft Teams-Clients für Web, Desktop (Windows und Mac) und mobile Betriebssysteme (Android, iOS und Windows Phone) verwenden."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 6a1dea833a96781ae89ffb8f822e96b3e8636371
ms.sourcegitcommit: 8cc7856bb7c305e0e96a4178535b1570cbfc3694
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2017
---
<a name="get-clients-for-microsoft-teams"></a>Beziehen von Clients für Microsoft Teams 
===========================

Microsoft Teams-Clients sind für Web, Desktop (Windows und Mac) und mobile Betriebssysteme (Android, iOS und Windows Phone) verfügbar. Alle diese Clients erfordern eine aktive Internetverbindung. Ein Offlinemodus wird nicht unterstützt.

<a name="web-client"></a>Webclient 
----------------

Beim Webclient ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) handelt es sich um einen vollständigen funktionsfähigen Client, der in einer Vielzahl von Browsern verwendet werden kann. Zurzeit unterstützt der Webclient keine Echtzeitkommunikation (das heißt Teilnehmen an Besprechungen und Tätigen von Einzelanrufen). Außerdem muss der Browser so konfiguriert sein, dass Drittanbietercookies zulässig sind.

Zum Nutzen von Microsoft Teams in einem Webbrowser ist kein Plug-In oder Download erforderlich.

Der Webclient erkennt die Browserversion beim Herstellen der Verbindung mit [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753). Wenn eine nicht unterstützte Browserversion erkannt wird, wird der Zugriff auf die Webschnittstelle blockiert, und dem Benutzer wird empfohlen, den Desktopclient oder die mobile App herunterzuladen.

Microsoft Teams unterstützt die folgenden Browser und Versionen:

-   **Microsoft Edge**: 12+

-   **Internet Explorer:** 11+

-   **Chrome**: 51.0+

-   **Firefox**: 47.0+


| | |
|---------|---------|
|![Symbol für „Wichtig“](media/Get_clients_for_Microsoft_Teams_image1.png)<br></br>Wichtig     |Safari wird noch nicht unterstützt, die Unterstützung kommt jedoch bald.         |

<a name="desktop-clients"></a>Desktopclients
------------------------

Beim Microsoft Teams-Desktopclient handelt es sich um eine eigenständige Anwendung, die zurzeit nicht Bestandteil von Office Pro Plus ist. Microsoft Teams ist für die 32-Bit- und 64-Bit-Versionen von Windows (7+) sowie für MacOS (10.10+) verfügbar.

Die Desktopclients bieten Unterstützung für Echtzeitkommunikation (Audio, Video und Inhaltsfreigabe) für Teambesprechungen, Gruppenanrufe und private Einzelanrufe.

Desktopclients können unter [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) von Endbenutzern direkt heruntergeladen und installiert werden, sofern sie über die entsprechenden lokalen Berechtigungen verfügen (Administratorrechte sind zum Installieren des Teams-Clients auf einem PC nicht erforderlich, auf einem Mac jedoch sind sie erforderlich).

IT-Administratoren können ihre bevorzugte Methode für die Verteilung der Installationsdateien an die Computer in ihrer Organisation auswählen, beispielsweise System Center Configuration Manager (Windows) oder Casper Suite (MacOS).


| | |
|---------|---------|
|![Hinweissymbol](media/Get_clients_for_Microsoft_Teams_image2.png)<br></br>Hinweis    |Die Verteilung des Clients über diese Mechanismen ist nur für die anfängliche Installation von Microsoft Team-Clients gedacht, nicht für zukünftige Updates.         |

#### <a name="windows"></a>Windows

Für die Microsoft Teams-Installation unter Windows können Installationsprogramme mit 32-Bit- und 64-Bit-Architektur heruntergeladen werden. Die Architektur sollte mit der des Betriebssystems übereinstimmen und wird beim Onlinedownload standardmäßig ausgewählt.

| | |
|---------|---------|
|![Hinweissymbol](media/Get_clients_for_Microsoft_Teams_image2.png)<br></br>Hinweis    |Die Architektur (32-Bit oder 64-Bit) von Microsoft Teams ist unabhängig von der Architektur der installierten Office-Version.        |

Der Windows-Client wird im Ordner „AppData“ im Profil des Benutzers bereitgestellt. Durch die Bereitstellung im lokalen Profil des Benutzers kann der Client installiert werden, ohne dass erhöhte Rechte erforderlich sind. Der Windows-Client wird an den folgenden Speicherorten installiert:

-   %appdata%\\local\\Microsoft\\Teams

-   %appdata%\\roaming\\Microsoft\\Teams

Wenn Benutzer erstmals mit dem Microsoft Teams-Client einen Anruf einleiten, sehen sie möglicherweise eine Warnung mit den Einstellungen der Windows-Firewall, in der sie aufgefordert werden, die Kommunikation zuzulassen. Die Benutzer können angewiesen werden, diese Meldung zu ignorieren, da der Anruf auch dann funktioniert, wenn die Warnung geschlossen wird.

![Screenshot des Dialogfelds „Windows-Sicherheitshinweis“](media/Get_clients_for_Microsoft_Teams_image3.png)

| | |
|---------|---------|
|![Hinweissymbol](media/Get_clients_for_Microsoft_Teams_image2.png)<br></br>Hinweis    |Die Konfiguration der Windows-Firewall wird auch dann geändert, wenn die Eingabeaufforderung durch Auswählen von „Abbrechen“ geschlossen wird. Zwei eingehende Regeln für „teams.exe“ werden mit der Aktion „Blockieren“ für die Protokolle TCP und UDP erstellt.        |

#### <a name="mac"></a>Mac

Microsoft stellt auch eine DMG-Installationsdatei für Mac OS X-Computer bereit. Zum Installieren des Mac-Clients ist Administratorzugriff erforderlich. Der Mac OS X-Client wird an den folgenden Speicherorten installiert:

\~/Library/Application Support/Microsoft/Teams

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
