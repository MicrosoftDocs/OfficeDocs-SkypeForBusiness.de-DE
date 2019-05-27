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
ms.openlocfilehash: e61a4456d926c8d939769e49968a79943c1138b4
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433279"
---
<a name="manage-user-access-to-microsoft-teams"></a>Verwalten des Benutzerzugriffs auf Microsoft Teams
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Auf Benutzerebene kann der Zugriff auf Microsoft Teams für einzelne Benutzer aktiviert oder deaktiviert werden, indem die Microsoft Teams-Produktlizenz zugewiesen oder entfernt wird.

Verwenden Sie im Team Admin Center verwaltete Nachrichtenrichtlinien, um zu steuern, welche Chat-und Kanal-Messaging Features Benutzern in Teams zur Verfügung stehen. Sie können die Standardrichtlinie verwenden oder eine oder mehrere benutzerdefinierte Messagingrichtlinien für Personen in Ihrer Organisation erstellen. Weitere Informationen finden Sie unter [Verwalten von Nachrichtenrichtlinien in Teams](messaging-policies-in-teams.md).

> [!NOTE]
>Microsoft empfiehlt, dass Sie Teams für alle Benutzer in einem Unternehmen aktivieren, damit Teams organisch für Projekte und andere dynamische Initiativen ausgebildet werden können. Auch wenn Sie sich für ein Pilotprojekt entscheiden, ist es möglicherweise weiterhin hilfreich, Teams für alle Benutzer aktiviert zu halten, aber nur die Kommunikation mit der Pilotgruppe von Benutzern zu erreichen.

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a>Verwalten von Teams über das Microsoft 365 Admin Center

Teams auf Benutzerebene Lizenzen werden direkt über die Benutzer Verwaltungsschnittstellen von Microsoft 365 Admin Center verwaltet. Ein Administrator kann neuen Benutzern Lizenzen zuweisen, wenn neue Benutzerkonten erstellt werden, oder für Benutzer mit vorhandenen Konten. Der Administrator muss über die Administratorrechte von Office 365 Global Administrator oder Benutzerverwaltung verfügen, um Microsoft Teams-Lizenzen verwalten zu können.

Wenn einem Benutzer eine Lizenz-SKU wie E3 oder E5 zugewiesen wird, wird automatisch eine Microsoft Teams-Lizenz zugewiesen, und der Benutzer wird für Microsoft Teams aktiviert. Administratoren können alle Office 365-Dienste und -Lizenzen präzise steuern, und die Microsoft Teams-Lizenz für einen bestimmten Benutzer oder eine bestimmte Gruppe von Benutzern kann aktiviert oder deaktiviert werden.

![Screenshot des Abschnitts „Produktlizenzen“ im Office 365 Admin Center](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Eine Benutzerlizenz für Teams kann jederzeit deaktiviert werden. Nachdem die Lizenz deaktiviert wurde, wird der Zugriff von Benutzern auf Microsoft Teams verhindert, und der Benutzer kann keine Teams mehr im Office 365-App-Startfeld und auf der Startseite anzeigen.

![Screenshot mit den im Abschnitt "Produktlizenzen" ausgewählten Teams](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>Verwalten über PowerShell

> [!IMPORTANT]
> New-MsolLicenseOptions aktiviert alle Dienste, die zuvor deaktiviert wurden, es sei denn, explictitly identitied in Ihrem angepassten Skript. Wenn Sie beispielsweise beide Exchange-& Sway deaktiviert lassen möchten, während Additonally die Deaktivierung von Teams durchführen möchten, müssen Sie dies im Skript INLCUDE, oder beide Exchange & Sway werden für die von Ihnen identifizierten Benutzer aktiviert. Wenn Sie eine GUI verwenden möchten, um diese Funktionalität zu verwalten, lesen Sie: [Office 365-Lizenz Berichterstattung und-Verwaltungs Tool – Zuweisen von Entfernen von Lizenzen in Massen](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)

Das Aktivieren und Deaktivieren von Microsoft Teams als Arbeitsauslastungslizenz über PowerShell funktioniert genau wie bei jeder anderen Arbeitsauslastung. Der Name des Dienstplans für Microsoft Teams lautet TEAMS1. Für gcc lautet der Service Plan Name TEAMS_GOV. Für gcc ist der Service Plan Name TEAMS_GCCHIGH. Für DoD lautet der Service Plan Name TEAMS_DOD (Weitere Informationen finden Sie unter [Deaktivieren des Zugriffs auf Dienste mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) .)

**Beispiel:** Im folgenden sehen Sie nur ein kurzes Beispiel, wie Sie Teams für jeden in einem bestimmten Lizenztyp deaktivieren. Sie müssen dies zuerst tun und dann den Lizenztyp für die Benutzer, die im Rahmen von Pilottests Zugriff haben sollen, einzeln aktivieren.

Um die in Ihrer Organisation vorhandenen Abonnementtypen anzuzeigen, verwenden Sie den folgenden Befehl:

      Get-MsolAccountSku

Tragen Sie den Namen Ihres Plans einschließlich des Organisationsnamens und des Plans für Ihre Bildungseinrichtung ein (zum Beispiel „ContosoSchool:ENTERPRISEPACK_STUDENT“), und führen Sie dann die folgenden Befehle aus:

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
Führen Sie den folgenden Befehl aus, um Teams für alle Benutzer mit einer aktiven Lizenz für Ihren benannten Plan zu deaktivieren:

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |Entscheidungspunkt         |<ul><li>Was ist der Plan Ihrer Organisation für Teams, die sich in der gesamten Organisation an Bord befinden?  (Pilot oder Open)</li></ul>         |
|![Symbol für „Nächste Schritte“](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |Nächste Schritte         |<ul><li>Wenn Sie über ein geschlossenes Pilot Projekt an Bord sind, entscheiden Sie, ob Sie dies über eine Lizenzierung oder gezielte Kommunikation tun möchten.</li><li>Führen Sie je nach Entscheidung die erforderlichen Schritte aus, um sicherzustellen, dass nur Pilot Benutzer, die auf Teams zugreifen dürfen (falls erforderlich).</li><li>Dokumentieren Sie die Richtlinien für die Benutzer, die Zugriff auf Teams haben (oder nicht).</li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a>Verwalten von Teams auf der Office 365-Mandantenebene
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

