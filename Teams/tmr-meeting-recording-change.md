---
title: Verwenden OneDrive for Business und SharePoint Online für Besprechungsaufzeichnungen
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie von Stream zu Stream wechseln OneDrive for Business und SharePoint Online-Besprechungsaufzeichnungsspeicher in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: e00ccbf9ade9b1fae3dde64033fe82b502e2366b
ms.sourcegitcommit: 79d20fa2c45173d5a990551e79571caff06d7f82
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2021
ms.locfileid: "53486135"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>Verwenden OneDrive for Business und SharePoint Online oder Stream für Besprechungsaufzeichnungen

> [!Note]
> Die Umstellung von Microsoft Stream auf OneDrive for Business und Besprechungsaufzeichnungen Microsoft Office SharePoint Online phasenweiser Ansatz.

|<div style="width:290px">Datum&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Ereignis&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|5. Oktober 2020<br> *(Abgeschlossen)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Sie aktivieren die Teams-Besprechungsrichtlinie, damit Besprechungsaufzeichnungen auf OneDrive for Business und SharePoint Online statt in Microsoft Stream (klassisch) gespeichert werden.|
|Einführung ab dem 7. Januar 2021<br> *(Abgeschlossen)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Alle neuen Teams-Besprechungsaufzeichnungen werden in OneDrive for Business und SharePoint Online gespeichert, es sei denn, Sie verzögern diese Änderung, indem Sie die Teams-Besprechungsrichtlinien Ihrer Organisation ändern und explizit auf **Stream** festlegen. Es reicht nicht aus, die Richtlinienberichte als Stream zu sehen. Sie müssen den Richtlinienwert explizit auf **Stream** festlegen.|
|Einführung ab dem 11. Januar 2021<br> *(Abgeschlossen)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Nur GCC**<br> GCC-Kunden können die Option zwar ab dem 5. Oktober deaktivieren können, Sie können Sie jedoch nicht aktivieren. Dieses Feature wird ab dem 11. Januar 2021 für alle GCC-Kunden zur Verfügung stellen, sofern Sie das Feature nicht deaktivieren.<br>  <br>Ab dem 11. Januar 2021 werden alle neuen Teams-Besprechungsaufzeichnungen für GCC-Kunden auf OneDrive for Business und SharePoint Online gespeichert, sofern Sie diese Änderung nicht verzögern, indem Sie die Teams-Besprechungsrichtlinien Ihrer Organisation ändern und sie explizit auf **Stream** festlegen. <br><br>Wenn Sie das Feature deaktiviert haben, es nun aber aktivieren möchten, können Sie dazu Ihre Richtlinie für Teams-Besprechungen explizit auf **OneDrive for Business** setzen. |
|Einführung ab dem 1. März 2021 <br> *(Complete)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC High und DoD**<br> Kunden können nun zum ersten Mal Cloud-Besprechungsaufzeichnungen in Microsoft Teams aktivieren. Diese Aufzeichnungen werden standardmäßig auf OneDrive und SharePoint Online gespeichert und abgespielt. |
|Wird ab dem 7. Juli 2021 veröffentlicht<br> *(Complete)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Alle Kunden (Enterprise, Education und GCC)**<br> Für eine Teams-Besprechung, die in OneDrive und SharePoint Online aufgezeichnet und während der Besprechung auch live aufgezeichnet wurde, können Sie jetzt in Microsoft Search suchen, um die Aufzeichnungsdatei der Besprechung basierend auf der Aufzeichnung zu finden. |
|Inkrementell ab dem 16. August 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Alle Kunden (Enterprise, Education und GCC)**<br>In Microsoft Stream (klassisch) können keine neuen Besprechungsaufzeichnungen gespeichert werden. alle Kunden haben Besprechungsaufzeichnungen automatisch auf OneDrive for Business und SharePoint Online gespeichert, selbst wenn sie ihre Richtlinien für Besprechungen Teams Stream geändert haben.<br><br> Um den Wandel in Ihrem Unternehmen besser kontrollieren zu können, empfehlen wir unseren Kunden, sich für den Wechsel zu entscheiden, wann immer Sie denken, es ist der richtige Zeitpunkt, anstatt darauf zu warten, dass der Wechsel stattfindet. |

Microsoft Teams hat eine neue Methode zum Speichern von Besprechungsaufzeichnungen. Als erste Phase des Übergangs vom klassischen Microsoft Stream zum neuen [Stream](/stream/streamnew/new-stream)speichert diese Methode Aufzeichnungen auf Microsoft OneDrive for Business und SharePoint Online in Microsoft 365 und bietet zahlreiche Vorteile.

Der Stream (klassisch) als Plattform wird in naher Zukunft nicht mehr unterstützt. Die Videos, die aktuell in Stream (klassisch) laufen, bleiben dort, bis ein zukünftiges Migrationstool verfügbar ist, um sie auf OneDrive und SharePoint online zu verschieben. Weitere [Informationen zu unseren zukünftigen Plänen](/stream/streamnew/classic-migration) finden Sie unter Klassische Migration streamen.

> [!NOTE]
> Wenn eine Teams-Besprechungsaufzeichnung nicht erfolgreich auf OneDrive/SharePoint Online hochgeladen werden kann, wird die Aufzeichnung stattdessen vorübergehend Azure Media Services (AMS) gespeichert. Nach dem Speichern in AMS werden keine Wiederholungsversuche ausgeführt, um die Aufzeichnung automatisch in OneDrive/SharePoint Online oder Stream hochzuladen.

In AMS gespeicherte Besprechungsaufzeichnungen sind 21 Tage lang verfügbar, bevor sie automatisch gelöscht werden. Benutzer können das Video von AMS herunterladen, wenn sie eine Kopie behalten müssen.

Die Verwendung von OneDrive for Business und SharePoint Online zum Speichern von Aufzeichnungen bietet folgende Vorteile:

- Aufbewahrungsrichtlinien für Teams-Besprechungsaufzeichnung (TMR) (S+C E5 Beschriftungen zur automatischen Aufbewahrung)
- Profitieren von OneDrive for Business und SharePoint Online Information Governance
- Einfach eingestellte Berechtigungen und Freigabe
- Freigeben von Aufzeichnungen für Gäste (externe Benutzer) nur mit expliziter Freigabe
- Ablauf von „Zugriff anfordern“
- Bereitstellen OneDrive for Business und SharePoint freigegebenen Onlinelinks
- Besprechungsaufzeichnungen sind schneller verfügbar
- Aufzeichnung des Aufzeichnungsergebniss der Suchbasis in Ihrer Besprechung
- **Nach lokal verschieben** Mandantenunterstützung
- Multi-Geo-Unterstützung – Aufzeichnungen werden in einer für den Benutzer spezifischen Region gespeichert
- Unterstützung von "Bring your own key" (BYOK)

Hier finden Sie eine vollständige Liste der heute verfügbaren Features [und was im Laufe der Zeit zu erwarten ist.](/stream/streamnew/features-new-version-stream)

Weitere Informationen finden Sie unter "Microsoft Teams für Besprechungsaufzeichnungen".

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>Einrichten der Besprechungsaufzeichnungsoption für OneDrive for Business und SharePoint Online

Die Option zur Besprechungsaufzeichnung ist eine Einstellung auf der Richtlinienebene von Teams. Das folgende Beispiel zeigt, wie Sie die globale Richtlinie festlegen können. Stellen Sie sicher, dass Sie die Option zur Besprechungsaufzeichnung für die Richtlinie oder Richtlinien festlegen, die Sie Ihren Benutzern zugewiesen haben.

> [!Note]
> Teams der Aktualisierung von Besprechungsrichtlinien dauert es eine Weile, bis sie weitervererbt wurden. Schauen Sie nach ein paar Stunden nach dem Festlegen wieder nach, melden Sie sich ab und wieder bei der Teams Desktop-App an, oder starten Sie Ihren Computer einfach neu.

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

5. Verwenden [Sie Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) zum Festlegen einer Teams-Besprechungsrichtlinie für den Übergang vom Streamspeicher zu OneDrive for Business und SharePoint Online.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Wenn einige Ihrer Benutzer eine Richtlinie pro Organisator oder pro Benutzer zugewiesen haben, müssen Sie diese Einstellung für diese Richtlinie festlegen, wenn Sie möchten, dass diese Benutzer die Besprechungsaufzeichnungen auch in OneDrive for Business und SharePoint Online speichern. Weitere Informationen finden Sie unter [Besprechungsrichtlinien in Teams verwalten](meeting-policies-in-teams.md).

## <a name="learn-more"></a>Weitere Informationen

Weitere Informationen zum Aufzeichnen von Teams in der Cloud finden Sie unter Teams [von Cloud-Besprechungsaufzeichnungen.](cloud-recording.md) In diesem Artikel erfahren Sie mehr über das Aufzeichnen von Setup, Verwaltung, Governance, Berechtigungen und Speicher.
