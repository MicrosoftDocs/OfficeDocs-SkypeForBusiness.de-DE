---
title: Löschen einer Standort- oder Benutzerrichtlinie für den externen Benutzerzugriff
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können eine beliebige Standort- oder Benutzerrichtlinie löschen, die in der Skype für Business Server-Systemsteuerung auf der Seite Richtlinie für den externen Zugriff aufgeführt ist.
ms.openlocfilehash: 53087985ee0723a6291582c3a584be0986119918
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222856"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="f9c6a-103">Löschen einer Standort- oder Benutzerrichtlinie für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="f9c6a-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="f9c6a-104">Wenn Sie erstellt oder konfiguriert Richtlinien für den externen Benutzerzugriff, die Sie nicht mehr verwenden möchten, können Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f9c6a-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="f9c6a-105">Löschen Sie alle Standort- oder Benutzerrichtlinie, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="f9c6a-106">Die globale Richtlinie auf die Standardeinstellungen zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-106">Reset the global policy to the default settings.</span></span> <span data-ttu-id="f9c6a-107">Die Standardeinstellungen für die globale Richtlinie verweigern keinen Zugriff externer Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-107">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="f9c6a-108">Die globale Richtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-108">The global policy cannot be deleted.</span></span>


<span data-ttu-id="f9c6a-109">Sie können eine beliebige Standort- oder Benutzerrichtlinie löschen, die in der Skype für Business Server-Systemsteuerung auf der Seite **Richtlinie für den externen Zugriff** aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="f9c6a-110">Löschen die globale Richtlinie nicht tatsächlich gelöscht, jedoch wird es nur auf die Standardeinstellungen, die Unterstützung für externe Benutzer Zugriffsoptionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="f9c6a-111">Ausführliche Informationen zum Zurücksetzen der globalen Richtlinie finden Sie unter [Zurücksetzen der globalen Richtlinie für den Zugriff externer Benutzer](reset-the-global-policy-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f9c6a-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="f9c6a-112">So löschen Sie eine Standort- oder Benutzerrichtlinie für den Zugriff externer Benutzer</span><span class="sxs-lookup"><span data-stu-id="f9c6a-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="f9c6a-113">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f9c6a-114">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f9c6a-115">Klicken Sie auf **Zugriff durch externe Benutzer**, klicken Sie auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="f9c6a-116">Klicken Sie auf der Registerkarte **Richtlinie für den externen Zugriff** auf die Standort- oder Benutzerrichtlinie zu löschen, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="f9c6a-117">Wenn Sie aufgefordert werden, den Löschvorgang zu bestätigen, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f9c6a-118">Entfernen der PIN-Richtlinien mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f9c6a-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f9c6a-119">Richtlinien für externen Zugriff können mithilfe von Windows PowerShell und Remove-CsExternalAccessPolicy-Cmdlet gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="f9c6a-120">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="f9c6a-121">So entfernen eine bestimmte externe Zugriffsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="f9c6a-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="f9c6a-122">Dieser Befehl entfernt die externe Zugriffsrichtlinie, die auf den Standort Redmond angewendet:</span><span class="sxs-lookup"><span data-stu-id="f9c6a-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="f9c6a-123">So entfernen Sie alle externen Zugriff auf der Benutzerebene angewendete Richtlinien</span><span class="sxs-lookup"><span data-stu-id="f9c6a-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="f9c6a-124">Mit diesem Befehl werden alle externen Richtlinien für den Zugriff auf der Benutzerebene konfigurierte entfernt:</span><span class="sxs-lookup"><span data-stu-id="f9c6a-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="f9c6a-125">Um alle Richtlinien für den externen Zugriff zu entfernen, in denen externe Benutzerzugriff deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="f9c6a-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="f9c6a-126">Dieser Befehl löscht alle Richtlinien den externen Zugriff, in dem externe Benutzerzugriff deaktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="f9c6a-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="f9c6a-127">Weitere Informationen finden Sie im Hilfethema zum [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f9c6a-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
