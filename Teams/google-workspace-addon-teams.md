---
title: Einrichten des Microsoft Teams-Besprechungs-Add-Ons für Google Workspace
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Erfahren Sie, wie Sie das Microsoft Teams-Besprechungs-Add-On für Google Workspace einrichten.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e1b7024190ac51b89e09fafced86ffea13f5961
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120696"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Einrichten des Microsoft Teams-Besprechungs-Add-Ons für Google Workspace

Mithilfe des Microsoft Teams-Besprechungs-Add-Ons können Google-Kalenderbenutzer eine Microsoft Teams-Besprechung direkt aus Google Workspace planen und an einer Besprechung teilnehmen. Benutzer erhalten Zugriff auf Die Features für Teams-Besprechungen, einschließlich Video- und Audiokonferenzen, Bildschirmfreigabe, Besprechungschat, digitale Whiteboards und vieles mehr. Bleiben Sie in Verbindung und organisiert, um mehr für Arbeit, Schule und Leben zu tun.

Das Microsoft Teams-Besprechungs-Add-On für Google Workspace muss von einem Teams-Administrator aktiviert werden, bevor Mandantenbenutzer auf die App zugreifen können.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Aktivieren oder Deaktivieren des Microsoft Teams-Besprechungs-Add-Ons für Google Workspace im Azure-Portal

Als Mandantenadministrator können Sie ein Microsoft Teams-Besprechungs-Add-On für Google Workspace über das Azure-Portal über das Administratorkonto Ihrer Organisation aktivieren oder deaktivieren.

Das Add-On ist standardmäßig aktiviert.

1. Melden Sie sich beim Azure-Portal an.

2. Wählen Sie **Unternehmensanwendungen**  >  **Alle Anwendungen aus.**

3. Suchen Sie **nach dem Microsoft Teams-Besprechungs-Add-On für Google Workspace.**

   ![Azure-Portal mit allen Anwendungen](media/aad-add-google-workspace.png)

4. Wählen Sie **Ja aus.**

   ![Azure-Portal mit den Eigenschaften des Google-Arbeitsbereichs](media/google-workspace-properties.png)

5. (Optional) Um das Add-On zu deaktivieren, wählen Sie in Schritt 4 **Nein** statt **Ja** aus.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Deaktivieren des Microsoft Teams-Besprechungs-Add-Ons für Google Workspace mit PowerShell

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already, disable it
    Set-AzureADServicePrincipal -ObjectId $servicePrincipal.ObjectId -AccountEnabled $false
    Write-Host "Disabled existing Service Principal \n"
} else {
    # Service principal does not yet exist, create it and disable it at the same time
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    $servicePrincipal = New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName -AccountEnabled $false
    Write-Host "Created and disabled the Service Principal \n"
}
```

Weitere Informationen finden Sie unter [Erstellen eines Azure-Dienstprinzipal mit Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Löschen des Microsoft Teams-Besprechungs-Add-Ons für Google Workspace

Anweisungen finden Sie in der Google-Dokumentation Löschen einer [Google Workspace Marketplace-App.](https://support.google.com/a/answer/6216211?hl=en)