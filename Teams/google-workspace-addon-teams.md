---
title: Einrichten Microsoft Teams Besprechungs-Add-Ons für Google Workspace
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
description: Erfahren Sie, wie Sie Microsoft Teams-Add-On für Besprechungen für Google Workspace einrichten.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f4fe6a61dd4891f457656e0659243c75c372142
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598539"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Einrichten Microsoft Teams Besprechungs-Add-Ons für Google Workspace

Mithilfe des Microsoft Teams Besprechungs-Add-Ons können Google-Kalenderbenutzer eine Besprechung direkt aus Google Workspace Microsoft Teams und an ihnen teilnehmen. Die Benutzer erhalten Zugriff auf Teams Besprechungsfunktionen wie Video- und Audiokonferenzen, Bildschirmfreigabe, Besprechungschat, digitale Whiteboards und vieles mehr. Bleiben Sie in Verbindung und organisiert, um am Arbeitsplatz, in der Schule und im Leben mehr zusammen zu tun.

Das Microsoft Teams Besprechungs-Add-On für Google Workspace muss von einem Teams-Administrator aktiviert werden, bevor Mandantenbenutzer auf die App zugreifen können.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Aktivieren oder Deaktivieren Microsoft Teams Besprechungs-Add-Ons für Google Workspace im Azure-Portal

Als Mandantenadministrator können Sie über das Azure-Portal ein Microsoft Teams-Besprechungs-Add-On für Google Workspace aus dem Administratorkonto Ihrer Organisation aktivieren oder deaktivieren.

Das Add-On ist standardmäßig aktiviert.

1. Melden Sie sich beim Azure-Portal an.

2. Wählen **Enterprise Anwendungen Alle** Anwendungen  >  **aus.**

3. Suchen Sie Microsoft Teams Für Google Workspace nach **dem Besprechungs-Add-On**.

   ![Azure-Portal mit allen Anwendungen](media/aad-add-google-workspace.png)

4. Wählen Sie **Ja aus.**

   ![Azure-Portal mit den Google Workspace-Eigenschaften](media/google-workspace-properties.png)

5. (Optional) Um das Add-On zu deaktivieren, wählen **Sie** in Schritt 4 nein statt **Ja** aus.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Deaktivieren Microsoft Teams Besprechungs-Add-Ons für Google Workspace mithilfe von PowerShell

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

Weitere Informationen finden Sie unter [Erstellen eines Azure-Dienstprinzipals mit Azure PowerShell.](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Löschen des Microsoft Teams Besprechungs-Add-Ons für Google Workspace

Anweisungen dazu finden Sie in [der Google-Dokumentation](https://support.google.com/a/answer/6216211?hl=en) Löschen einer Google Workspace Marketplace-App.