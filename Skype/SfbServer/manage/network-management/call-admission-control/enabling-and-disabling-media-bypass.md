---
title: Aktivieren und Deaktivieren der medienumgehung
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Verwenden Sie die Verfahren in diesem Artikel zum Aktivieren oder deaktivieren die medienumgehung mithilfe der Skype für Business Server-Systemsteuerung.
ms.openlocfilehash: eebbc111f0d205be8dced9ec8ddb5150deff8119
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226242"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="398fd-103">Aktivieren und Deaktivieren der Medienumgehung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="398fd-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="398fd-104">Verwenden Sie die Verfahren in diesem Artikel zum Aktivieren oder deaktivieren die medienumgehung mithilfe der Skype für Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="398fd-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="398fd-105">Aktivieren der netzwerkmedienumgehung</span><span class="sxs-lookup"><span data-stu-id="398fd-105">Enable network media bypass</span></span> 

<span data-ttu-id="398fd-106">Einstellungen für die medienumgehung gelten global für einen Skype für Business Server-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="398fd-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="398fd-107">Die medienumgehung lässt Aufrufe Umgehung des Vermittlungsservers.</span><span class="sxs-lookup"><span data-stu-id="398fd-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="398fd-108">Ausführliche Informationen zur Verwendung von Medien zu umgehen, finden Sie unter [Plan für Medien zu umgehen](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="398fd-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="398fd-109">Sie können aktivieren und Konfigurieren der medienumgehung aus der Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="398fd-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="398fd-110">Zum Aktivieren und Konfigurieren der medienumgehung</span><span class="sxs-lookup"><span data-stu-id="398fd-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="398fd-111">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="398fd-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="398fd-112">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="398fd-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="398fd-113">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Global**.</span><span class="sxs-lookup"><span data-stu-id="398fd-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="398fd-114">Klicken Sie auf der Seite **Global** auf die Konfiguration **Global** .</span><span class="sxs-lookup"><span data-stu-id="398fd-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="398fd-115">Es ist immer nur eine Konfiguration, und es heißt immer Global.</span><span class="sxs-lookup"><span data-stu-id="398fd-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="398fd-116">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="398fd-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="398fd-117">Klicken Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **medienumgehung aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="398fd-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="398fd-118">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="398fd-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="398fd-119">**Immer umgehen**   wählen Sie diese Option, um Medien versuchen für alle Anrufe zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="398fd-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="398fd-120">Diese Option wird nicht verfügbar, wenn die anrufsteuerung (CAC) aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="398fd-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="398fd-121">Wenn CAC nicht aktiviert ist, wählen Sie diese Option in den folgenden Situationen:</span><span class="sxs-lookup"><span data-stu-id="398fd-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="398fd-122">Besteht keine Notwendigkeit zur bandbreitensteuerung.</span><span class="sxs-lookup"><span data-stu-id="398fd-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="398fd-123">Es besteht keine Notwendigkeit abgestimmte Konfiguration, um zu bestimmen, wann Umgehung geschehen soll.</span><span class="sxs-lookup"><span data-stu-id="398fd-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="398fd-124">Es ist vollständige Konnektivität zwischen Gateways und Clients.</span><span class="sxs-lookup"><span data-stu-id="398fd-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="398fd-125">**Verwenden Sie Standorte und Regionen**   wenn CAC aktiviert ist, diese Option ist standardmäßig aktiviert und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="398fd-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="398fd-126">Wenn diese Option ausgewählt ist, werden netzwerkkonfigurationsstandorte und Regionen verwendet werden, um zu bestimmen, wann die medienumgehung möglich ist.</span><span class="sxs-lookup"><span data-stu-id="398fd-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="398fd-127">Wenn Sie diese Option auswählen, können Sie auswählen, um Umgehung für Websites zu aktivieren, die nicht zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="398fd-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="398fd-128">Klicken Sie auf das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte aktivieren** nur, wenn Sie verfügen über eine oder mehrere große Standorte derselben Region zugeordnet, die keine bandbreiteneinschränkungen (beispielsweise einem großen zentralen Standort) und Ihnen auch einige Zweigniederlassungen zugeordnet die derselben Region, die bandbreiteneinschränkungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="398fd-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="398fd-129">Wenn Sie aktivieren für nicht zugeordnete Standorte umgehen, Konfiguration wird optimiert, da Sie nur die die Zweigniederlassungen zugeordnete Subnetze angeben, statt dass alle Subnetze angeben müssen alle Websites zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="398fd-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="398fd-130">Es wird empfohlen, dass Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte aktivieren** nicht auswählen, wenn die Anrufsteuerung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="398fd-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="398fd-131">Klicken Sie auf **Commit** , um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="398fd-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="398fd-132">Deaktivieren der netzwerkmedienumgehung</span><span class="sxs-lookup"><span data-stu-id="398fd-132">Disable network media bypass</span></span>

<span data-ttu-id="398fd-133">Einstellungen für die medienumgehung gelten global für einen Skype für Business Server-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="398fd-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="398fd-134">Die medienumgehung lässt Aufrufe Umgehung des Vermittlungsservers.</span><span class="sxs-lookup"><span data-stu-id="398fd-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="398fd-135">Ausführliche Informationen zur Verwendung von Medien zu umgehen, finden Sie unter [Plan für Medien zu umgehen](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="398fd-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="398fd-136">Sie können die medienumgehung über die Skype Business Server-Systemsteuerung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="398fd-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="398fd-137">So deaktivieren Sie die medienumgehung</span><span class="sxs-lookup"><span data-stu-id="398fd-137">To disable media bypass</span></span>

1.  <span data-ttu-id="398fd-138">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="398fd-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="398fd-139">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="398fd-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="398fd-140">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Global**.</span><span class="sxs-lookup"><span data-stu-id="398fd-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="398fd-141">Klicken Sie auf der Seite **Global** auf die Konfiguration **Global** .</span><span class="sxs-lookup"><span data-stu-id="398fd-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="398fd-142">Es ist immer nur eine Konfiguration, und es heißt immer Global.</span><span class="sxs-lookup"><span data-stu-id="398fd-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="398fd-143">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="398fd-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="398fd-144">Deaktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **medienumgehung aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="398fd-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="398fd-145">Klicken Sie auf **Commit** , um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="398fd-145">Click **Commit** to save your changes.</span></span>

  
