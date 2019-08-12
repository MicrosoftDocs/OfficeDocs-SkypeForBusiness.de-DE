---
title: Beziehen von Clients für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die verschiedenen verfügbaren Microsoft Teams-Clients für Web, Desktop (Windows und Mac) und mobile Betriebssysteme (Android und iOS) verwenden.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 47341662267a3da0a83174cbccb2b2cd251538b6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245753"
---
<a name="get-clients-for-microsoft-teams"></a>Beziehen von Clients für Microsoft Teams 
===========================

Microsoft Teams-Clients sind für Desktop (Windows und Mac), Web und mobile Betriebssysteme (Android und iOS) verfügbar. Alle diese Clients erfordern eine aktive Internetverbindung. Ein Offlinemodus wird nicht unterstützt.

> [!NOTE]
> Ab dem 29. November 2018 können Sie die Microsoft Teams for Windows 10 S-App (Vorschau), die im Microsoft Store verfügbar ist, nicht mehr verwenden. Stattdessen können Sie nun den Teams-Desktopclient auf Geräte herunterladen und installieren, die mit Windows 10 S-Modus betrieben werden. Den Desktopclient zum Herunterladen finden Sie unter [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754). MSI-Builds des Teams-Desktopclients stehen für Geräte, die mit Windows 10 S-Modus betrieben werden, derzeit noch nicht zur Verfügung.
>
> Weitere Informationen zum Windows 10 S-Modus finden Sie unter [Einführung in den Windows 10-Modus](https://www.microsoft.com/windows/s-mode). 

<a name="desktop-client"></a>Desktopclient
--------------

> [!Tip]
> Schauen Sie sich die folgende Sitzung mit Informationen zu den Vorteilen des Windows-Desktopclient sowie zum Planen und Bereitstellen der Lösung an: [Windows-Desktopclient für Teams](https://aka.ms/teams-clients)

Der Microsoft Teams-Desktopclient ist eine eigenständige Anwendung und auch [in Office 365 ProPlus verfügbar](https://docs.microsoft.com/de-DE/deployoffice/teams-install). Teams ist für die 32-Bit- und 64-Bit-Versionen von Windows (7+) und für macOS (10.10+) verfügbar. Unter Windows erfordert Teams .NET Framework 4.5 oder höher. Das Installationsprogramm für Teams bietet die Installation an, wenn Sie nicht darüber verfügen. 

Die Desktopclients bieten Unterstützung für Echtzeitkommunikation (Audio, Video und Inhaltsfreigabe) für Teambesprechungen, Gruppenanrufe und private Einzelanrufe.

Desktopclients können unter [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) von Endbenutzern direkt heruntergeladen und installiert werden, sofern sie über die entsprechenden lokalen Berechtigungen verfügen (Administratorrechte sind zum Installieren des Teams-Clients auf einem PC nicht erforderlich, auf einem Mac jedoch sind sie erforderlich).

IT-Administratoren können ihre bevorzugte Methode für die Verteilung der Installationsdateien an die Computer in ihrer Organisation auswählen, beispielsweise System Center Configuration Manager (Windows) oder Jamf Pro (macOS). Informationen dazu, wie Sie das MSI-Paket für die Verteilung von Windows erhalten, finden Sie unter [Installieren von Microsoft Teams mithilfe eines MSI-Pakets](msi-deployment.md).  

> [!NOTE]
> Die Verteilung des Clients über diese Mechanismen ist nur für die anfängliche Installation von Microsoft Team-Clients gedacht, nicht für zukünftige Updates.

### <a name="windows"></a>Windows

Die Installation von Microsoft Teams für Windows bietet herunterladbare Installationsprogramme in der 32-Bit- und 64-Bit-Architektur.

> [!NOTE]
> Die Architektur (32 Bit oder 64 Bit) von Microsoft Teams ist unabhängig von der Architektur der installierten Windows- und Office-Version.

Der Windows-Client wird im Ordner „AppData“ im Profil des Benutzers bereitgestellt. Durch das Bereitstellen im lokalen Profil des Benutzers kann der Client ohne erweiterte Berechtigungen installiert werden. Der Windows-Client nutzt die folgenden Speicherorte:

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingsAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

Wenn Benutzer erstmals mit dem Microsoft Teams-Client einen Anruf einleiten, sehen sie möglicherweise eine Warnung mit den Einstellungen der Windows-Firewall, in der sie aufgefordert werden, die Kommunikation zuzulassen. Die Benutzer können angewiesen werden, diese Meldung zu ignorieren, da der Anruf auch dann funktioniert, wenn die Warnung geschlossen wird.

![Screenshot des Dialogfelds „Windows-Sicherheitshinweis“](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> Die Konfiguration der Windows-Firewall wird auch dann geändert, wenn die Eingabeaufforderung durch Auswählen von „Abbrechen“ geschlossen wird. Zwei eingehende Regeln für „teams.exe“ werden mit der Aktion „Blockieren“ für die Protokolle TCP und UDP erstellt.

### <a name="mac"></a>Mac

Mac-Benutzer können Teams mit einer PKG-Installationsdatei für macOS-Computer installieren. Administratorzugriff ist erforderlich, um den Mac-Client zu installieren. Der macOS-Client wird im Ordner „/Programme“ installiert.

#### <a name="install-teams-by-using-the-pkg-file"></a>Installieren von Teams mithilfe der PKG-Datei

1. Klicken Sie auf der [Teams-Downloadseite](https://teams.microsoft.com/downloads) unter **Mac** auf **Herunterladen**.
2. Doppelklicken Sie auf die PKG-Datei.
3. Folgen Sie zum Durchführen der Installation den Anweisungen im Installations-Assistenten.
4. Teams werden im Ordner „/Programme“ installiert. Es handelt sich um eine computerweite Installation.

> [!NOTE]
> Während der Installation fordert die PKG-Datei den Benutzer zur Eingabe von Administratoranmeldeinformationen auf. Der Benutzer muss die Administratoranmeldeinformationen eingeben, unabhängig davon, ob er ein Administrator ist oder nicht.

Wenn ein Benutzer aktuell über eine DMG-Installation von Teams verfügt und sie durch die PKG-Installation ersetzen möchte, sollte der Benutzer:

1. Die Teams-App beenden.
2. Die Teams-App deinstallieren.
3. Die PKG-Datei installieren.

IT-Administratoren können die verwaltete Bereitstellung von Teams für die Verteilung der Installationsdateien auf allen Macs in ihrer Organisation verwenden, z. B. Jamf Pro.

> [!NOTE]
> Wenn Probleme beim Installieren der PKG-Datei auftreten, lassen Sie es uns wissen. Klicken Sie im Abschnitt **Feedback** am Ende dieses Artikels auf **Produktfeedback**.

<a name="web-client"></a>Webclient 
----------

Beim Webclient ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) handelt es sich um einen vollständig funktionsfähigen Client, der in einer Vielzahl von Browsern verwendet werden kann. Der Webclient unterstützt Anrufe und Besprechungen mit WebRTC, es ist also kein Plug-In oder Download erforderlich, um Teams in einem Webbrowser ausführen. Der Browser muss so konfiguriert sein, dass Drittanbietercookies zulässig sind. 

[!INCLUDE [browser-support](includes/browser-support.md)]

Der Webclient führt beim Herstellen einer Verbindung mit [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) eine Ermittlung der Browserversion durch. Wenn eine nicht unterstützte Browserversion erkannt wird, wird der Zugriff auf die Webschnittstelle blockiert, und dem Benutzer wird empfohlen, den Desktopclient oder die mobile App herunterzuladen.

<a name="mobile-clients"></a>Mobile Clients
--------------

Die Microsoft Teams-Apps für Mobilgeräte stehen für Android und iOS zur Verfügung und sind auf mobile Benutzer ausgelegt, die an Chat-basierten Unterhaltungen teilnehmen. Außerdem ermöglichen sie Peer-to-Peer-Audioanrufe. Rufen Sie den entsprechenden Store für mobile Apps – Google Play oder Apple App Store – auf, um die Apps herunterzuladen. Die Windows Phone-App wurde am 20. Juli 2018 eingestellt und funktioniert möglicherweise nicht mehr. 

Unterstützte mobile Plattformen für mobile Microsoft Teams-Apps:

-   **Android**: 4.4 oder höher

-   **iOS**: 10.0 oder höher

> [!NOTE]
> Die mobile Version muss der Öffentlichkeit zur Verfügung stehen, damit Teams wie erwartet funktioniert.

Mobile Apps werden nur über den jeweiligen App Store für ihre mobile Plattform verteilt und aktualisiert. Sie können nicht über MDM-Lösungen (Mobile Device Management, mobile Geräteverwaltung) verteilt oder quergeladen werden.


| | | |
|---------|---------|---------|
|![Ein Symbol, das einen Entscheidungspunkt darstellt](media/Get_clients_for_Microsoft_Teams_image4.png)      |Entscheidungspunkt         |Gelten Einschränkungen, die Benutzer daran hindern, den entsprechenden Microsoft Teams-Client auf ihren Geräten zu installieren?         |
|![Ein Symbol, das die nächsten Schritte darstellt](media/Get_clients_for_Microsoft_Teams_image5.png)     |Nächste Schritte         |Wenn Ihre Organisation Softwareinstallationen einschränkt, stellen Sie sicher, dass dieser Prozess mit Microsoft Teams kompatibel ist. Hinweis: Administratorrechte sind zum Installieren von Clients auf einem PC nicht erforderlich, auf einem Mac jedoch sind sie erforderlich.         |

<a name="client-update-management"></a>Verwaltung von Clientupdates
------------------------

Clients werden aktuell vom Microsoft Teams-Dienst aktualisiert, ohne dass ein IT-Administrator eingreifen muss. Wenn ein Update verfügbar ist, wird der Client das Update automatisch herunterladen und wenn die App für einen bestimmten Zeitraum nicht verwendet wurde, beginnt der Updatevorgang.

<a name="client-side-configurations"></a>Clientseitige Konfigurationen
---------------------------

Zurzeit sind keine unterstützten Optionen zum Konfigurieren des Clients durch den Mandantenadministrator, PowerShell, Gruppenrichtlinienobjekte oder die Registrierung verfügbar.

<a name="notification-settings"></a>Benachrichtigungseinstellungen
----------------------------

Zurzeit sind keine Optionen verfügbar, mit denen IT-Administratoren clientseitige Benachrichtigungseinstellungen konfigurieren können. Alle Benachrichtigungsoptionen werden von den Benutzern festgelegt. Die folgende Abbildung zeigt die Standardclienteinstellungen.

![Screenshot der Benachrichtigungseinstellungen](media/Get_clients_for_Microsoft_Teams_image6.png)

<a name="sample-powershell-script"></a>PowerShell-Beispielskript
----------------------------

Dieses Beispielskript, das auf Clientcomputern im Kontext eines Administratorkontos mit erweiterten Berechtigungen ausgeführt werden muss, erstellt eine neue eingehende Firewallregel für jeden Benutzerordner unter C:\Users. Wenn Teams diese Regel findet, kann sie verhindern, dass die Teams-Anwendung Benutzer zum Erstellen von Firewallregeln auffordert, wenn der Benutzer seinen ersten Aufruf über Teams tätigt. 

```

<#
.Synopsis
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($users.Length -gt 0)
{
    foreach ($user in $users)
    {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath)
        {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue))
            {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}

```
