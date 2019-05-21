---
title: Anwenden einer Archivierungsrichtlinie auf Benutzer in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Benutzern in Skype for Business Server eine Archivierungsrichtlinie zuweisen.'
ms.openlocfilehash: 895a7fac34fcac0a4a7e39756796f6b7d2fc6377
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282049"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="5d734-103">Anwenden einer Archivierungsrichtlinie auf Benutzer in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5d734-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="5d734-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie Benutzern in Skype for Business Server eine Archivierungsrichtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5d734-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="5d734-105">Wenn Sie eine oder mehrere Benutzerrichtlinien für die Archivierung für Benutzer erstellt haben, die in Skype for Business Server verwaltet werden, können Sie Archivierungsunterstützung für bestimmte Benutzer implementieren, indem Sie die entsprechenden Richtlinien auf diese Benutzer oder Benutzergruppen anwenden.</span><span class="sxs-lookup"><span data-stu-id="5d734-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="5d734-106">Wenn Sie beispielsweise eine Richtlinie erstellen, um die Archivierung interner Kommunikation zu unterstützen, können Sie diese auf mindestens einen Benutzer oder eine Benutzergruppe anwenden, um die Archivierung der Skype for Business Server-Kommunikation des Benutzers zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5d734-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d734-107">Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktiviert haben, Steuern Exchange-in-situ-Speicherrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die sich in Exchange befinden, und dass ihre Postfächer in-situ-Speicher abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="5d734-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="5d734-108">Ausführliche Informationen finden Sie unter [Planen der Archivierung in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) und [Konfigurieren der Integration in Exchange Storage für Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="5d734-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="5d734-109">Anwenden einer Benutzerrichtlinie mithilfe der Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="5d734-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="5d734-110">So wenden Sie eine Benutzerrichtlinie mithilfe der Systemsteuerung an:</span><span class="sxs-lookup"><span data-stu-id="5d734-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="5d734-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="5d734-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="5d734-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5d734-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="5d734-113">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="5d734-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="5d734-114">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="5d734-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="5d734-115">Wählen Sie in **lync Server-Benutzer bearbeiten** unter **Archivierungsrichtlinie**die Archivierungs Benutzerrichtlinie aus, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="5d734-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5d734-116">Die \*\* \<automatischen\> \*\* Einstellungen gelten für die standardmäßigen Server Installationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="5d734-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="5d734-117">Diese Einstellungen werden vom Server automatisch übernommen.</span><span class="sxs-lookup"><span data-stu-id="5d734-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="5d734-118">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5d734-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="5d734-119">Anwenden einer Benutzerrichtlinie mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d734-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="5d734-120">Sie können eine Benutzerrichtlinie auch mithilfe des Windows PowerShell-Cmdlets **Grant-CsArchivingPolicy** anwenden.</span><span class="sxs-lookup"><span data-stu-id="5d734-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="5d734-121">Mithilfe des folgenden Befehls wird die benutzerbezogene Archivierungsrichtlinie „RedmondArchivingPolicy“ dem Benutzer Jonas Baar zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="5d734-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="5d734-122">Der folgende Befehl weist die benutzerbezogene Archivierungsrichtlinie „RedmondArchivingPolicy“ allen Benutzern zu, deren Konten sich auf dem Registrierungsstellenpool „atl-cs-001.contoso.com“ befinden.</span><span class="sxs-lookup"><span data-stu-id="5d734-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="5d734-123">Details zu dem in diesem Befehl verwendeten Filter Parameter finden Sie in der Dokumentation zum Cmdlet " [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) ".</span><span class="sxs-lookup"><span data-stu-id="5d734-123">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="5d734-p105">Mithilfe des folgenden Befehls wird die Zuordnung aller benutzerbezogenen Archivierungsrichtlinien aufgehoben, die zuvor Jonas Baar zugeordnet wurden. Nach dem Aufheben der Zuordnung der benutzerbezogenen Richtlinie wird Jonas Baar automatisch mithilfe der globalen Richtlinie oder, sofern vorhanden, mithilfe seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="5d734-p105">The following command removes any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="5d734-127">Ausführliche Informationen finden Sie in der Dokumentation zu [Grant-CsArchivingPolicy-](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="5d734-127">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

