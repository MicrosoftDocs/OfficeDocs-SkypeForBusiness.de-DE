---
title: Verschieben eines einzelnen Benutzers in den pilotpool
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können einen Benutzer aus Ihrem vorversionspool in Ihrer Skype für Business Server 2019 pilot Pool mit Skype für Business Server 2019-Systemsteuerung oder Skype für Business Server 2019-Verwaltungsshell verschieben. Im folgenden Beispiel, in der Spalte Registrierungspool pool01.contoso.net Pool der Vorgängerversion ist, und alle sechs dieser Benutzer mit diesem Pool verbunden sind. Verwenden Sie die folgenden Verfahren, um einen Benutzer in Ihrer Skype für mithilfe von Skype für Business Server 2019-Systemsteuerung und Skype für Business Server-Verwaltungsshell Business Server 2019 Pool verschieben.
ms.openlocfilehash: 6742c5fc00c9d53030ac32ee698686bb8b11fa07
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372745"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="943dc-105">Verschieben eines einzelnen Benutzers in den pilotpool</span><span class="sxs-lookup"><span data-stu-id="943dc-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="943dc-106">Sie können einen Benutzer aus Ihrem vorversionspool in Ihrer Skype für Business Server 2019 pilot Pool mit Skype für Business Server 2019-Systemsteuerung oder Skype für Business Server 2019-Verwaltungsshell verschieben.</span><span class="sxs-lookup"><span data-stu-id="943dc-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="943dc-107">Im folgenden Beispiel, in der Spalte **registrierungspool** **pool01.contoso.net** Pool der Vorgängerversion ist, und alle sechs dieser Benutzer mit diesem Pool verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="943dc-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="943dc-108">Verwenden Sie die folgenden Verfahren, um einen Benutzer in Ihrer Skype für mithilfe von Skype für Business Server 2019-Systemsteuerung und Skype für Business Server-Verwaltungsshell Business Server 2019 Pool verschieben.</span><span class="sxs-lookup"><span data-stu-id="943dc-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="943dc-109">Zum Verschieben eines Benutzers mithilfe der Skype für Business Server 2019-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="943dc-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="943dc-110">Melden Sie sich über ein Konto, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsAdministrator“ oder „CsUserAdministrator“ ist, am Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="943dc-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="943dc-111">**Skype für Business Server-Systemsteuerung**zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="943dc-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="943dc-112">Klicken Sie auf **Benutzer**, klicken Sie auf **Suchen**, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="943dc-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="943dc-113">Wählen Sie einen Benutzer, den Sie in der Skype für Business Server 2019 Pool verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="943dc-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="943dc-114">In diesem Beispiel wird es Benutzer Sara Davis verschoben.</span><span class="sxs-lookup"><span data-stu-id="943dc-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="943dc-115">Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben** aus.</span><span class="sxs-lookup"><span data-stu-id="943dc-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="943dc-116">Wählen Sie aus der Dropdownliste die Skype für Business Server 2019 Pool aus.</span><span class="sxs-lookup"><span data-stu-id="943dc-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="943dc-117">Klicken Sie auf **Aktion**, und klicken Sie dann auf **ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="943dc-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="943dc-118">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="943dc-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="943dc-119">Stellen Sie sicher, dass die Spalte **Registrierungsstellenpool** für den Benutzer enthält nun die Skype für Business Server 2019 Pool, die angibt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="943dc-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="943dc-120">Zum Verschieben eines Benutzers mithilfe der Skype für Business Server 2019-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="943dc-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="943dc-121">Öffnen Sie die Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="943dc-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="943dc-122">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="943dc-122">At the command line, type the following:</span></span> 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="943dc-123">Geben Sie im nächsten Schritt in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="943dc-123">Next, at the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="943dc-124">Die Identität des **RegistrarPool** zeigt jetzt auf das Skype für Business Server 2019 Pool.</span><span class="sxs-lookup"><span data-stu-id="943dc-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="943dc-125">Das Vorhandensein von diese Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="943dc-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="943dc-126">Weitere Informationen zum **Get-CsUser** -Cmdlet ausführen: **Get-Help Get-CsUser-Detailed**</span><span class="sxs-lookup"><span data-stu-id="943dc-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

