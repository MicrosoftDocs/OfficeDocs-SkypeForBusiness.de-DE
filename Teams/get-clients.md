---
title: Beziehen von Clients für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/05/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vichau, majafry
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die verschiedenen verfügbaren Microsoft Teams-Clients für Web, Desktop (Windows und Mac) und mobile Betriebssysteme (Android, iOS und Windows Phone) verwenden.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9caef93f2303458d20c2d7e2142579edaae69748
ms.sourcegitcommit: c864a4b5337960deed01ff8c481326dbbd23c960
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "24975116"
---
<a name="get-clients-for-microsoft-teams"></a>Beziehen von Clients für Microsoft Teams 
===========================

Microsoft-Teams, hat die Clients verfügbar für desktop (Windows und Mac), Web und mobile (Android-, IOS- und Windows Phone). Alle diese Clients erfordern eine aktive Internetverbindung. Ein Offlinemodus wird nicht unterstützt.

<a name="desktop-client"></a>Desktop-client
--------------

> [!Tip]
> Sehen Sie sich die folgenden Sitzung Informationen zu den Vorteilen der Windows-Desktop Client, wie es geplant und wie diese bereitgestellt: [Teams Windows Desktop Client](https://aka.ms/teams-clients)

Der Microsoft-Teams Desktopclient ist eine eigenständige Anwendung und derzeit kein Bestandteil von Office 365 ProPlus. Teams ist für Windows (7 +), 32-Bit- und 64-Bit-Versionen und Mac OS (10.10. +) verfügbar. Unter Windows-Teams erfordert .NET Framework 4.5 oder höher. Das Installationsprogramm Teams bietet es für Sie installieren, wenn Sie nicht vorhanden ist. 

Desktop-Clients unterstützen Echtzeitkommunikation (Audio-, Video- und Content Freigabe) Team Besprechungen, Gruppe aufrufende und privaten Angebot Anrufe.

Desktop-Clients können heruntergeladen und installiert werden durch Endbenutzer direkt aus [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) Wenn sie die entsprechenden lokalen Berechtigungen verfügen (Administratorrechte ist nicht erforderlich, den Teams-Client auf einem PC zu installieren, aber sind erforderlich für Mac).

IT-Administratoren können ihre bevorzugte Methode zum Verteilen der Installationsdateien auf Computern in ihrer Organisation, beispielsweise von System Center Configuration Manager (Windows) oder Jamf Pro (Mac OS) auswählen. Wenn das MSI-Paket für die Windows-Verteilung erhalten möchten, finden Sie unter [Installieren von Microsoft-Teams verwenden MSI-Datei](msi-deployment.md).

> [!NOTE]
> Die Verteilung des Clients über diese Mechanismen ist nur für die anfängliche Installation von Microsoft Team-Clients gedacht, nicht für zukünftige Updates.

### <a name="windows"></a>Windows

Die Microsoft-Teams, Installation für Windows bietet herunterladbare Installer in 32-Bit- und 64-Bit-Architektur.

> [!NOTE]
> Die Architektur (32-Bit im Vergleich zu 64-Bit) von Microsoft-Teams, ist der Architektur von Windows und Office-Installation unabhängig.

Der Windows-Client wird in den Anwendungsdaten-Ordner befindet sich im Profil des Benutzers bereitgestellt. Bereitstellen von lokalen Profil des Benutzers ermöglicht dem Client installiert werden soll, ohne dass mit erhöhten Rechten Rechte. Der Windows-Client nutzt die folgenden Speicherorten:

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingsAddin

- Anwendungsdaten %\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

Wenn Benutzer einen Anruf über den Client für Microsoft-Teams zum ersten Mal starten, bemerken sie möglicherweise eine Warnung mit den Einstellungen der Windows-Firewall mit der Aufforderung für Benutzer, um die Kommunikation zu ermöglichen. Benutzer möglicherweise aufgefordert, diese Meldung ignorieren, da der Anruf wird arbeiten, auch wenn die Warnung geschlossen wird.

![Screenshot des Dialogfelds „Windows-Sicherheitshinweis“](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> Die Konfiguration der Windows-Firewall wird auch dann geändert, wenn die Eingabeaufforderung durch Auswählen von „Abbrechen“ geschlossen wird. Zwei eingehende Regeln für „teams.exe“ werden mit der Aktion „Blockieren“ für die Protokolle TCP und UDP erstellt.

### <a name="mac"></a>Mac

Mac-Benutzer können Teams mithilfe einer Installation Paketdatei für Mac OS-Computer installieren. Zum Installieren des Mac-Clients ist Administratorzugriff erforderlich. Mac OS-Client wird in den Ordner/Programme installiert.

#### <a name="install-teams-by-using-the-pkg-file"></a>Installieren von Teams mithilfe der Paketdatei

1. Die [Downloadseite für Teams](https://teams.microsoft.com/downloads)unter **Mac**, klicken Sie auf **herunterladen**.
2. Klicken Sie mit der Doppelklicken auf die Paketdatei.
3. Führen Sie den Installations-Assistenten, um die Installation abzuschließen.
4. Teams werden Ordner/Programme installiert werden. Es ist eine computerweiten-Installation.

> [!NOTE]
> Während der Installation werden die PKG-Admin-Anmeldeinformationen aufgefordert. Der Benutzer muss die Administratoranmeldeinformationen, unabhängig davon, ob der Benutzer Administrator ist eingeben

Wenn ein Benutzer derzeit eine DMG-Installation von Teams hat und Ersetzen Sie es mit der Installation PKG möchte, sollte der Benutzer:

1. Beenden Sie die app Teams.
2. Deinstallieren Sie die app Teams.
3. Installieren der Paketdatei.

Verwaltete Bereitstellung von Teams können IT-Administratoren die Installationsdateien alle Macs in ihrer Organisation, beispielsweise Jamf Pro verteilen.

> [!NOTE]
> Wenn Sie Probleme beim Installieren von der PKG auftreten, wollen wir uns kennen. Klicken Sie im Bereich am Ende dieses Artikels **Feedback** auf **Feedback zum Produkt**.

<a name="web-client"></a>Webclient 
----------

WebClient ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) ist ein vollständiger, funktionsfähige Client, der aus einer Vielzahl von Browsern verwendet werden kann. Webclient unterstützt Anruf- und Besprechungen mithilfe von WebRTC, damit es kein Plugin ist oder herunterladen, die zum Ausführen von Teams in einem Webbrowser. Der Browser muss für Drittanbieter-Cookies konfiguriert werden. 

[!INCLUDE [browser-support](includes/browser-support.md)]

Der Webclient führt die Erkennung des Clientbrowsers Version beim Herstellen einer Verbindung mit [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753). Wenn eine nicht unterstützte Browserversion erkannt wurde, wird es blockieren Sie den Zugriff auf die Weboberfläche und wird empfohlen, dass der Benutzer den Desktopclient oder mobilen app herunterladen.

<a name="mobile-clients"></a>Mobile Clients
--------------

Die mobilen Microsoft Teams-Apps sind für Android, iOS und Windows Phone verfügbar und richten sich an Benutzer, die sich unterwegs an chatbasierten Unterhaltungen beteiligen möchten. Peer-zu-Peer-Audioanrufe sind ebenfalls möglich. Sie finden die mobilen Apps im jeweiligen mobilen Store: Google Play, Apple App Store und Microsoft Store.

Unterstützte mobile Plattformen für mobile Microsoft Teams-Apps:

-   **Android**: 4.4 oder höher

-   **iOS**: 10.0 oder höher

> [!NOTE]
> Die mobile Version muss an die Öffentlichkeit in Reihenfolge für Teams erwartungsgemäß verfügbar sein.

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
