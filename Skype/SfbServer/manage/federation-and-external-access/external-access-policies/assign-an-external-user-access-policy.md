---
title: Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn ein Benutzer für Skype for Business Server aktiviert wurde, können Sie in der Skype for Business Server-Systemsteuerung SIP Federation, Remote User Access und Public Instant Messaging (im) konfigurieren, indem Sie die entsprechenden Richtlinien auf bestimmte Benutzer anwenden.
ms.openlocfilehash: ae8bea38a01f9211fc3338faf3e97f737c99e1a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280173"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="0ac34-103">Zuweisen einer Zugriffsrichtlinie für einen externen Benutzer zu einem Skype for Business-aktivierten Benutzer</span><span class="sxs-lookup"><span data-stu-id="0ac34-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="0ac34-104">Wenn ein Benutzer für Skype for Business Server aktiviert wurde, können Sie in der Skype for Business Server-Systemsteuerung SIP Federation, Remote User Access und Public Instant Messaging (im) konfigurieren, indem Sie die entsprechenden Richtlinien auf bestimmte Benutzer anwenden.</span><span class="sxs-lookup"><span data-stu-id="0ac34-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="0ac34-105">Wenn Sie beispielsweise eine Richtlinie zur Unterstützung des Remotebenutzerzugriffs erstellt haben, müssen Sie Sie auf den Benutzer anwenden, bevor der Benutzer von einem Remotestandort aus eine Verbindung mit Skype for Business Server herstellen und mit internen Benutzern am Remotestandort zusammenarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="0ac34-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="0ac34-106">Wenn Sie den Zugriff durch externe Benutzer unterstützen möchten, müssen Sie die Unterstützung für jeden Typ von externem Benutzer Zugriff aktivieren, den Sie unterstützen möchten, und die entsprechenden Richtlinien und anderen Optionen zum Steuern der Verwendung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0ac34-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="0ac34-107">Ausführliche Informationen finden Sie unter [Verwalten des Föderations-und externen Zugriffs auf Skype for Business Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="0ac34-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="0ac34-108">Verwenden Sie das in diesem Thema beschriebene Verfahren, um eine zuvor erstellte Richtlinie für den Benutzer Zugriff auf ein oder mehrere Benutzerkonten anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="0ac34-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="0ac34-109">So wenden Sie eine externe Benutzerrichtlinie auf ein Benutzerkonto an</span><span class="sxs-lookup"><span data-stu-id="0ac34-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="0ac34-110">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="0ac34-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0ac34-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0ac34-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0ac34-112">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="0ac34-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="0ac34-113">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="0ac34-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="0ac34-114">Wählen Sie in **Skype for Business Server-Benutzer bearbeiten** unter **Richtlinie für den externen Zugriff**die Benutzerrichtlinie aus, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="0ac34-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="0ac34-115">Die \*\* \<Automatic>\*\* -Einstellungen wenden den Standardserver oder die globalen Richtlinieneinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="0ac34-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0ac34-116">Zuweisen von externen Zugriffsrichtlinien für einzelne Benutzer mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0ac34-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0ac34-117">Richtlinien für den externen Zugriff pro Benutzer können mithilfe von Windows PowerShell und dem Cmdlet Grant-CsExternalAccessPolicy zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="0ac34-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="0ac34-118">Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0ac34-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="0ac34-119">So weisen Sie einem einzelnen Benutzer eine Richtlinie für den externen Zugriff pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="0ac34-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="0ac34-120">Mit diesem Befehl wird dem Benutzer Ken Myers die Richtlinie für den externen Zugriff per Benutzer RedmondExternalAccessPolicy zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0ac34-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="0ac34-121">So weisen Sie mehreren Benutzern eine Richtlinie für den externen Zugriff pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="0ac34-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="0ac34-122">Dieser Befehl weist allen Benutzern, die über Konten in der United States ou in Active Directory verfügen, die USAExternalAccessPolicy-Richtlinie für den externen Zugriff pro Benutzer zu.</span><span class="sxs-lookup"><span data-stu-id="0ac34-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="0ac34-123">Weitere Informationen zu dem in diesem Befehl verwendeten ou-Parameter finden Sie in der Dokumentation für das Cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="0ac34-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="0ac34-124">So heben Sie die Zuweisung einer externen Zugriffsrichtlinie für einzelne Benutzer auf</span><span class="sxs-lookup"><span data-stu-id="0ac34-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="0ac34-125">Mit diesem Befehl wird die Zuweisung einer externen Zugriffsrichtlinie für einzelne Benutzer aufheben, die Ken Myers zuvor zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="0ac34-125">This command unassigns any per-user external access policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="0ac34-126">Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="0ac34-126">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="0ac34-127">Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="0ac34-127">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="0ac34-128">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="0ac34-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>


