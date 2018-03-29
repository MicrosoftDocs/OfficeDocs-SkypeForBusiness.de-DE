---
title: Planen der Remoteanrufsteuerung in Skype for Business 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Remoteanrufsteuerung wurde Feature in früheren Versionen von Lync Server die Benutzer ihre Nebenstellentelefone über mit Lync Server steuern aktiviert. Dieses Feature wurde in Skype für Business Server mit über Arbeitsplatz anrufen ersetzt. In die Clientversionen für Skype für Business Server 2015 und Wechsel zu weiterleiten, remote Call Control ist nicht mehr verfügbar in den Client konfiguriert und wurde für die Verwendung entfernt.
ms.openlocfilehash: 2db859ad33a697d5bca632ca9b6677a3a67bd103
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-remote-call-control-in-skype-for-business-2015"></a><span data-ttu-id="3c53c-105">Planen der Remoteanrufsteuerung in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="3c53c-105">Plan for remote call control in Skype for Business 2015</span></span>
 
<span data-ttu-id="3c53c-106">Remoteanrufsteuerung wurde Feature in früheren Versionen von Lync Server die Benutzer ihre Nebenstellentelefone über mit Lync Server steuern aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3c53c-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="3c53c-107">Dieses Feature wurde in Skype für Business Server mit über Arbeitsplatz anrufen ersetzt.</span><span class="sxs-lookup"><span data-stu-id="3c53c-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="3c53c-108">*In die Clientversionen für Skype für Business Server 2015 und Wechsel zu weiterleiten, remote Call Control ist nicht mehr verfügbar in den Client konfiguriert und wurde für die Verwendung entfernt.*</span><span class="sxs-lookup"><span data-stu-id="3c53c-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="3c53c-109">Remoteanrufsteuerung Steuerelementbenutzer in Ihrer Organisation, die auf Front-End-Servern mit Lync Server verwaltet werden können auch weiterhin mithilfe Remoteanrufsteuerung, auch wenn sie einen Skype für die Business-Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c53c-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="3c53c-110">Für alle Benutzer in Skype für Business Server verwaltet werden, wird die Remoteanrufsteuerung jedoch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3c53c-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="3c53c-111">In der folgenden Tabelle können Sie sich über Server/Client-Kombinationen und darüber informieren, ob diese Remoteanrufsteuerung oder „Anruf über den Arbeitsplatz“ unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="3c53c-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="3c53c-112">**Skype für Business 2015 Client With Skype-Benutzeroberfläche aktiviert**</span><span class="sxs-lookup"><span data-stu-id="3c53c-112">**Skype for Business 2015 Client With Skype UI enabled**</span></span>|<span data-ttu-id="3c53c-113">**Skype für Business 2015 Client With Lync-Benutzeroberfläche aktiviert**</span><span class="sxs-lookup"><span data-stu-id="3c53c-113">**Skype for Business 2015 Client With Lync UI enabled**</span></span>|<span data-ttu-id="3c53c-114">**Skype für Business 2016-Client**</span><span class="sxs-lookup"><span data-stu-id="3c53c-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="3c53c-115">**Lync 2013-Clients**</span><span class="sxs-lookup"><span data-stu-id="3c53c-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="3c53c-116">**Lync 2010-Client**</span><span class="sxs-lookup"><span data-stu-id="3c53c-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="3c53c-117">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3c53c-117">Skype for Business Server 2015</span></span> <br/> |<span data-ttu-id="3c53c-118">Anruf über den Arbeitsplatz</span><span class="sxs-lookup"><span data-stu-id="3c53c-118">Call via Work</span></span>  <br/> |<span data-ttu-id="3c53c-119">1</span><span class="sxs-lookup"><span data-stu-id="3c53c-119">1</span></span> <br/> |<span data-ttu-id="3c53c-120">Anruf über den Arbeitsplatz</span><span class="sxs-lookup"><span data-stu-id="3c53c-120">Call via Work</span></span>  <br/> |<span data-ttu-id="3c53c-121">1</span><span class="sxs-lookup"><span data-stu-id="3c53c-121">1</span></span> <br/> |<span data-ttu-id="3c53c-122">1</span><span class="sxs-lookup"><span data-stu-id="3c53c-122">1</span></span> <br/> |
| <span data-ttu-id="3c53c-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c53c-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="3c53c-124">Remoteanrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="3c53c-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3c53c-125">Remoteanrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="3c53c-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3c53c-126">1</span><span class="sxs-lookup"><span data-stu-id="3c53c-126">1</span></span> <br/> |<span data-ttu-id="3c53c-127">Remoteanrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="3c53c-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3c53c-128">Remoteanrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="3c53c-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="3c53c-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3c53c-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="3c53c-130">Remoteanrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="3c53c-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3c53c-131">Remoteanrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="3c53c-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3c53c-132">1</span><span class="sxs-lookup"><span data-stu-id="3c53c-132">1</span></span> <br/> |<span data-ttu-id="3c53c-133">Remoteanrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="3c53c-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3c53c-134">Remoteanrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="3c53c-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="3c53c-135">Weder Feature wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3c53c-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="3c53c-136">Weitere Informationen finden Sie unter [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in der Dokumentation zu Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c53c-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3c53c-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c53c-137">See also</span></span>

#### 

[<span data-ttu-id="3c53c-138">Planen der Anruf über den Arbeitsplatz in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3c53c-138">Plan for Call Via Work in Skype for Business Server 2015</span></span>](call-via-work.md)
  
[<span data-ttu-id="3c53c-139">Desktopclient Featurevergleich für Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="3c53c-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)
#### 

[<span data-ttu-id="3c53c-140">Stellen Sie einen Skype für Business Anruf jedoch verwenden Telefonapparat PBX für audio</span><span class="sxs-lookup"><span data-stu-id="3c53c-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

