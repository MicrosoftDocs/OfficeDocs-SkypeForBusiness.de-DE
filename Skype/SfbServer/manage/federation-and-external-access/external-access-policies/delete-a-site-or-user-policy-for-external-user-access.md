---
title: Löschen einer Standort-oder Benutzerrichtlinie für den Zugriff durch externe Benutzer
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
f1.keywords:
- NOCSH
localization_priority: Normal
description: Sie können eine beliebige Website-oder Benutzerrichtlinie löschen, die in der Skype for Business Server-Systemsteuerung auf der Seite Richtlinie für den externen Zugriff aufgeführt ist.
ms.openlocfilehash: ae0a0499e7497c4d62884860a2730960e5070ac8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041234"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="83958-103">Löschen einer Standort-oder Benutzerrichtlinie für den Zugriff durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="83958-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="83958-104">Wenn Sie Richtlinien für den externen Benutzer Zugriff erstellt oder konfiguriert haben, die Sie nicht mehr verwenden möchten, können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="83958-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="83958-105">Löschen Sie alle Website-oder Benutzerrichtlinien, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="83958-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="83958-106">Setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück.</span><span class="sxs-lookup"><span data-stu-id="83958-106">Reset the global policy to the default settings.</span></span> <span data-ttu-id="83958-107">Die standardmäßigen globalen Richtlinieneinstellungen verweigern den Zugriff durch externe Benutzer.</span><span class="sxs-lookup"><span data-stu-id="83958-107">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="83958-108">Die globale Richtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="83958-108">The global policy cannot be deleted.</span></span>


<span data-ttu-id="83958-109">Sie können eine beliebige Website-oder Benutzerrichtlinie löschen, die in der Skype for Business Server-Systemsteuerung auf der Seite **Richtlinie für den externen Zugriff** aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="83958-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="83958-110">Wenn Sie die globale Richtlinie löschen, wird Sie nicht tatsächlich gelöscht, sondern nur auf die Standardeinstellungen zurückgesetzt, die keine Unterstützung für externe Benutzerzugriffsoptionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="83958-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="83958-111">Ausführliche Informationen zum Zurücksetzen der globalen Richtlinie finden Sie unter [Zurücksetzen der globalen Richtlinie für den Zugriff durch externe Benutzer](reset-the-global-policy-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="83958-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="83958-112">So löschen Sie eine Standort- oder Benutzerrichtlinie für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="83958-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="83958-113">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="83958-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="83958-114">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="83958-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="83958-115">Klicken Sie auf **Externer Benutzerzugriff** und dann auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="83958-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="83958-116">Klicken Sie auf der Registerkarte **Richtlinie für den externen Zugriff** auf die zu löschende Standort- oder Benutzerrichtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="83958-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="83958-117">Klicken Sie zum Bestätigen des Löschvorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="83958-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="83958-118">Entfernen von PIN-Richtlinien mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="83958-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="83958-119">Richtlinien für den externen Zugriff können mithilfe von Windows PowerShell und dem Cmdlet Remove-CsExternalAccessPolicy gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="83958-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="83958-120">Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="83958-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="83958-121">So entfernen Sie eine bestimmte Richtlinie für den externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="83958-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="83958-122">Dieser Befehl entfernt die Richtlinie für den externen Zugriff, die auf den Standort "Redmond" angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="83958-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="83958-123">So entfernen Sie alle auf Benutzerebene angewendeten Richtlinien für den externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="83958-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="83958-124">Dieser Befehl entfernt alle Richtlinien für den externen Zugriff, die auf Benutzerbasis konfiguriert wurden:</span><span class="sxs-lookup"><span data-stu-id="83958-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="83958-125">So entfernen Sie alle externen Zugriffsrichtlinien, bei denen der Zugriff außerhalb des Benutzers deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="83958-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="83958-126">Dieser Befehl löscht alle Richtlinien für den externen Zugriff, für die der externe Benutzerzugriff deaktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="83958-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="83958-127">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="83958-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
