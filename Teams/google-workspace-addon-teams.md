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
ms.openlocfilehash: 9c86d707a4298d88d3ae0cff389bda73490390e4
ms.sourcegitcommit: 380cd74c08cd34e1c3f73f5c0f51da4ae2674f6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880876"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Einrichten des Microsoft Teams-Besprechungs-Add-Ons für Google Workspace

Mithilfe des Microsoft Teams-Besprechungs-Add-Ons können Google -Kalenderbenutzer eine Microsoft Teams-Besprechung direkt aus Google Workspace planen und an ihr teilnehmen. Benutzer erhalten Zugriff auf Teams-Besprechungsfeatures, darunter Video- und Audiokonferenzen, Bildschirmfreigabe, Besprechungschat, digitale Whiteboards und vieles mehr. Bleiben Sie in Verbindung und organisieren Sie, um in Arbeit, Schule und Leben mehr zusammen zu tun.

Das Microsoft Teams-Besprechungs-Add-On für Google Workspace muss von einem Teamadministrator aktiviert werden, bevor Mandantenbenutzer auf die App zugreifen können.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Aktivieren oder Deaktivieren des Microsoft Teams-Besprechungs-Add-Ons für Google Workspace im Azure-Portal

Als Mandantenadministrator können Sie ein Microsoft Teams-Besprechungs-Add-On für Google Workspace über das Verwaltungskonto Ihrer Organisation über das Azure-Portal aktivieren oder deaktivieren.

Das Add-On ist standardmäßig aktiviert.

1. Melden Sie sich beim Azure-Portal an.

2. Wählen Sie **"Unternehmensanwendungen**  >  **Alle Anwendungen" aus.**

3. Suchen Sie **nach dem Microsoft Teams-Besprechungs-Add-On für Google Workspace.**

   ![Azure-Portal, in dem alle Anwendungen angezeigt werden](media/aad-add-google-workspace.png)

4. Wählen Sie **"Ja" aus.**

   ![Azure-Portal mit den Google Workspace-Eigenschaften](media/google-workspace-properties.png)

5. (Optional) Um das Add-On zu deaktivieren, **wählen** Sie in Schritt 4 "Nein" statt **"Ja"** aus.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Deaktivieren des Microsoft Teams-Besprechungs-Add-Ons für Google Workspace mithilfe von PowerShell

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

Weitere Informationen finden Sie unter ["Erstellen eines Azure-Dienstprinzipal mit Azure PowerShell".](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Löschen des Microsoft Teams-Besprechungs-Add-Ons für Google Workspace

Anweisungen dazu finden Sie in [der Google-Dokumentation zum](https://support.google.com/a/answer/6216211?hl=en) Löschen einer Google Workspace Marketplace-App.
