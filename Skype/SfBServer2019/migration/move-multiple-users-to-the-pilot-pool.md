---
title: Verschieben Sie mehrerer Benutzer in den pilotpool
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können mehrere Benutzer in Ihrer Skype für Business Server 2019 pilot Pool mit Skype für Business Server 2019-Systemsteuerung oder Skype für Business Server 2019-Verwaltungsshell aus Ihrem legacy-Pool verschieben.
ms.openlocfilehash: e96ef658f566f0e069f4db6e4f2f08e0410ea260
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028656"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="e5dd2-103">Verschieben Sie mehrerer Benutzer in den pilotpool</span><span class="sxs-lookup"><span data-stu-id="e5dd2-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="e5dd2-104">Sie können mehrere Benutzer in Ihrer Skype für Business Server 2019 pilot Pool mit Skype für Business Server 2019-Systemsteuerung oder Skype für Business Server 2019-Verwaltungsshell aus Ihrem legacy-Pool verschieben.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="e5dd2-105">**In diesem Artikel**</span><span class="sxs-lookup"><span data-stu-id="e5dd2-105">**In this article**</span></span>
  
[<span data-ttu-id="e5dd2-106">So verschieben Sie mehrere Benutzer mithilfe der Skype für Business Server 2019-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="e5dd2-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="e5dd2-107">So verschieben Sie mehrere Benutzer mithilfe der Skype für Business Server 2019-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="e5dd2-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="e5dd2-108">So verschieben Sie alle Benutzer gleichzeitig mithilfe der Skype für Business Server 2019-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="e5dd2-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="e5dd2-109">So verschieben Sie mehrere Benutzer mithilfe der Skype für Business Server 2019-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="e5dd2-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="e5dd2-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="e5dd2-110"></span></span>

1. <span data-ttu-id="e5dd2-111">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="e5dd2-112">Klicken Sie auf **Benutzer**, klicken Sie auf **Suchen**, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="e5dd2-113">Wählen Sie zwei Benutzer, die Sie in der Skype für Business Server 2019 Pool verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="e5dd2-114">In diesem Beispiel wird es Benutzern Chen Yang und Claus Hansen verschoben.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![Migrieren von Benutzern zu bestimmten Register-pool](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="e5dd2-116">Wählen Sie im Menü **Aktion** **ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="e5dd2-117">Wählen Sie aus der Dropdownliste die Skype für Business Server 2019 Pool aus.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="e5dd2-118">Klicken Sie auf **Aktion**, und klicken Sie dann auf **ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="e5dd2-119">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-119">Click **OK**.</span></span>
    
     ![Verschieben von Benutzern im Dialogfeld Registrar-Pool Ziel](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="e5dd2-121">Stellen Sie sicher, dass die Spalte **Registrierungsstellenpool** für die Benutzer enthält nun die Skype für Business Server 2019 Pool, die angibt, dass die Benutzer erfolgreich verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="e5dd2-122">So verschieben Sie mehrere Benutzer mithilfe der Skype für Business Server 2019-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="e5dd2-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="e5dd2-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="e5dd2-123"></span></span>

1. <span data-ttu-id="e5dd2-124">Öffnen Sie die Skype für Business Server 2019-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2.  <span data-ttu-id="e5dd2-125">In der Befehlszeile Folgendes ein, und Ersetzen Sie **User1** und **User2** durch die betreffenden Benutzernamen, den, die Sie verschieben möchten, und Ersetzen Sie **Pool_FQDN** durch den Namen des zielpools.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="e5dd2-126">In diesem Beispiel wird es Benutzern Hao Chen und Katie Jordanien verschoben.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
  ```
  Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
  ```

     ![Beispiel für PowerShell Get-CsUser-cmdlet](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="e5dd2-128">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e5dd2-128">At the command line, type the following:</span></span> 
    
  ```
  Get-CsUser -Identity "User1"
  ```

4. <span data-ttu-id="e5dd2-129">Die Identität des **Registrar-Pools** sollten nun auf den Pool verweisen, den Sie als **Pool_FQDN** im vorherigen Schritt angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="e5dd2-130">Das Vorhandensein von diese Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="e5dd2-131">Wiederholen Sie Schritt zu überprüfen, ob **Benutzer2** verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![Ausgabe von PowerShell Get-UsUser-Identity-Cmdlet](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="e5dd2-133">So verschieben Sie alle Benutzer gleichzeitig mithilfe der Skype für Business Server 2019-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="e5dd2-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="e5dd2-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="e5dd2-134"></span></span>

<span data-ttu-id="e5dd2-135">In diesem Beispiel wurden alle Benutzer auf den Pool der Vorgängerversion (pool01.contoso.net) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="e5dd2-136">Die Skype für Business Server 2019-Verwaltungsshell verwenden, werden wir alle Benutzer gleichzeitig in die Skype für Business Server 2019 Pool (pool02.contoso.net) verschoben.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="e5dd2-137">Öffnen Sie die Skype für Business Server 2019-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="e5dd2-138">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e5dd2-138">At the command line, type the following:</span></span> 
    
  ```
  Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
  ```

     ![PowerShell-Cmdlets und die Ergebnisse in der-Verwaltungsshell](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="e5dd2-140">Führen Sie **Get-CsUser** für einen der Pilotbenutzer aus.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
  ```
  Get-CsUser -Identity "Hao Chen"
  ```

4. <span data-ttu-id="e5dd2-141">Die **Registrar-Pool** -Identität für jeden Benutzer zeigt jetzt auf den Pool, den Sie als **Pool_FQDN** im vorherigen Schritt angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="e5dd2-142">Das Vorhandensein von diese Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="e5dd2-143">Darüber hinaus können wir zeigt eine Liste von Benutzern in der Skype Business Server 2019-Systemsteuerung, und stellen Sie sicher, dass der Wert des Registrierungspools jetzt auf das Skype für Business Server 2019 Pool verweist.</span><span class="sxs-lookup"><span data-stu-id="e5dd2-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Skype für Benutzerliste Business Server 2019-Systemsteuerung](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

