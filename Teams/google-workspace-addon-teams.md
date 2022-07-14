---
title: Einrichten des Microsoft Teams-Besprechungs-Add-Ons für Google Workspace
author: CarolynRowe
ms.author: crowe
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Erfahren Sie, wie Sie das Microsoft Teams-Besprechungs-Add-On für Google Workspace einrichten.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 020fdd048b25dc015036e49d00858c106cf9a7af
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789180"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Einrichten des Microsoft Teams-Besprechungs-Add-Ons für Google Workspace

Mithilfe des Microsoft Teams-Besprechungs-Add-Ons können Google-Kalenderbenutzer eine Microsoft Teams-Besprechung direkt über Google Workspace planen und daran teilnehmen. Benutzer erhalten Zugriff auf Teams-Besprechungsfeatures wie Video- und Audiokonferenzen, Bildschirmfreigabe, Besprechungschat, digitale Whiteboards und vieles mehr. Bleiben Sie in Verbindung und organisiert, um mehr gemeinsam in Arbeit, Schule und Leben zu erledigen.

Das Microsoft Teams-Besprechungs-Add-On für Google Workspace muss von einem Teams-Administrator aktiviert werden, bevor Mandantenbenutzer auf die App zugreifen können.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Aktivieren oder Deaktivieren des Microsoft Teams-Besprechungs-Add-Ons für Google Workspace im Azure-Portal

Als Mandantenadministrator können Sie ein Microsoft Teams-Besprechungs-Add-On für Google Workspace über das Administratorkonto Ihrer Organisation mithilfe der Azure-Portal aktivieren oder deaktivieren.

Das Add-On ist standardmäßig aktiviert.

1. Melden Sie sich beim Azure-Portal an.

2. Wählen Sie **"Unternehmensanwendungen** > **alle Anwendungen" aus**.

3. Suchen Sie nach **dem Microsoft Teams-Besprechungs-Add-On für Google Workspace**.

   ![Azure-Portal alle Anwendungen anzeigen.](media/aad-add-google-workspace.png)

4. Wählen Sie **"Ja**" aus.

   ![Azure-Portal die Eigenschaften des Google-Arbeitsbereichs anzeigen.](media/google-workspace-properties.png)

5. (Optional) Um das Add-On zu deaktivieren, wählen Sie in Schritt 4 **"Nein** " statt " **Ja** " aus.

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
    Get-AzureADServicePrincipal -Filter "appId eq '$appId'" | Set-AzureADServicePrincipal -AccountEnabled:$false
    Write-Host "Created and disabled the Service Principal \n"
}
```

Weitere Informationen finden Sie unter [Erstellen eines Azure-Dienstprinzipals mit Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Löschen des Microsoft Teams-Besprechungs-Add-Ons für Google Workspace

Anweisungen finden Sie in der Google-Dokumentation [Löschen einer Google Workspace Marketplace-App](https://support.google.com/a/answer/6216211?hl=en) .

## <a name="create-the-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Erstellen des Microsoft Teams-Besprechungs-Add-Ons für Google Workspace mithilfe von PowerShell

Falls das Microsoft Teams-Besprechungs-Add-On in Ihrem Mandanten nicht vorhanden ist, können Sie es mithilfe von PowerShell erstellen: 

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already
    Write-Host "The Service principal already exists"
} else {
    # Service principal does not yet exist, create it
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    Write-Host "Created the Service Principal"
}
```
