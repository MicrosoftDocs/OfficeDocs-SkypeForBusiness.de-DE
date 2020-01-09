---
title: Verschieben mehrerer Benutzer in den Pilot Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können mehrere Benutzer aus Ihrem Legacy Pool in Ihren Skype for Business Server 2019-Pilot Pool mit der Skype for Business Server 2019-Systemsteuerung oder der Skype for Business Server 2019-Verwaltungsshell verschieben.
ms.openlocfilehash: abaffea04ff190b2ae99639484f63b564fd7784a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988950"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="57c5d-103">Verschieben mehrerer Benutzer in den Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="57c5d-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="57c5d-104">Sie können mehrere Benutzer aus Ihrem Legacy Pool in Ihren Skype for Business Server 2019-Pilot Pool mit der Skype for Business Server 2019-Systemsteuerung oder der Skype for Business Server 2019-Verwaltungsshell verschieben.</span><span class="sxs-lookup"><span data-stu-id="57c5d-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="57c5d-105">**In diesem Artikel**</span><span class="sxs-lookup"><span data-stu-id="57c5d-105">**In this article**</span></span>
  
[<span data-ttu-id="57c5d-106">So verschieben Sie mehrere Benutzer mithilfe der Skype for Business Server 2019-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="57c5d-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="57c5d-107">So verschieben Sie mehrere Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="57c5d-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="57c5d-108">So verschieben Sie alle Benutzer gleichzeitig mithilfe der Skype for Business Server 2019-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="57c5d-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="57c5d-109">So verschieben Sie mehrere Benutzer mithilfe der Skype for Business Server 2019-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="57c5d-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="57c5d-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="57c5d-110"></span></span>

1. <span data-ttu-id="57c5d-111">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="57c5d-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="57c5d-112">Klicken Sie auf **Benutzer**, klicken Sie auf **Suchen**, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="57c5d-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="57c5d-113">Wählen Sie zwei Benutzer aus, die Sie in den Skype for Business Server 2019-Pool verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="57c5d-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="57c5d-114">In diesem Beispiel werden die Benutzer Chen Yang und Claus Hansen verschoben.</span><span class="sxs-lookup"><span data-stu-id="57c5d-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![Verschieben von Benutzern in einen bestimmten Registrierungspool](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="57c5d-116">Wählen Sie im Menü **Aktion** die Option **ausgewählte Benutzer in Pool verschieben**aus.</span><span class="sxs-lookup"><span data-stu-id="57c5d-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="57c5d-117">Wählen Sie in der Dropdownliste den Skype for Business Server 2019-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="57c5d-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="57c5d-118">Klicken Sie auf **Aktion**und dann auf **ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="57c5d-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="57c5d-119">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="57c5d-119">Click **OK**.</span></span>
    
     ![Dialogfeld ' Benutzer verschieben, Ziel Registrierungspool '](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="57c5d-121">Überprüfen Sie, ob die Spalte des **registrierungspools** für die Benutzer jetzt den Skype for Business Server 2019-Pool enthält, der angibt, dass die Benutzer erfolgreich verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="57c5d-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="57c5d-122">So verschieben Sie mehrere Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="57c5d-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="57c5d-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="57c5d-123"></span></span>

1. <span data-ttu-id="57c5d-124">Öffnen Sie die Skype for Business Server 2019-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="57c5d-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="57c5d-125">Geben Sie in der Befehlszeile Folgendes ein, und ersetzen Sie **Benutzer1** und **User2** durch bestimmte Benutzernamen, die Sie verschieben möchten, und ersetzen Sie **pool_FQDN** durch den Namen des Ziel Pools.</span><span class="sxs-lookup"><span data-stu-id="57c5d-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="57c5d-126">In diesem Beispiel werden die Benutzer Hao Chen und Katie Jordan verschoben.</span><span class="sxs-lookup"><span data-stu-id="57c5d-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Beispiel für ein PowerShell-Cmdlet "Get-CsUser"](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="57c5d-128">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="57c5d-128">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="57c5d-129">Die Identität des **Registrierungsstellen Pools** sollte nun auf den Pool verweisen, den Sie im vorherigen Schritt als **pool_FQDN** angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="57c5d-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="57c5d-130">Das vorhanden sein dieser Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="57c5d-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="57c5d-131">Wiederholen Sie den Schritt, um zu überprüfen, ob **User2** verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="57c5d-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![Ausgabe des PowerShell-Cmdlets Get-UsUser-Identity](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="57c5d-133">So verschieben Sie alle Benutzer gleichzeitig mithilfe der Skype for Business Server 2019-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="57c5d-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="57c5d-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="57c5d-134"></span></span>

<span data-ttu-id="57c5d-135">In diesem Beispiel wurden alle Benutzer an den Legacy Pool (pool01.contoso.net) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="57c5d-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="57c5d-136">Mit der Skype for Business Server 2019-Verwaltungsshell werden alle Benutzer gleichzeitig in den Skype for Business Server 2019-Pool (pool02.contoso.net) verschoben.</span><span class="sxs-lookup"><span data-stu-id="57c5d-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="57c5d-137">Öffnen Sie die Skype for Business Server 2019-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="57c5d-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="57c5d-138">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="57c5d-138">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell-Cmdlet und Ergebnisse in der Verwaltungsshell](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="57c5d-140">Führen **Sie Get-CsUser** für einen der Pilotbenutzer aus.</span><span class="sxs-lookup"><span data-stu-id="57c5d-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="57c5d-141">Die Identität des **registrierungspools** für jeden Benutzer verweist nun auf den Pool, den Sie im vorherigen Schritt als **pool_FQDN** angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="57c5d-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="57c5d-142">Das vorhanden sein dieser Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="57c5d-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="57c5d-143">Darüber hinaus können wir die Liste der Benutzer in der Systemsteuerung von Skype for Business Server 2019 anzeigen und überprüfen, ob der Wert des registrierungspools nun auf den Skype for Business Server 2019-Pool verweist.</span><span class="sxs-lookup"><span data-stu-id="57c5d-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Skype for Business Server 2019 Control Panel-Benutzerliste](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

