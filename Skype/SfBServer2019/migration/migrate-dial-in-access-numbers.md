---
title: Migrieren von Einwahl Zugriffsnummern
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Migrieren von Einwahlnummern Zahlen zu Skype für Business Server 2019 erforderlich sind, mit dem Cmdlet Move-CsApplicationEndpoint die Kontaktobjekte zu migrieren. Während der Vorversion installieren und Skype für Business Server 2019 Koexistenz Zeitraum Verhalten sich Einwahlnummern Zahlen, die Sie in Skype für Business Server 2019 erstellt haben ähnlich wie DFÜ-Zugriff Zahlen, die Sie in der Vorversion installieren, erstellen Sie wie beschrieben in diesem Abschnitt.
ms.openlocfilehash: 62d2d4f34f109c265a72a92283082601bd92b40b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027725"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="358c9-104">Migrieren von Einwahl Zugriffsnummern</span><span class="sxs-lookup"><span data-stu-id="358c9-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="358c9-105">Migrieren von Einwahlnummern Zahlen zu Skype für Business Server 2019 erforderlich sind, mit dem Cmdlet **Move-CsApplicationEndpoint** die Kontaktobjekte zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="358c9-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="358c9-106">Während der Vorversion installieren und Skype für Business Server 2019 Koexistenz Zeitraum Verhalten sich Einwahlnummern Zahlen, die Sie in Skype für Business Server 2019 erstellt haben ähnlich wie DFÜ-Zugriff Zahlen, die Sie in der Vorversion installieren, erstellen Sie wie beschrieben in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="358c9-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 
  
<span data-ttu-id="358c9-107">DFÜ-Zugriff Zahlen, die Sie in der Vorgängerversion erstellt haben, installieren Sie jedoch verschoben und Skype für Business Server 2019 oder erstellten in Skype für Business Server 2019 vor, während oder nach der Migration, weisen folgende Merkmale auf:</span><span class="sxs-lookup"><span data-stu-id="358c9-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>
  
- <span data-ttu-id="358c9-108">In Office Communications Server 2007 R2-besprechungseinladungen und die Seite mit der DFÜ-Zugriff nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="358c9-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>
    
- <span data-ttu-id="358c9-109">Klicken Sie auf der Vorversion Install-besprechungseinladungen und auf die Seite mit der DFÜ-Zugriff angezeigt.</span><span class="sxs-lookup"><span data-stu-id="358c9-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>
    
- <span data-ttu-id="358c9-110">Für Business Server 2019-besprechungseinladungen und auf die Seite mit der DFÜ-Zugriff auf Skype angezeigt.</span><span class="sxs-lookup"><span data-stu-id="358c9-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>
    
- <span data-ttu-id="358c9-111">Nicht angezeigt oder im Verwaltungstool von Office Communications Server 2007 R2 geändert werden.</span><span class="sxs-lookup"><span data-stu-id="358c9-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>
    
- <span data-ttu-id="358c9-112">Können angezeigt und in der Vorversion Install-Systemsteuerung und in der Vorversion Install-Verwaltungsshell geändert werden.</span><span class="sxs-lookup"><span data-stu-id="358c9-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>
    
- <span data-ttu-id="358c9-113">Können angezeigt und in der Skype Business Server 2019-Systemsteuerung und Skype für Business Server 2019-Verwaltungsshell geändert werden.</span><span class="sxs-lookup"><span data-stu-id="358c9-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>
    
- <span data-ttu-id="358c9-114">Können innerhalb der Region neu sequenziert werden mithilfe des Cmdlets Set-CsDialinConferencingAccessNumber mit dem Parameter Priority.</span><span class="sxs-lookup"><span data-stu-id="358c9-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>
    
<span data-ttu-id="358c9-115">Sie müssen die Migration abgeschlossen Einwahl Zugriffsnummern, die auf der Vorgängerversion zeigen Pool installieren, bevor Sie den Vorversion Install-Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="358c9-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="358c9-116">Eingehende Anrufe an die Zugriffsnummern schlägt fehl, wenn Sie nicht über DFÜ-Zugriff der Migration wie im folgenden Verfahren beschrieben durchführen.</span><span class="sxs-lookup"><span data-stu-id="358c9-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="358c9-117">Sie müssen dieses Verfahren vor der Außerbetriebnahme der Vorversion Install Pools ausführen.</span><span class="sxs-lookup"><span data-stu-id="358c9-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="358c9-118">Es wird empfohlen, das Netzwerkauslastung möglichst gering ist, für den Fall, dass es eine kurzen Dienstausfall wird Einwahl Zugriffsnummern verschieben.</span><span class="sxs-lookup"><span data-stu-id="358c9-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 
  
## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="358c9-119">So identifizieren und Einwahl Zugriffsnummern verschieben</span><span class="sxs-lookup"><span data-stu-id="358c9-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="358c9-120">Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype für Business Server 2019**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="358c9-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="358c9-121">Um jede Zugriffsnummer für Einwahl-Zugriffsnummer in einen auf Skype für Business Server 2019 gehosteten Pool verschieben, über die Befehlszeile ausführen:</span><span class="sxs-lookup"><span data-stu-id="358c9-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 
    
  ```
  Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
  
  ```

3. <span data-ttu-id="358c9-122">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="358c9-122">Open Skype for Business Server Control Panel.</span></span>
    
4. <span data-ttu-id="358c9-123">Klicken Sie in der linken Navigationsleiste auf **Konferenz**.</span><span class="sxs-lookup"><span data-stu-id="358c9-123">In the left navigation bar, click **Conferencing**.</span></span>
    
5. <span data-ttu-id="358c9-124">Klicken Sie auf der Registerkarte **Zugriffsnummer für Einwahl** .</span><span class="sxs-lookup"><span data-stu-id="358c9-124">Click the **Dial-in Access Number** tab.</span></span> 
    
6. <span data-ttu-id="358c9-125">Stellen Sie sicher, dass keine Zugriffsnummer für Einwahl-Zugriffsnummern für den Pool der Vorgängerversion installieren zurückbleiben, aus dem Sie migrieren.</span><span class="sxs-lookup"><span data-stu-id="358c9-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="358c9-126">Wenn alle Einwahl Zugriffsnummern auf die Skype für Business Server 2019 Pool zeigen, können Sie dann den Vorversion installieren Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="358c9-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 
  
## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="358c9-127">Überprüfen der DFÜ-Zugriff der Migrations mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="358c9-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="358c9-128">Melden Sie sich von einem Benutzerkonto, dem die Rolle **"CsUserAdministrator** " oder **der csadministrator** zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="358c9-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="358c9-129">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="358c9-129">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="358c9-130">Klicken Sie in der linken Navigationsleiste auf **Konferenz**.</span><span class="sxs-lookup"><span data-stu-id="358c9-130">In the left navigation bar, click **Conferencing**.</span></span>
    
4. <span data-ttu-id="358c9-131">Klicken Sie auf der Registerkarte **Zugriffsnummer für Einwahl** .</span><span class="sxs-lookup"><span data-stu-id="358c9-131">Click the **Dial-in Access Number** tab.</span></span> 
    
5. <span data-ttu-id="358c9-132">Stellen Sie sicher, dass alle Einwahlnummern Zahlen in der auf Skype für Business Server 2019 gehosteten Pool migriert werden.</span><span class="sxs-lookup"><span data-stu-id="358c9-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>
    
## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="358c9-133">Überprüfen der DFÜ-Zugriff der Migrations mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="358c9-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="358c9-134">Öffnen Sie Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="358c9-134">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="358c9-135">Um alle zurücksenden migriert die Zugriffsnummern für einwahlkonferenzen über die Befehlszeile ausführen:</span><span class="sxs-lookup"><span data-stu-id="358c9-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
  ```
  Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
  ```

3. <span data-ttu-id="358c9-136">Stellen Sie sicher, dass alle Einwahlnummern Zahlen in der auf Skype für Business Server 2019 gehosteten Pool migriert werden.</span><span class="sxs-lookup"><span data-stu-id="358c9-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>
    

