---
title: Einrichten des Microsoft Teams-Besprechungs-Add-ons für Google Workspace
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
description: Hier erfahren Sie, wie Sie das Microsoft Teams-Besprechungs-Add-on für Google Workspace einrichten.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c86d707a4298d88d3ae0cff389bda73490390e4
ms.sourcegitcommit: 882ed439f8bba27b1cf0c14056c146267cacd359
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49387294"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Einrichten des Microsoft Teams-Besprechungs-Add-ons für Google Workspace

Mithilfe des Microsoft Teams-Besprechungs-Add-ons können Google Calendar-Benutzer eine Microsoft Teams-Besprechung direkt aus Google Workspace planen und daran teilnehmen. Benutzer erhalten Zugriff auf die Besprechungsfunktionen von Teams, darunter Video-und Audiokonferenzen, Bildschirmübertragung, Besprechungs Chat, digitale Whiteboards und vieles mehr. Bleiben Sie in Kontakt und Organisation, um mehr über Arbeit, Schule und Leben hinweg zu erledigen.

Das Microsoft Teams-Besprechungs-Add-on für Google Workspace muss von einem Teams-Administrator aktiviert werden, bevor Mandanten Benutzer auf die App zugreifen können.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Aktivieren oder Deaktivieren des Microsoft Teams-Besprechungs-Add-ons für Google Workspace im Azure-Portal

Als mandantenadministrator können Sie über das Azure-Portal ein Microsoft Teams-Besprechungs-Add-on für Google Workspace aus dem Administratorkonto Ihres Unternehmens aktivieren oder deaktivieren.

Das Add-on ist standardmäßig aktiviert.

1. Anmelden beim Azure-Portal.

2. Wählen Sie **Enterprise-Anwendungen**  >  **alle Anwendungen** aus.

3. Suchen **Sie nach dem Microsoft Teams-Besprechungs-Add-on für Google Workspace**.

   ![Azure-Portal mit allen Anwendungen](media/aad-add-google-workspace.png)

4. Wählen Sie **Ja** aus.

   ![Azure-Portal mit den Eigenschaften von Google Workspace](media/google-workspace-properties.png)

5. Optional Wenn Sie das Add-on deaktivieren möchten, wählen Sie in Schritt 4 **Nein** anstelle von **Ja** aus.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Deaktivieren des Microsoft Teams-Besprechungs-Add-ons für Google Workspace mithilfe von PowerShell

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

Weitere Informationen finden Sie unter [Erstellen eines Azure-Dienst Prinzipals mit Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Löschen des Microsoft Teams-Besprechungs-Add-ons für Google Workspace

Anweisungen hierzu finden Sie in der Google-Dokumentation [Löschen einer Google Workspace Marketplace-App](https://support.google.com/a/answer/6216211?hl=en) .
