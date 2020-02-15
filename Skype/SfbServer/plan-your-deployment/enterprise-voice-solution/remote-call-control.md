---
title: Planen der Remoteanrufsteuerung in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Die Remote Anrufsteuerung war ein Feature in früheren Versionen von lync Server, mit dem Benutzer Ihre PBX-Telefone mit lync Server steuern konnten. In Skype for Business Server wurde dieses Feature durch die Funktion "Anruf über Arbeit" ersetzt. In den Clientversionen für Skype for Business Server 2015 und weiterleiten ist die Remoteanrufsteuerung nicht mehr für die Konfiguration im Client verfügbar und wurde zur Verwendung entfernt.
ms.openlocfilehash: 788939c392b1d86d14590232c19979e664fa0c09
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982800"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="53573-105">Planen der Remoteanrufsteuerung in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="53573-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="53573-106">Die Remote Anrufsteuerung war ein Feature in früheren Versionen von lync Server, mit dem Benutzer Ihre PBX-Telefone mit lync Server steuern konnten.</span><span class="sxs-lookup"><span data-stu-id="53573-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="53573-107">In Skype for Business Server wurde dieses Feature durch die Funktion "Anruf über Arbeit" ersetzt.</span><span class="sxs-lookup"><span data-stu-id="53573-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="53573-108">*In den Clientversionen für Skype for Business Server 2015 und weiterleiten ist die Remoteanrufsteuerung nicht mehr für die Konfiguration im Client verfügbar und wurde zur Verwendung entfernt.*</span><span class="sxs-lookup"><span data-stu-id="53573-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="53573-109">Remoteanrufsteuerung Benutzer in Ihrer Organisation, die auf Front-End-Servern mit lync Server verwaltet werden, können die Remoteanrufsteuerung auch dann weiterhin verwenden, wenn Sie einen Skype for Business-Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="53573-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="53573-110">Für Benutzer, die in Skype for Business Server verwaltet werden, wird die Remoteanrufsteuerung jedoch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="53573-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="53573-111">In der folgenden Tabelle finden Sie eine Kombination aus Server-und Client Kombinationen sowie Informationen dazu, ob Sie die Remoteanrufsteuerung oder den Anruf über Arbeit unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="53573-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="53573-112">**Skype for Business Client mit aktivierter Skype-Benutzeroberfläche**</span><span class="sxs-lookup"><span data-stu-id="53573-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="53573-113">**Skype for Business Client mit aktivierter lync-Benutzeroberfläche**</span><span class="sxs-lookup"><span data-stu-id="53573-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="53573-114">**Skype for Business 2016-Client**</span><span class="sxs-lookup"><span data-stu-id="53573-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="53573-115">**Lync 2013-Client**</span><span class="sxs-lookup"><span data-stu-id="53573-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="53573-116">**Lync 2010-Client**</span><span class="sxs-lookup"><span data-stu-id="53573-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="53573-117">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="53573-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="53573-118">Anruf über den Arbeitsplatz</span><span class="sxs-lookup"><span data-stu-id="53573-118">Call via Work</span></span>  <br/> |<span data-ttu-id="53573-119">1 </span><span class="sxs-lookup"><span data-stu-id="53573-119">1</span></span> <br/> |<span data-ttu-id="53573-120">Anruf über den Arbeitsplatz</span><span class="sxs-lookup"><span data-stu-id="53573-120">Call via Work</span></span>  <br/> |<span data-ttu-id="53573-121">1 </span><span class="sxs-lookup"><span data-stu-id="53573-121">1</span></span> <br/> |<span data-ttu-id="53573-122">1 </span><span class="sxs-lookup"><span data-stu-id="53573-122">1</span></span> <br/> |
| <span data-ttu-id="53573-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53573-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="53573-124">Remote Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="53573-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="53573-125">Remote Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="53573-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="53573-126">1 </span><span class="sxs-lookup"><span data-stu-id="53573-126">1</span></span> <br/> |<span data-ttu-id="53573-127">Remote Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="53573-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="53573-128">Remote Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="53573-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="53573-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="53573-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="53573-130">Remote Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="53573-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="53573-131">Remote Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="53573-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="53573-132">1 </span><span class="sxs-lookup"><span data-stu-id="53573-132">1</span></span> <br/> |<span data-ttu-id="53573-133">Remote Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="53573-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="53573-134">Remote Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="53573-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="53573-135">Keine Funktion wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="53573-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="53573-136">Weitere Informationen finden Sie unter [Remote Anrufsteuerung](https://go.microsoft.com/fwlink/p/?LinkId=530208) in der lync Server 2013 Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="53573-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="53573-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53573-137">See also</span></span>

[<span data-ttu-id="53573-138">Planen der Anruf über Arbeit in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="53573-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="53573-139">Vergleich der Desktop Clientfeatures für Skype for Business</span><span class="sxs-lookup"><span data-stu-id="53573-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="53573-140">Einen Skype for Business Anruf tätigen, aber Ihr PBX-Telefon für Audio verwenden</span><span class="sxs-lookup"><span data-stu-id="53573-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

