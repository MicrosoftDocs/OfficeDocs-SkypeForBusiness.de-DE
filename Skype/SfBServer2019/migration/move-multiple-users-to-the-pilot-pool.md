---
title: Mehrere Benutzer in den Pilot Pool migrieren
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Sie können mehrere Benutzer aus Ihrem Legacy Pool mithilfe Skype for Business Server 2019-Systemsteuerung oder Skype for Business Server 2019-Verwaltungsshell in Ihren Skype for Business Server 2019-Pilot Pool migrieren.
ms.openlocfilehash: d1b003c5630a0917fbecbd9b04196675657fef83
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753427"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="435d3-103">Mehrere Benutzer in den Pilot Pool migrieren</span><span class="sxs-lookup"><span data-stu-id="435d3-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="435d3-104">Sie können mehrere Benutzer aus Ihrem Legacy Pool mithilfe Skype for Business Server 2019-Systemsteuerung oder Skype for Business Server 2019-Verwaltungsshell in Ihren Skype for Business Server 2019-Pilot Pool migrieren.</span><span class="sxs-lookup"><span data-stu-id="435d3-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="435d3-105">**Inhalt dieses Artikels**</span><span class="sxs-lookup"><span data-stu-id="435d3-105">**In this article**</span></span>
  
[<span data-ttu-id="435d3-106">So können Sie mehrere Benutzer mithilfe der Systemsteuerung von Skype for Business Server 2019 migrieren</span><span class="sxs-lookup"><span data-stu-id="435d3-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="435d3-107">So migrieren Sie mehrere Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="435d3-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="435d3-108">So führen Sie eine gleichzeitige Verlagerung aller Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell aus</span><span class="sxs-lookup"><span data-stu-id="435d3-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="435d3-109">So können Sie mehrere Benutzer mithilfe der Systemsteuerung von Skype for Business Server 2019 migrieren</span><span class="sxs-lookup"><span data-stu-id="435d3-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="435d3-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="435d3-110"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="435d3-111">Öffnen Sie Skype for Business Server Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="435d3-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="435d3-112">Klicken Sie auf **Benutzer**, klicken Sie auf **Suchen**, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="435d3-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="435d3-113">Wählen Sie zwei Benutzer aus, die Sie zum Pool Skype for Business Server 2019 migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="435d3-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="435d3-114">In diesem Beispiel werden wir die Benutzer Chen Yang und Claus Hansen verschieben.</span><span class="sxs-lookup"><span data-stu-id="435d3-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![Migrieren von Benutzern zu einem bestimmten Register Pool](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="435d3-116">Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben** aus.</span><span class="sxs-lookup"><span data-stu-id="435d3-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="435d3-117">Wählen Sie in der Dropdownliste den Skype for Business Server Pool 2019 aus.</span><span class="sxs-lookup"><span data-stu-id="435d3-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="435d3-118">Klicken Sie auf **Aktion** und dann auf **Ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="435d3-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="435d3-119">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="435d3-119">Click **OK**.</span></span>
    
     ![Dialogfeld zum Migrieren von Benutzern, Ziel registrierungsstellenpool](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="435d3-121">Stellen Sie sicher, dass die Spalte **Registrierungspool** für die Benutzer jetzt den Skype for Business Server 2019-Pool enthält, der angibt, dass die Benutzer erfolgreich verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="435d3-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="435d3-122">So migrieren Sie mehrere Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="435d3-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="435d3-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="435d3-123"><a name="sectionSection1"> </a></span></span>

1. <span data-ttu-id="435d3-124">Öffnen Sie die Skype for Business Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="435d3-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="435d3-125">Geben Sie an der Befehlszeile Folgendes ein, und ersetzen Sie **User1** und **Benutzer2** durch bestimmte Benutzernamen, die Sie wechseln möchten, und ersetzen Sie **pool_FQDN** durch den Namen des Ziel Pools.</span><span class="sxs-lookup"><span data-stu-id="435d3-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="435d3-126">In diesem Beispiel verschieben wir die Benutzer Hao Chen und Katie Jordan.</span><span class="sxs-lookup"><span data-stu-id="435d3-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Beispiel für das PowerShell Get-CsUser-Cmdlet](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="435d3-128">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="435d3-128">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="435d3-129">Die **Registrierungspool**-Identität sollte jetzt auf den Pool zeigen, den Sie im vorherigen Schritt als **pool_FQDN** angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="435d3-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="435d3-130">Das Vorhandensein dieser Identität bestätigt, dass die Benutzer erfolgreich verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="435d3-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="435d3-131">Wiederholen Sie den Schritt, um zu überprüfen, ob **Benutzer2** verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="435d3-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![Ausgabe des PowerShell Get-UsUser-Identity-Cmdlets](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="435d3-133">So führen Sie eine gleichzeitige Verlagerung aller Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell aus</span><span class="sxs-lookup"><span data-stu-id="435d3-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="435d3-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="435d3-134"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="435d3-135">In diesem Beispiel wurden alle Benutzer an den Legacy Pool (pool01.contoso.net) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="435d3-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="435d3-136">Mithilfe der Skype for Business Server 2019-Verwaltungsshell werden alle Benutzer gleichzeitig in den Skype for Business Server 2019-Pool (pool02.contoso.net) verlagert.</span><span class="sxs-lookup"><span data-stu-id="435d3-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="435d3-137">Öffnen Sie die Skype for Business Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="435d3-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="435d3-138">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="435d3-138">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell-Cmdlet und Ergebnisse in der Verwaltungskonsole](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="435d3-140">Führen **Sie Get-CsUser** für einen der Pilotbenutzer aus.</span><span class="sxs-lookup"><span data-stu-id="435d3-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="435d3-141">Die Identität des **Registrierungsstellen Pools** für jeden Benutzer verweist nun auf den Pool, den Sie im vorherigen Schritt als **pool_FQDN** angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="435d3-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="435d3-142">Das Vorhandensein dieser Identität zeigt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="435d3-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="435d3-143">Darüber hinaus können wir die Liste der Benutzer in der Skype for Business Server 2019-Systemsteuerung anzeigen und überprüfen, ob der Wert des Registrierungsstellen Pools nun auf den Skype for Business Server 2019-Pool zeigt.</span><span class="sxs-lookup"><span data-stu-id="435d3-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Skype for Business Server 2019-Benutzerliste der Systemsteuerung](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

