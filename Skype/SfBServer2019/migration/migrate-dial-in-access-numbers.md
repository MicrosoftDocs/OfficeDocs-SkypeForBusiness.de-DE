---
title: Migrieren von Zugriffsnummern für die Einwahl
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Zum Migrieren der Kontaktobjekte muss das Cmdlet Move-CsApplicationEndpoint ausgeführt werden, um Einwahlnummern in Skype for Business Server 2019 zu migrieren. Während des Koexistenz Zeitraums für Legacy Installationen und Skype for Business Server 2019 Verhalten sich Einwahlnummern, die Sie in Skype for Business Server 2019 erstellt haben, ähnlich wie die Einwahl Zugriffsnummern, die Sie in der Legacy Installation erstellt haben, wie in diesem Beispiel beschrieben. Abschnitt.
ms.openlocfilehash: 83cf8b75bcf9a8d4794ae0f95962f3627d8592c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280812"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="dcb2b-104">Migrieren von Zugriffsnummern für die Einwahl</span><span class="sxs-lookup"><span data-stu-id="dcb2b-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="dcb2b-105">Zum Migrieren der Kontaktobjekte muss das Cmdlet **Move-CsApplicationEndpoint** ausgeführt werden, um Einwahlnummern in Skype for Business Server 2019 zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="dcb2b-106">Während des Koexistenz Zeitraums für Legacy Installationen und Skype for Business Server 2019 Verhalten sich Einwahlnummern, die Sie in Skype for Business Server 2019 erstellt haben, ähnlich wie die Einwahl Zugriffsnummern, die Sie in der Legacy Installation erstellt haben, wie in diesem Beispiel beschrieben. Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="dcb2b-107">Einwahl Zugriffsnummern, die Sie in der Legacy Installation erstellt, aber in Skype for Business Server 2019 verschoben haben oder die Sie in Skype for Business Server 2019 vor, während oder nach der Migration erstellt haben, weisen die folgenden Merkmale auf:</span><span class="sxs-lookup"><span data-stu-id="dcb2b-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="dcb2b-108">Sie werden nicht auf Office Communications Server 2007 R2-Besprechungseinladungen und auf der Seite Einwahl Zugriffsnummer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="dcb2b-109">In den Legacy-Installations Einladungen für Besprechungen und auf der Seite Einwahl Zugriffsnummer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="dcb2b-110">In den Skype for Business Server 2019-Besprechungseinladungen und auf der Seite "Einwahl Zugriffsnummer" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="dcb2b-111">Kann im Office Communications Server 2007 R2-Verwaltungstool nicht angezeigt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="dcb2b-112">Kann in der Systemsteuerung für Legacy Installationen und in der Legacy-Installations Verwaltungsshell angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="dcb2b-113">Kann in der Skype for Business Server 2019-Systemsteuerung und in der Skype for Business Server 2019-Verwaltungsshell angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="dcb2b-114">Kann innerhalb des Bereichs mithilfe des Cmdlets "CsDialinConferencingAccessNumber" mit dem Priority-Parameter neu sequenziert werden.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="dcb2b-115">Sie müssen die Migration von Einwahl Zugriffsnummern beenden, die auf den Legacy Installations Pool verweisen, bevor Sie den Legacy Installations Pool außer Betrieb setzen.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="dcb2b-116">Wenn Sie die Migration von Einwahlnummern wie im folgenden Verfahren beschrieben nicht abschließen, treten bei eingehenden Anrufen an die Zugriffsnummern keine Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dcb2b-117">Sie müssen dieses Verfahren vor der Außerbetriebnahme des Legacy Installations Pools ausführen.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="dcb2b-118">Es wird empfohlen, Einwahlnummern zu verschieben, wenn die Netzwerkauslastung gering ist, falls es einen kurzen Zeitraum für einen Ausfall des Diensts gibt.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="dcb2b-119">So identifizieren und verschieben Sie Einwahl Zugriffsnummern</span><span class="sxs-lookup"><span data-stu-id="dcb2b-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="dcb2b-120">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="dcb2b-121">Um jede Einwahl-Zugriffsnummer in einen Pool zu verschieben, der in Skype for Business Server 2019 gehostet wird, führen Sie in der Befehlszeile Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="dcb2b-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="dcb2b-122">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="dcb2b-123">Klicken Sie in der linken Navigationsleiste auf **Konferenz**.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="dcb2b-124">Klicken Sie auf die Registerkarte **Einwahlnummer** .</span><span class="sxs-lookup"><span data-stu-id="dcb2b-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="dcb2b-125">Stellen Sie sicher, dass keine Einwahl Zugriffsnummern für den Legacy Installations Pool verbleiben, von dem aus Sie migrieren.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dcb2b-126">Wenn alle Einwahl Zugriffsnummern auf den Skype for Business Server 2019-Pool verweisen, können Sie den Legacy-Installations Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="dcb2b-127">Überprüfen der Migration von Einwahl Zugriffsnummern mit der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="dcb2b-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="dcb2b-128">Melden Sie sich bei einem Benutzerkonto, das der **CsUserAdministrator** -Rolle oder der **CsAdministrator** -Rolle zugewiesen ist, bei jedem Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="dcb2b-129">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="dcb2b-130">Klicken Sie in der linken Navigationsleiste auf **Konferenz**.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="dcb2b-131">Klicken Sie auf die Registerkarte **Einwahlnummer** .</span><span class="sxs-lookup"><span data-stu-id="dcb2b-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="dcb2b-132">Überprüfen Sie, ob alle Einwahl Zugriffsnummern in den Pool migriert werden, der in Skype for Business Server 2019 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="dcb2b-133">Überprüfen der Migration von Einwahl Zugriffsnummern mit der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="dcb2b-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="dcb2b-134">Öffnen Sie die Skype for Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="dcb2b-135">Um alle migrierten Zugriffsnummern für Einwahlkonferenzen zurückzugeben, führen Sie über die Befehlszeile Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="dcb2b-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="dcb2b-136">Überprüfen Sie, ob alle Einwahl Zugriffsnummern in den Pool migriert werden, der in Skype for Business Server 2019 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="dcb2b-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


