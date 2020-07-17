---
title: Verlagern eines einzelnen Benutzers in den Pilot Pool
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
description: Sie können einen Benutzer aus Ihrem Legacy Pool mithilfe Skype for Business Server 2019-Systemsteuerung oder Skype for Business Server 2019-Verwaltungsshell in Ihren Skype for Business Server 2019-Pilot Pool migrieren. Im Beispiel unten in der Spalte registrierungsstellenpool ist pool01.contoso.net der Legacy Pool, und alle sechs dieser Benutzer sind mit diesem Pool verbunden. Verwenden Sie die folgenden Verfahren, um einen Benutzer zu Ihrem Skype for Business Server 2019-Pool mit Skype for Business Server 2019-Systemsteuerung und Skype for Business Server Verwaltungsshell zu migrieren.
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752507"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="e33c1-105">Verlagern eines einzelnen Benutzers in den Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="e33c1-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="e33c1-106">Sie können einen Benutzer aus Ihrem Legacy Pool mithilfe Skype for Business Server 2019-Systemsteuerung oder Skype for Business Server 2019-Verwaltungsshell in Ihren Skype for Business Server 2019-Pilot Pool migrieren.</span><span class="sxs-lookup"><span data-stu-id="e33c1-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="e33c1-107">Im Beispiel unten in der Spalte **registrierungsstellenpool** ist **pool01.contoso.net** der Legacy Pool, und alle sechs dieser Benutzer sind mit diesem Pool verbunden.</span><span class="sxs-lookup"><span data-stu-id="e33c1-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="e33c1-108">Verwenden Sie die folgenden Verfahren, um einen Benutzer zu Ihrem Skype for Business Server 2019-Pool mit Skype for Business Server 2019-Systemsteuerung und Skype for Business Server Verwaltungsshell zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="e33c1-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="e33c1-109">So migrieren Sie einen Benutzer mithilfe der Systemsteuerung Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e33c1-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="e33c1-110">Melden Sie sich über ein Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder der Administratorrolle "CsAdministrator" oder "CsUserAdministrator" ist, am Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="e33c1-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="e33c1-111">Öffnen Sie **Skype for Business Server System**Steuerung.</span><span class="sxs-lookup"><span data-stu-id="e33c1-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="e33c1-112">Klicken Sie auf **Benutzer**, klicken Sie auf **Suchen**, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="e33c1-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="e33c1-113">Wählen Sie einen Benutzer aus, den Sie in den Skype for Business Server 2019-Pool umlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="e33c1-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="e33c1-114">In diesem Beispiel verschieben wir Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="e33c1-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="e33c1-115">Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="e33c1-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="e33c1-116">Wählen Sie in der Dropdownliste den Skype for Business Server Pool 2019 aus.</span><span class="sxs-lookup"><span data-stu-id="e33c1-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="e33c1-117">Klicken Sie auf **Aktion** und dann auf **Ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="e33c1-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="e33c1-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e33c1-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="e33c1-119">Stellen Sie sicher, dass die Spalte **Registrierungspool** für den Benutzer jetzt den Skype for Business Server 2019-Pool enthält, der angibt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="e33c1-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="e33c1-120">So migrieren Sie einen Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="e33c1-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="e33c1-121">Öffnen Sie die Skype for Business Server Management-Shell.</span><span class="sxs-lookup"><span data-stu-id="e33c1-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="e33c1-122">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e33c1-122">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="e33c1-123">Geben Sie anschließend an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e33c1-123">Next, at the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="e33c1-124">Die **RegistrarPool** -Identität verweist nun auf den Pool Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e33c1-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="e33c1-125">Das Vorhandensein dieser Identität zeigt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="e33c1-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="e33c1-126">Ausführliche Informationen zum **Get-CsUser** -Cmdlet finden Sie unter: **Get-Help Get-CsUser-detailed**</span><span class="sxs-lookup"><span data-stu-id="e33c1-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

