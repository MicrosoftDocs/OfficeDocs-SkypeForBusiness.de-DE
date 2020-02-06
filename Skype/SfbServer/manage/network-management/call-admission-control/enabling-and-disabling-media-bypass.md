---
title: Aktivieren und Deaktivieren der medienumgehung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Führen Sie die in diesem Artikel beschriebenen Verfahren aus, um die medienumgehung mithilfe des Skype for Business Server-Control Panels zu aktivieren oder zu deaktivieren.
ms.openlocfilehash: d1c0a5eb409c6bb5c07c530b4799ab8a53a9fddb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817544"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="58ce7-103">Aktivieren und Deaktivieren der Medienumgehung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="58ce7-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="58ce7-104">Führen Sie die in diesem Artikel beschriebenen Verfahren aus, um die medienumgehung mithilfe des Skype for Business Server-Control Panels zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="58ce7-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="58ce7-105">Aktivieren der Netzwerkmedien Umgehung</span><span class="sxs-lookup"><span data-stu-id="58ce7-105">Enable network media bypass</span></span> 

<span data-ttu-id="58ce7-106">Medienumgehungseinstellungen gelten global für eine Skype for Business Server-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="58ce7-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="58ce7-107">Die medienumgehung ermöglicht Anrufe, den Vermittlungs Server zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="58ce7-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="58ce7-108">Ausführliche Informationen zur Verwendung der medienumgehung finden Sie unter [Planen der medienumgehung](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="58ce7-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="58ce7-109">Sie können die medienumgehung über das Skype Control Panel für Unternehmens-Server aktivieren und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="58ce7-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="58ce7-110">So aktivieren und konfigurieren Sie die medienumgehung</span><span class="sxs-lookup"><span data-stu-id="58ce7-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="58ce7-111">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="58ce7-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="58ce7-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="58ce7-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="58ce7-113">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Global**.</span><span class="sxs-lookup"><span data-stu-id="58ce7-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="58ce7-114">Klicken Sie auf der Seite **Global** auf die **globale** Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="58ce7-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="58ce7-115">Es gibt immer nur eine Konfiguration, und Sie wird immer als "Global" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="58ce7-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="58ce7-116">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="58ce7-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="58ce7-117">Klicken Sie auf der Seite **globale Einstellungen bearbeiten** auf das Kontrollkästchen **medienumgehung aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="58ce7-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="58ce7-118">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="58ce7-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="58ce7-119">**Immer umgehen**   wählen Sie diese Option aus, um bei allen Anrufen medienumgehung zu versuchen.</span><span class="sxs-lookup"><span data-stu-id="58ce7-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="58ce7-120">Diese Option steht nicht zur Verfügung, wenn die Anrufsteuerung (Call Admission Control, CAC) aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="58ce7-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="58ce7-121">Wenn CAC nicht aktiviert ist, wählen Sie diese Option in den folgenden Fällen aus:</span><span class="sxs-lookup"><span data-stu-id="58ce7-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="58ce7-122">Die Bandbreitensteuerung ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58ce7-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="58ce7-123">Es besteht keine Notwendigkeit für eine fein abgestimmte Konfiguration, um festzustellen, wann eine Umgehung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="58ce7-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="58ce7-124">Es besteht eine vollständige Konnektivität zwischen Gateways und Clients.</span><span class="sxs-lookup"><span data-stu-id="58ce7-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="58ce7-125">**Verwenden von Websites und der Regions Konfiguration**   wenn CAC aktiviert ist, ist diese Option standardmäßig aktiviert und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="58ce7-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="58ce7-126">Wenn diese Option ausgewählt ist, werden Netzwerk Konfigurations Websites und-Regionen verwendet, um zu ermitteln, wann eine medienumgehung möglich ist.</span><span class="sxs-lookup"><span data-stu-id="58ce7-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="58ce7-127">Wenn Sie diese Option auswählen, können Sie die Umgehung für Websites aktivieren, die nicht zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="58ce7-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="58ce7-128">Aktivieren Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Websites aktivieren** nur, wenn Sie über eine oder mehrere große Websites verfügen, die dem gleichen Bereich zugeordnet sind, die keine Bandbreiteneinschränkungen aufweisen (beispielsweise eine große zentrale Website), und Sie verfügen auch über einige Verzweigungs Websites, die dem gleichen Bereich zugeordnet sind, für den es keine Bandbreiteneinschränkungen gibt.</span><span class="sxs-lookup"><span data-stu-id="58ce7-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="58ce7-129">Wenn Sie die Umgehung für nicht zugeordnete Websites aktivieren, wird die Konfiguration optimiert, da Sie nur die Subnetze angeben, die den Zweigstellen zugeordnet sind, anstatt alle Subnetze anzugeben, die allen Websites zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="58ce7-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="58ce7-130">Wir empfehlen, dass Sie das Kontrollkästchen **Bypass für nicht zugeordnete Websites aktivieren** nicht aktivieren, wenn CAC aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="58ce7-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="58ce7-131">Klicken Sie auf **Commit** , um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="58ce7-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="58ce7-132">Deaktivieren der Netzwerkmedien Umgehung</span><span class="sxs-lookup"><span data-stu-id="58ce7-132">Disable network media bypass</span></span>

<span data-ttu-id="58ce7-133">Medienumgehungseinstellungen gelten global für eine Skype for Business Server-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="58ce7-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="58ce7-134">Die medienumgehung ermöglicht Anrufe, den Vermittlungs Server zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="58ce7-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="58ce7-135">Ausführliche Informationen zur Verwendung der medienumgehung finden Sie unter [Planen der medienumgehung](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="58ce7-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="58ce7-136">Sie können die medienumgehung über das Skype Control Panel für Unternehmen-Server deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="58ce7-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="58ce7-137">So deaktivieren Sie die medienumgehung</span><span class="sxs-lookup"><span data-stu-id="58ce7-137">To disable media bypass</span></span>

1.  <span data-ttu-id="58ce7-138">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="58ce7-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="58ce7-139">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="58ce7-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="58ce7-140">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Global**.</span><span class="sxs-lookup"><span data-stu-id="58ce7-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="58ce7-141">Klicken Sie auf der Seite **Global** auf die **globale** Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="58ce7-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="58ce7-142">Es gibt immer nur eine Konfiguration, und Sie wird immer als "Global" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="58ce7-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="58ce7-143">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="58ce7-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="58ce7-144">Deaktivieren Sie auf der Seite **globale Einstellungen bearbeiten** das Kontrollkästchen **medienumgehung aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="58ce7-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="58ce7-145">Klicken Sie auf **Commit** , um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="58ce7-145">Click **Commit** to save your changes.</span></span>

  
