---
title: Löschen einer Standort- oder Benutzerrichtlinie für den externen Benutzerzugriff
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können jede Website oder Benutzerrichtlinie löschen, die im Skype for Business Server-Control Panel auf der Seite "Richtlinien für den externen Zugriff" aufgeführt ist.
ms.openlocfilehash: 615df309088a329e07f5417dce16e98366a371c7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280124"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="34dd9-103">Löschen einer Standort- oder Benutzerrichtlinie für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="34dd9-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="34dd9-104">Wenn Sie Richtlinien für den externen Benutzer Zugriff erstellt oder konfiguriert haben, die Sie nicht mehr verwenden möchten, können Sie die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="34dd9-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="34dd9-105">Löschen Sie alle von Ihnen erstellten Websites oder Benutzerrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="34dd9-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="34dd9-106">Setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück.</span><span class="sxs-lookup"><span data-stu-id="34dd9-106">Reset the global policy to the default settings.</span></span> <span data-ttu-id="34dd9-107">Die globalen Standardrichtlinieneinstellungen verweigern den Zugriff externer Benutzer.</span><span class="sxs-lookup"><span data-stu-id="34dd9-107">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="34dd9-108">Die globale Richtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="34dd9-108">The global policy cannot be deleted.</span></span>


<span data-ttu-id="34dd9-109">Sie können jede Website oder Benutzerrichtlinie löschen, die im Skype for Business Server-Control Panel auf der Seite " **Richtlinien für den externen Zugriff** " aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="34dd9-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="34dd9-110">Wenn Sie die globale Richtlinie löschen, wird Sie nicht tatsächlich gelöscht, sondern nur auf die Standardeinstellungen zurückgesetzt, die keine Unterstützung für die Zugriffsoptionen für externe Benutzer beinhalten.</span><span class="sxs-lookup"><span data-stu-id="34dd9-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="34dd9-111">Details zum Zurücksetzen der globalen Richtlinie finden Sie unter [Zurücksetzen der globalen Richtlinie für den Zugriff durch externe Benutzer](reset-the-global-policy-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="34dd9-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="34dd9-112">So löschen Sie eine Website-oder Benutzerrichtlinie für den Zugriff durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="34dd9-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="34dd9-113">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="34dd9-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="34dd9-114">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="34dd9-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="34dd9-115">Klicken Sie auf **externer Benutzer Zugriff**, und klicken Sie auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="34dd9-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="34dd9-116">Klicken Sie auf der Registerkarte **Richtlinie für den externen Zugriff** auf die Website oder Benutzerrichtlinie, die Sie löschen möchten, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="34dd9-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="34dd9-117">Wenn Sie aufgefordert werden, den Löschvorgang zu bestätigen, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="34dd9-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="34dd9-118">Entfernen von PIN-Richtlinien mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="34dd9-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="34dd9-119">Richtlinien für den externen Zugriff können mithilfe von Windows PowerShell und dem Cmdlet Remove-CsExternalAccessPolicy gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="34dd9-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="34dd9-120">Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="34dd9-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="34dd9-121">So entfernen Sie eine bestimmte Richtlinie für den externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="34dd9-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="34dd9-122">Mit diesem Befehl wird die auf die Redmond-Website angewendete Richtlinie für den externen Zugriff entfernt:</span><span class="sxs-lookup"><span data-stu-id="34dd9-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="34dd9-123">So entfernen Sie alle auf den Benutzerbereich angewendeten Richtlinien für den externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="34dd9-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="34dd9-124">Mit diesem Befehl werden alle im Benutzerbereich konfigurierten externen Zugriffsrichtlinien entfernt:</span><span class="sxs-lookup"><span data-stu-id="34dd9-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="34dd9-125">So entfernen Sie alle externen Zugriffsrichtlinien, bei denen der Zugriff außerhalb des Benutzers deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="34dd9-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="34dd9-126">Dieser Befehl löscht alle externen Zugriffsrichtlinien, bei denen der Zugriff außerhalb des Benutzers deaktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="34dd9-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="34dd9-127">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="34dd9-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
