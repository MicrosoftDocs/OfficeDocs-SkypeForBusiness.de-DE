---
title: Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn ein Benutzer für Skype für Business Server aktiviert wurde, können Sie die SIP-Verbund, Remotebenutzerzugriff und öffentlichen Instant messaging-Diensten in der Skype Business Server-Systemsteuerung durch Anwenden geeigneten Richtlinien auf bestimmte Benutzer konfigurieren.
ms.openlocfilehash: f07a407fee6f32f4cd4207c93ca19341e409ea78
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881500"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="22f27-103">Zuweisen einer Richtlinie für den externen Benutzerzugriff zu einer Skype für Geschäftsbenutzer aktiviert</span><span class="sxs-lookup"><span data-stu-id="22f27-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="22f27-104">Wenn ein Benutzer für Skype für Business Server aktiviert wurde, können Sie die SIP-Verbund, Remotebenutzerzugriff und öffentlichen Instant messaging-Diensten in der Skype Business Server-Systemsteuerung durch Anwenden geeigneten Richtlinien auf bestimmte Benutzer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="22f27-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="22f27-105">Beispielsweise wenn Sie eine Richtlinie zur Unterstützung des Zugriffs durch Remotebenutzer erstellt haben, müssen Sie sie anwenden, die dem Benutzer, bevor der Benutzer kann und Herstellen einer Verbindung mit Skype für Business Server von einem Remotestandort mit internen Benutzern von remote-Standort zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="22f27-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="22f27-106">Zur Unterstützung der Zugriff durch externe Benutzer müssen Sie Aktivieren der Unterstützung für jede Art von Zugriff durch externe Benutzer, den Sie unterstützen möchten, und konfigurieren Sie geeigneten Richtlinien und andere Optionen, deren Verwendung steuern.</span><span class="sxs-lookup"><span data-stu-id="22f27-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="22f27-107">Weitere Informationen hierzu finden Sie unter [Managing Federation und externen Zugriff auf Skype für Business Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="22f27-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="22f27-108">Verwenden Sie das Verfahren in diesem Thema, um eine zuvor erstellte externe Benutzerrichtlinie auf einen oder mehrere Benutzerkonten anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="22f27-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="22f27-109">Anwenden eine Richtlinie für externe Benutzer auf ein Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="22f27-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="22f27-110">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="22f27-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="22f27-111">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="22f27-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="22f27-112">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="22f27-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="22f27-113">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="22f27-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="22f27-114">Wählen Sie in **Skype für Business Server-Benutzer bearbeiten** unter **Richtlinie für den externen Zugriff**die Benutzerrichtlinie aus, der Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="22f27-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="22f27-115">Die \*\* \<Automatic>\*\* Einstellungen gelten die Standardeinstellungen des Servers oder globale Richtlinieneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="22f27-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="22f27-116">Zuweisen von Richtlinien für externen Zugriff pro Benutzer mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="22f27-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="22f27-117">Richtlinien für externen Zugriff pro Benutzer können mithilfe von Windows PowerShell und dem Grant-CsExternalAccessPolicy-Cmdlet zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="22f27-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="22f27-118">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="22f27-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="22f27-119">So weisen eine externe Zugriffsrichtlinie pro Benutzer zu einem einzelnen Benutzer</span><span class="sxs-lookup"><span data-stu-id="22f27-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="22f27-120">Mit diesem Befehl wird dem Benutzer Ken Myer die externen Zugriff benutzerbasierte Richtlinie "redmondexternalaccesspolicy" zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="22f27-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="22f27-121">So weisen eine externe Zugriffsrichtlinie pro Benutzer zu mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="22f27-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="22f27-122">Dieser Befehl weist die benutzerbasierte Zugriff durch externe Richtlinie USAExternalAccessPolicy alle Benutzer mit Konten in den Vereinigten Staaten Organisationseinheit in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="22f27-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="22f27-123">Weitere Informationen zu der OU-Parameter, die in dieser Befehl verwendet finden Sie in der Dokumentation für das Cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="22f27-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="22f27-124">Zum Aufheben der Zuweisung einer externen Zugriffsrichtlinie pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="22f27-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="22f27-125">Mit diesem Befehl unassigns pro Benutzer externe Zugriffsrichtlinien zuvor Ken Myer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="22f27-125">This command unassigns any per-user external access policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="22f27-126">Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="22f27-126">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="22f27-127">Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="22f27-127">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="22f27-128">Weitere Informationen finden Sie im Hilfethema zum [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="22f27-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>


