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
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="c431c-103">Einrichten des Microsoft Teams-Besprechungs-Add-ons für Google Workspace</span><span class="sxs-lookup"><span data-stu-id="c431c-103">Set up Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="c431c-104">Mithilfe des Microsoft Teams-Besprechungs-Add-ons können Google Calendar-Benutzer eine Microsoft Teams-Besprechung direkt aus Google Workspace planen und daran teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="c431c-104">Using the Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace.</span></span> <span data-ttu-id="c431c-105">Benutzer erhalten Zugriff auf die Besprechungsfunktionen von Teams, darunter Video-und Audiokonferenzen, Bildschirmübertragung, Besprechungs Chat, digitale Whiteboards und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="c431c-105">Users will get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.</span></span> <span data-ttu-id="c431c-106">Bleiben Sie in Kontakt und Organisation, um mehr über Arbeit, Schule und Leben hinweg zu erledigen.</span><span class="sxs-lookup"><span data-stu-id="c431c-106">Stay connected and organized to get more done together across work, school, and life.</span></span>

<span data-ttu-id="c431c-107">Das Microsoft Teams-Besprechungs-Add-on für Google Workspace muss von einem Teams-Administrator aktiviert werden, bevor Mandanten Benutzer auf die App zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="c431c-107">The Microsoft Teams meeting add-on for Google Workspace must be enabled by a Teams admin before tenant users can access the app.</span></span>

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a><span data-ttu-id="c431c-108">Aktivieren oder Deaktivieren des Microsoft Teams-Besprechungs-Add-ons für Google Workspace im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="c431c-108">Enable or disable Microsoft Teams meeting add-on for Google Workspace in the Azure portal</span></span>

<span data-ttu-id="c431c-109">Als mandantenadministrator können Sie über das Azure-Portal ein Microsoft Teams-Besprechungs-Add-on für Google Workspace aus dem Administratorkonto Ihres Unternehmens aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c431c-109">As a tenant administrator, you can enable or disable a Microsoft Teams meeting add-on for Google Workspace from your organization's admin account using the Azure portal.</span></span>

<span data-ttu-id="c431c-110">Das Add-on ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c431c-110">The add-on is enabled by default.</span></span>

1. <span data-ttu-id="c431c-111">Anmelden beim Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="c431c-111">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="c431c-112">Wählen Sie **Enterprise-Anwendungen**  >  **alle Anwendungen** aus.</span><span class="sxs-lookup"><span data-stu-id="c431c-112">Select **Enterprise applications** > **All applications**.</span></span>

3. <span data-ttu-id="c431c-113">Suchen **Sie nach dem Microsoft Teams-Besprechungs-Add-on für Google Workspace**.</span><span class="sxs-lookup"><span data-stu-id="c431c-113">Search for **Microsoft Teams meeting add-on for Google Workspace**.</span></span>

   ![Azure-Portal mit allen Anwendungen](media/aad-add-google-workspace.png)

4. <span data-ttu-id="c431c-115">Wählen Sie **Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="c431c-115">Select **Yes**.</span></span>

   ![Azure-Portal mit den Eigenschaften von Google Workspace](media/google-workspace-properties.png)

5. <span data-ttu-id="c431c-117">Optional Wenn Sie das Add-on deaktivieren möchten, wählen Sie in Schritt 4 **Nein** anstelle von **Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="c431c-117">(Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.</span></span>

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a><span data-ttu-id="c431c-118">Deaktivieren des Microsoft Teams-Besprechungs-Add-ons für Google Workspace mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="c431c-118">Disable Microsoft Teams meeting add-on for Google Workspace using PowerShell</span></span>

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

<span data-ttu-id="c431c-119">Weitere Informationen finden Sie unter [Erstellen eines Azure-Dienst Prinzipals mit Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span><span class="sxs-lookup"><span data-stu-id="c431c-119">For more information, see [Create an Azure service principal with Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span></span>

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="c431c-120">Löschen des Microsoft Teams-Besprechungs-Add-ons für Google Workspace</span><span class="sxs-lookup"><span data-stu-id="c431c-120">Delete the Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="c431c-121">Anweisungen hierzu finden Sie in der Google-Dokumentation [Löschen einer Google Workspace Marketplace-App](https://support.google.com/a/answer/6216211?hl=en) .</span><span class="sxs-lookup"><span data-stu-id="c431c-121">See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.</span></span>
