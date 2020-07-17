---
title: Migrieren von Zugriffsnummern für die Einwahl
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
description: Zum Migrieren der Kontaktobjekte müssen Sie das Cmdlet "CsApplicationEndpoint" ausführen, um die Zugriffsnummern für die Einwahl in Skype for Business Server 2019 zu migrieren. Während des Zeitraums für die Legacy Installation und Skype for Business Server 2019-Koexistenz Verhalten sich Einwahlnummern, die Sie in Skype for Business Server 2019 erstellt haben, ähnlich wie die in diesem Abschnitt beschriebenen Zugriffsnummern für Einwahlen, die Sie in der Legacy Installation erstellt haben.
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752697"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="ee6c8-104">Migrieren von Zugriffsnummern für die Einwahl</span><span class="sxs-lookup"><span data-stu-id="ee6c8-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="ee6c8-105">Zum Migrieren der Kontaktobjekte müssen Sie das Cmdlet " **CsApplicationEndpoint** " ausführen, um die Zugriffsnummern für die Einwahl in Skype for Business Server 2019 zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="ee6c8-106">Während des Zeitraums für die Legacy Installation und Skype for Business Server 2019-Koexistenz Verhalten sich Einwahlnummern, die Sie in Skype for Business Server 2019 erstellt haben, ähnlich wie die in diesem Abschnitt beschriebenen Zugriffsnummern für Einwahlen, die Sie in der Legacy Installation erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="ee6c8-107">Einwahlnummern, die Sie in der Legacy Installation erstellt, aber auf Skype for Business Server 2019 verschoben haben oder die Sie in Skype for Business Server 2019 vor, während oder nach der Migration erstellt haben, weisen die folgenden Merkmale auf:</span><span class="sxs-lookup"><span data-stu-id="ee6c8-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="ee6c8-108">Sie werden nicht in Office Communications Server 2007 R2-Besprechungseinladungen und auf der Einwahlnummernseite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="ee6c8-109">In den Legacy-Installations-Besprechungseinladungen und auf der Seite für die Einwahl Zugriffsnummer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="ee6c8-110">Auf Skype for Business Server 2019-Besprechungseinladungen und auf der Seite für die Einwahl Zugriffsnummer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="ee6c8-111">Sie können nicht im Verwaltungstool von Office Communications Server 2007 R2 angezeigt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="ee6c8-112">Kann in der Systemsteuerung der Legacy Installation und in der Legacy install Management Shell angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="ee6c8-113">Kann in der Skype for Business Server 2019-Systemsteuerung und in Skype for Business Server 2019-Verwaltungsshell angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="ee6c8-114">Sie können innerhalb des Bereichs durch Verwendung des Set-CsDialinConferencingAccessNumber-Cmdlets mit dem Priority-Parameter neu sequenziert werden.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="ee6c8-115">Sie müssen die Migration von Einwahlnummern, die auf den Legacy-Installations Pool deuten, abschließen, bevor Sie den Legacy-Installations Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="ee6c8-116">Wenn Sie die Migration von Einwahlnummern nicht wie im folgenden Verfahren beschrieben abschließen, schlagen eingehende Anrufe an die Einwahlnummern fehl.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee6c8-117">Sie müssen dieses Verfahren ausführen, bevor Sie den Legacy Installations Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="ee6c8-118">Wir empfehlen, das Verschieben von Einwahlen zu einem Zeitpunkt vorzunehmen, zu dem die Netzwerkauslastung möglichst gering ist, für den Fall, dass es zu einem kurzen Dienstausfall kommt.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="ee6c8-119">So identifizieren und verschieben Sie Einwahlnummern</span><span class="sxs-lookup"><span data-stu-id="ee6c8-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="ee6c8-120">Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="ee6c8-121">Um jede Zugriffsnummer für die Einwahl in einen Pool zu migrieren, der auf Skype for Business Server 2019 gehostet wird, führen Sie über die Befehlszeile Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="ee6c8-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="ee6c8-122">Öffnen Sie Skype for Business Server Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="ee6c8-123">Klicken Sie in der linken Navigationsleiste auf **Konferenz**.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="ee6c8-124">Klicken Sie auf die Registerkarte **Einwahlnummer**.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="ee6c8-125">Stellen Sie sicher, dass keine Einwahlnummern für den Legacy-Installations Pool verbleiben, von dem Sie migrieren.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ee6c8-126">Wenn alle Zugriffsnummern für Einwahlen auf den Skype for Business Server 2019-Pool deuten, können Sie den Legacy-Installations Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ee6c8-127">Überprüfen der Migration von Zugriffsnummern für die Einwahl mit Skype for Business Server Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="ee6c8-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ee6c8-128">Melden Sie sich mit einem Benutzerkonto, dem die Rolle **CsUserAdministrator** oder **CsAdministrator** zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="ee6c8-129">Öffnen Sie Skype for Business Server Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="ee6c8-130">Klicken Sie in der linken Navigationsleiste auf **Konferenz**.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="ee6c8-131">Klicken Sie auf die Registerkarte **Einwahlnummer**.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="ee6c8-132">Stellen Sie sicher, dass alle Einwahlnummern zu dem auf Skype for Business Server 2019 gehosteten Pool migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ee6c8-133">Überprüfen der Migration der Zugriffsnummern für die Einwahl mit Skype for Business Server Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="ee6c8-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ee6c8-134">Öffnen Sie Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="ee6c8-135">Um alle migrierten Einwahlnummern für Konferenzen zurückzugeben, führen Sie an der Befehlszeile folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="ee6c8-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="ee6c8-136">Stellen Sie sicher, dass alle Einwahlnummern zu dem auf Skype for Business Server 2019 gehosteten Pool migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="ee6c8-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


