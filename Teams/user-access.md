---
title: Verwalten des Benutzerzugriffs auf Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Hier erfahren Sie, wie Sie den Zugriff auf Benutzerebene pro Benutzer aktivieren oder deaktivieren.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83d2b0710b811431546f0df9931d3a0b867d2b2b
ms.sourcegitcommit: 28dd9b8ca3de35a73e4d6923eff5546925435b8b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2019
ms.locfileid: "30683884"
---
<a name="manage-user-access-to-microsoft-teams"></a>Verwalten des Benutzerzugriffs auf Microsoft Teams
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Auf Benutzerebene kann Zugriff auf Microsoft-Teams, aktiviert oder deaktiviert für jeden Benutzer einzeln durch Zuweisen oder Entfernen von der Microsoft-Teams-Lizenz werden.

Verwenden Sie Messagingrichtlinien verwaltete aus der Verwaltungskonsole Teams steuern, welche Chat und Channel messaging-Funktionen für Benutzer in Teams verfügbar sind. Sie können die Standardrichtlinie verwenden oder einen oder mehrere benutzerdefinierte Messagingrichtlinien für Personen in Ihrer Organisation erstellen. Weitere Informationen finden lesen Sie [Messagingrichtlinien in Teams verwalten](messaging-policies-in-teams.md).

> [!NOTE]
>Microsoft empfiehlt, dass Sie Teams für alle Benutzer in einem Unternehmen aktivieren, damit Teams Wiki für Projekte und anderen dynamischen Initiativen gebildet werden können. Auch wenn Sie Entscheidungen zu treffen pilot, möglicherweise noch ist es hilfreich zum Beibehalten von Teams, die für alle Benutzer aktiviert, jedoch nur als Ziel für die Kommunikation mit der Pilotgruppe von Benutzern.

## <a name="manage-teams-through-the-office-365-admin-center"></a>Verwalten von Teams über das Office 365 Administrationscenter

Teams auf Benutzerebene Lizenzen werden direkt über die Office 365 Admin Center Benutzer Verwaltungsschnittstellen verwaltet. Ein Administrator kann Lizenzen für neue Benutzer, wenn neue Benutzerkonten erstellt werden, oder Benutzer mit vorhandenen Konten zuweisen. Der Administrator muss Office 365 globaler Administrator oder Benutzerverwaltungsadministrator Berechtigungen zum Verwalten von Lizenzen für Microsoft-Teams verfügen.

Wenn einem Benutzer eine Lizenz-SKU wie E3 oder E5 zugewiesen wird, wird automatisch eine Microsoft Teams-Lizenz zugewiesen, und der Benutzer wird für Microsoft Teams aktiviert. Administratoren können alle Office 365-Dienste und -Lizenzen präzise steuern, und die Microsoft Teams-Lizenz für einen bestimmten Benutzer oder eine bestimmte Gruppe von Benutzern kann aktiviert oder deaktiviert werden.

![Screenshot des Abschnitts „Produktlizenzen“ im Office 365 Admin Center](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Eine Benutzerlizenz Teams kann jederzeit deaktiviert werden. Nachdem die Lizenz deaktiviert ist, wird der Benutzerzugriff auf Microsoft-Teams, verhindert werden, und der Benutzer werden nicht mehr Teams in die Office 365-app-Start "und" Homepage finden Sie unter.

![Screenshot des Abschnitts „Produktlizenzen“ im Office 365 Admin Center mit ausgewählter Option „Microsoft Teams“](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>Verwalten von über die PowerShell

> [!IMPORTANT]
> Neue MsolLicenseOptions werden aktivieren Sie alle Dienste, die zuvor deaktiviert wurden, es sei denn, Explictitly identitied in Ihrem benutzerdefinierten Skript. Beispiel: Wenn Sie sowohl Exchange & Schlingern beim Deaktivieren von Teams, zusätzlich deaktiviert lassen möchten enthält müssten Sie dies in das Skript oder beide Exchange & Schlingern wird aktiviert werden, für die Benutzer, den Sie angegeben haben. Wenn Sie eine Benutzeroberfläche zur Verwaltung dieser Funktionen nutzen möchten finden Sie unter: [Reporting zu Office 365-Lizenz und Verwaltungstool-entfernen Lizenzen in einer Sammeloperation](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)

Das Aktivieren und Deaktivieren von Microsoft Teams als Arbeitsauslastungslizenz über PowerShell funktioniert genau wie bei jeder anderen Arbeitsauslastung. Der Name des Dienstplans für Microsoft Teams lautet TEAMS1. Für GCC ist der Dienstname Plan TEAMS_GOV. Für GCC hoch ist der Dienstname Plan TEAMS_GCCHIGH. Für DoD ist der Dienstname Plan TEAMS_DOD (finden Sie unter [Disable-Zugriff auf Dienste mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) für Weitere Informationen.)

**Beispiel:** Im folgenden finden einfach einem Beispiel auf wie würden Sie Teams für alle Benutzer in einem bestimmten Lizenztyp deaktivieren. Sie müssen dies zuerst tun und dann den Lizenztyp für die Benutzer, die im Rahmen von Pilottests Zugriff haben sollen, einzeln aktivieren.

Um die in Ihrer Organisation vorhandenen Abonnementtypen anzuzeigen, verwenden Sie den folgenden Befehl:

      Get-MsolAccountSku

Tragen Sie den Namen Ihres Plans einschließlich des Organisationsnamens und des Plans für Ihre Bildungseinrichtung ein (zum Beispiel „ContosoSchool:ENTERPRISEPACK_STUDENT“), und führen Sie dann die folgenden Befehle aus:

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
Führen Sie zum Deaktivieren von Teams für alle Benutzer mit einer aktiven Lizenz für den benannten Plan den folgenden Befehl ein:

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |Entscheidungspunkt         |<ul><li>Was ist Ihre Organisation Planen von Teams Onboarding in der gesamten Organisation?  (Pilot- oder öffnen)</li></ul>         |
|![Symbol für „Nächste Schritte“](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |Nächste Schritte         |<ul><li>Wenn Sie über eine geschlossene Pilotprojekt Onboarding entscheiden, ob Sie über die Lizenzierung tun möchten, oder gezielten Kommunikation.</li><li>Je nach Entscheidung, dauern evaluieren Schritte aus, um sicherzustellen, nur Benutzer, die auf Teams (falls erforderlich) zugreifen dürfen.</li><li>Dokumentieren Sie die Richtlinien für welche Benutzer stellen, die werden (oder keine) haben Zugriff auf Teams.</li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a>Verwalten von Teams auf der Ebene der Office 365-Mandanten
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

