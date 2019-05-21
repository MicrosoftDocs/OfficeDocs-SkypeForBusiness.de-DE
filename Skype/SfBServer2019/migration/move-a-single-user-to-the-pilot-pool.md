---
title: Verschieben eines einzelnen Benutzers in den Pilot Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können einen Benutzer aus Ihrem Legacy Pool in Ihren Skype for Business Server 2019-Pilot Pool mit der Skype for Business Server 2019-Systemsteuerung oder der Skype for Business Server 2019-Verwaltungsshell verschieben. Im folgenden Beispiel ist in der Spalte "Registrar Pool" pool01.contoso.net der Legacy Pool, und alle sechs dieser Benutzer sind mit diesem Pool verbunden. Führen Sie die folgenden Verfahren aus, um einen Benutzer in den Skype for Business Server 2019-Pool mit der Skype for Business Server 2019-Systemsteuerung und der Skype for Business Server-Verwaltungsshell zu verschieben.
ms.openlocfilehash: 23ce56f8bcf759aeeaa9e9a9b64820958c656c6a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298134"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="efd3d-105">Verschieben eines einzelnen Benutzers in den Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="efd3d-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="efd3d-106">Sie können einen Benutzer aus Ihrem Legacy Pool in Ihren Skype for Business Server 2019-Pilot Pool mit der Skype for Business Server 2019-Systemsteuerung oder der Skype for Business Server 2019-Verwaltungsshell verschieben.</span><span class="sxs-lookup"><span data-stu-id="efd3d-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="efd3d-107">Im folgenden Beispiel ist in der Spalte " **Registrar Pool** " **pool01.contoso.net** der Legacy Pool, und alle sechs dieser Benutzer sind mit diesem Pool verbunden.</span><span class="sxs-lookup"><span data-stu-id="efd3d-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="efd3d-108">Führen Sie die folgenden Verfahren aus, um einen Benutzer in den Skype for Business Server 2019-Pool mit der Skype for Business Server 2019-Systemsteuerung und der Skype for Business Server-Verwaltungsshell zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="efd3d-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="efd3d-109">So verschieben Sie einen Benutzer mithilfe der Skype for Business Server 2019-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="efd3d-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="efd3d-110">Melden Sie sich über ein Konto, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsAdministrator“ oder „CsUserAdministrator“ ist, am Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="efd3d-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="efd3d-111">Öffnen Sie die **Skype for Business Server-System**Steuerung.</span><span class="sxs-lookup"><span data-stu-id="efd3d-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="efd3d-112">Klicken Sie auf **Benutzer**, klicken Sie auf **Suchen**, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="efd3d-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="efd3d-113">Wählen Sie einen Benutzer aus, den Sie in den Skype for Business Server 2019-Pool verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="efd3d-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="efd3d-114">In diesem Beispiel verschieben wir den Benutzer Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="efd3d-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="efd3d-115">Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben** aus.</span><span class="sxs-lookup"><span data-stu-id="efd3d-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="efd3d-116">Wählen Sie in der Dropdownliste den Skype for Business Server 2019-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="efd3d-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="efd3d-117">Klicken Sie auf **Aktion**und dann auf **ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="efd3d-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="efd3d-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="efd3d-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="efd3d-119">Überprüfen Sie, ob die Spalte des **registrierungspools** für den Benutzer jetzt den Skype for Business Server 2019-Pool enthält, der angibt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="efd3d-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="efd3d-120">So verschieben Sie einen Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="efd3d-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="efd3d-121">Öffnen Sie die Skype for Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="efd3d-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="efd3d-122">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="efd3d-122">At the command line, type the following:</span></span> 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="efd3d-123">Geben Sie als nächstes in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="efd3d-123">Next, at the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="efd3d-124">Die **RegistrarPool** -Identität verweist nun auf den Skype for Business Server 2019-Pool.</span><span class="sxs-lookup"><span data-stu-id="efd3d-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="efd3d-125">Das vorhanden sein dieser Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="efd3d-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="efd3d-126">Details zum Cmdlet " **Get-CsUser** " finden Sie unter **Get-Help Get-CsUser-detailed** .</span><span class="sxs-lookup"><span data-stu-id="efd3d-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

