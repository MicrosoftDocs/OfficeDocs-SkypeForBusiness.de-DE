---
title: Verwenden von OneDrive for Business und SharePoint Online für Sitzungsaufzeichnungen
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie in Microsoft Teams von Stream zu OneDrive for Business und zum Aufzeichnungsspeicher von SharePoint-Besprechungen wechseln.
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c53cc427c1db87a2d0296384d5d0c67e7e7996a
ms.sourcegitcommit: d34dbdc2f71f3d024cb7f1856fc0f8bbc701f66d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2021
ms.locfileid: "53506324"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>Verwenden von OneDrive for Business und SharePoint Online oder Stream für Besprechungsaufzeichnungen

> [!Note]
> Der Wechsel von Microsoft Stream zu OneDrive for Business und Microsoft SharePoint Online für Besprechungsaufzeichnungen erfolgt schrittweise.

|<div style="width:290px">Datum&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Ereignis&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|5. Oktober 2020<br> *(Abgeschlossen)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Sie aktivieren die Richtlinie für Teams-Besprechungen so, dass Besprechungsaufzeichnungen auf OneDrive for Business und SharePoint Online statt in Microsoft Stream (klassisch) gespeichert werden.|
|Einführung ab dem 7. Januar 2021<br> *(Abgeschlossen)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Alle neuen Teams-Besprechungsaufzeichnungen werden auf OneDrive for Business und SharePoint Online gespeichert, es sei denn, Sie verzögern diese Änderung, indem Sie die Richtlinien für Teams-Besprechungen in Ihrer Organisation ändern und diese explizit auf **Stream-Besprechung** festlegen. Es reicht nicht aus, die Richtlinienberichte als Stream zu sehen. Sie müssen den Richtlinienwert explizit auf **Stream** festlegen.|
|Einführung ab dem 11. Januar 2021<br> *(Abgeschlossen)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Nur GCC**<br> GCC-Kunden können die Option zwar ab dem 5. Oktober deaktivieren können, Sie können Sie jedoch nicht aktivieren. Dieses Feature wird ab dem 11. Januar 2021 für alle GCC-Kunden zur Verfügung stellen, sofern Sie das Feature nicht deaktivieren.<br>  <br>Ab 11. Januar 2021 werden alle neuen Teams-Besprechungsaufzeichnungen für GCC-Kunden auf OneDrive for Business und SharePoint Online gespeichert, es sei denn, Sie verzögern diese Änderung, indem Sie die Richtlinien für Teams-Besprechungen in Ihrer Organisation ändern und diese explizit auf **Stream-Besprechung** festlegen. <br><br>Wenn Sie das Feature deaktiviert haben, es nun aber aktivieren möchten, können Sie dazu Ihre Richtlinie für Teams-Besprechungen explizit auf **OneDrive for Business** setzen. |
|Einführung ab dem 1. März 2021 <br> *(Abgeschlossen)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC High und DoD**<br> Kunden können nun zum ersten Mal Cloud-Besprechungsaufzeichnungen in Microsoft Teams aktivieren. Diese Aufzeichnungen werden standardmäßig auf OneDrive und SharePoint Online gespeichert und abgespielt. |
|Einführung ab dem 7. Juli 2021 <br> *(Abgeschlossen)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Alle Kunden (Enterprise, Education und GCC)**<br> Für eine Teams-Besprechung, die auf OneDrive und SharePoint Online aufgezeichnet und während der Besprechung auch live transkribiert wurde, können Sie jetzt in Microsoft Search suchen, um die Aufzeichnungsdatei der Besprechung, basierend auf dem Transkript, zu finden. |
|Inkrementelle Einführung ab dem 16. August 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Alle Kunden (Enterprise, Education und GCC)**<br>Es können keine neuen Besprechungsaufzeichnungen in Microsoft Stream (klassisch) gespeichert werden. Bei allen Kunden werden Besprechungsaufzeichnungen automatisch auf OneDrive for Business und SharePoint Online gespeichert, selbst wenn sie ihre Teams-Besprechungsrichtlinien in "Stream" geändert haben.<br><br> Um den Wandel in Ihrem Unternehmen besser kontrollieren zu können, empfehlen wir unseren Kunden, sich für den Wechsel zu entscheiden, wann immer Sie denken, es ist der richtige Zeitpunkt, anstatt darauf zu warten, dass der Wechsel stattfindet. |

Microsoft Teams hat eine neue Methode zum Speichern von Besprechungsaufzeichnungen. Als erste Phase eines Übergangs vom klassischen Microsoft Stream zum [neuen Stream](/stream/streamnew/new-stream) speichert diese Methode Aufzeichnungen auf Microsoft OneDrive for Business und SharePoint Online in Microsoft 365 und bietet viele Vorteile.

Stream (klassisch) als Plattform wird in naher Zukunft nicht eingestellt. Die Videos, die derzeit in Stream (klassisch) live sind, bleiben dort, bis ein zukünftiges Migrationstool verfügbar ist, um sie auf OneDrive und SharePoint Online zu verschieben. Weitere Informationen zu unseren zukünftigen Plänen finden Sie unter [Migration von Stream (klassisch)](/stream/streamnew/classic-migration).

> [!NOTE]
> Wenn eine Teams-Besprechungsaufzeichnung nicht erfolgreich auf OneDrive/ SharePoint Online hochgeladen werden kann, wird die Aufzeichnung stattdessen vorübergehend in Azure Media Services (AMS) gespeichert. Nach der Speicherung in AMS werden keine Wiederholungsversuche unternommen, um die Aufzeichnung automatisch auf OneDrive/ SharePoint Online oder Stream hochzuladen.

Besprechungsaufzeichnungen, die in AMS gespeichert sind, sind 21 Tage lang verfügbar, bevor sie automatisch gelöscht werden. Benutzer können das Video von AMS herunterladen, wenn sie eine Kopie aufbewahren müssen.

Die Verwendung von OneDrive for Business und SharePoint Online zum Speichern von Aufzeichnungen bietet folgende Vorteile:

- Aufbewahrungsrichtlinien für Teams-Besprechungsaufzeichnung (TMR) (S+C E5 Beschriftungen zur automatischen Aufbewahrung)
- Vorteile der Informationsgovernance in OneDrive for Business und SharePoint Online
- Einfach eingestellte Berechtigungen und Freigabe
- Freigeben von Aufzeichnungen für Gäste (externe Benutzer) nur mit expliziter Freigabe
- Ablauf von „Zugriff anfordern“
- Bereitstellen von freigegebenen OneDrive for Business- und SharePoint Online-Links
- Besprechungsaufzeichnungen sind schneller verfügbar
- In Ihrer Besprechung aufgezeichnetes Suchbasistranskript
- **Nach lokal verschieben** Mandantenunterstützung
- Multi-Geo-Unterstützung – Aufzeichnungen werden in einer für den Benutzer spezifischen Region gespeichert
- Unterstützung von "Bring your own key" (BYOK)

Sehen Sie sich die vollständige Liste der heute verfügbaren [-Features an und erfahren Sie, was Sie im Laufe der Zeit erwarten können](/stream/streamnew/features-new-version-stream).

Schauen Sie sich für weitere Informationen "Hochladen einer Microsoft Teams-Besprechungsaufzeichnung in Stream".

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>Einrichten der Option zur Besprechungsaufzeichnung für OneDrive for Business und SharePoint Online

Die Option zur Besprechungsaufzeichnung ist eine Einstellung auf der Richtlinienebene von Teams. Das folgende Beispiel zeigt, wie Sie die globale Richtlinie festlegen können. Stellen Sie sicher, dass Sie die Option zur Besprechungsaufzeichnung für die Richtlinie oder Richtlinien festlegen, die Sie Ihren Benutzern zugewiesen haben.

> [!Note]
> Änderungen an Teams-Besprechungsrichtlinien brauchen eine Weile, um verteilt zu werden. Überprüfen Sie es einige Stunden nach der Einstellung, melden Sie sich dann bei der Teams Desktop-App ab und melden Sie sich erneut an, oder starten Sie ihren Computer einfach neu.

1. Teams PowerShell installieren.

   > [!NOTE]
   > Der Skype for Business Online-Connector ist derzeit Bestandteil des aktuellen PowerShell-Moduls von Teams. Wenn Sie die neueste Version von Teams PowerShell verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren. Siehe [Verwalten von Skype for Business Online mit PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide).

2. Öffnen Sie PowerShell als Administrator.

3. Installieren Sie das [PowerShell-Modul von Teams](./teams-powershell-install.md).

4. Importieren Sie das MicrosoftTeams-Modul, und melden Sie sich als Teamadministrator an.

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

5. Verwenden Sie [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) zum Festlegen einer Teams-Besprechungsrichtlinie für den Übergang vom Streamspeicher zu OneDrive for Business und SharePoint Online.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Wenn einige Ihrer Benutzer eine Richtlinie pro Organisator oder Benutzer zugewiesen haben, müssen Sie diese Einstellung für diese Richtlinie festlegen, wenn Sie möchten, dass diese Benutzer die Besprechungsaufzeichnungen auch in OneDrive for Business und SharePoint Online speichern. Weitere Informationen finden Sie unter [Besprechungsrichtlinien in Teams verwalten](meeting-policies-in-teams.md).

## <a name="learn-more"></a>Weitere Informationen

Näheres zur Aufzeichnung von Teams-Cloudbesprechungen erfahren Sie unter [Aufzeichnen von Microsoft Teams-Cloudbesprechungen](cloud-recording.md). In diesem Artikel erfahren Sie mehr über die Aufzeichnungseinrichtung, Verwaltung, Governance, Berechtigungen und Speicher.
