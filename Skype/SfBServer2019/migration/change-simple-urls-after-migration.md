---
title: Ändern einfacher URLs nach der Migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype für Business Server unterstützt einfache URLs.
ms.openlocfilehash: 02f4cc729a50459a8125e216265b935d557007c6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892709"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="bc6c9-103">Ändern einfacher URLs nach der Migration</span><span class="sxs-lookup"><span data-stu-id="bc6c9-103">Change simple URLs after migration</span></span>

<span data-ttu-id="bc6c9-104">Skype für Business Server unterstützt drei einfache URLs:</span><span class="sxs-lookup"><span data-stu-id="bc6c9-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="bc6c9-105">**Erfüllen** wird als Basis-URL für alle Konferenzen in der Website oder Ihrer Organisation verwendet.</span><span class="sxs-lookup"><span data-stu-id="bc6c9-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="bc6c9-106">Mit den einfachen URLs sind Links zu Besprechungen teilnehmen, die einfach zu verstehen und leicht zu kommunizieren und zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="bc6c9-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="bc6c9-107">**Zugriffsnummer für Einwahl** ermöglicht den Zugriff auf die Webseite mit Einwahl Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="bc6c9-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="bc6c9-108">Die Zugriffsnummer für Einwahl einfache URL ist in allen besprechungseinladungen enthalten, damit Benutzer, die in die Besprechung einwählen möchten die erforderlichen Telefonnummer und PIN-Informationen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="bc6c9-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="bc6c9-109">**Admin** ermöglicht schnellen Zugriff auf die Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="bc6c9-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="bc6c9-110">Die einfache Admin-URL dient der internen Verwendung in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="bc6c9-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="bc6c9-111">Nach der Migration zu Skype für Business Server, müssen Ihnen bekannt sein wie die Änderung Ihrer DNS-Einträgen und Zertifikaten für einfache URLs auswirkt.</span><span class="sxs-lookup"><span data-stu-id="bc6c9-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="bc6c9-112">Wenn derzeit in der Topologie der Vorgängerversion Skype für Business Server Director bleibt, sind keine Änderungen an der einfachen URLs erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bc6c9-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="bc6c9-113">Wenn die Skype für Business Server Director nach der Migration aus der Topologie entfernt wird, müssen die einfache URL-DNS-Einträge aktualisiert werden, um eines der Skype für Business Server-Pools zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="bc6c9-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="bc6c9-114">Wenn Sie einen einfachen URL-Name ändern, müssen Sie Enable-CsComputer auf jedem Director und Front-End-Server, um die Änderung zu registrieren ausführen.</span><span class="sxs-lookup"><span data-stu-id="bc6c9-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="bc6c9-115">So aktualisieren Sie die einfache Meet-URL</span><span class="sxs-lookup"><span data-stu-id="bc6c9-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="bc6c9-116">Klicken Sie im Topologie-Generator mit der rechten Maustaste im obersten Knotens **Skype für Business Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bc6c9-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="bc6c9-117">Wählen Sie die **Einfache URLs** im linken Bereich, klicken Sie dann unter **Besprechung URLs:** wählen Sie die URL erfüllen, und klicken Sie dann auf **URL bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bc6c9-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="bc6c9-118">Aktualisieren Sie die URL auf den gewünschten Wert ein, und klicken Sie dann auf **OK** , um die bearbeitete URL zu speichern.</span><span class="sxs-lookup"><span data-stu-id="bc6c9-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="bc6c9-119">So aktualisieren Sie die einfache Admin-URL</span><span class="sxs-lookup"><span data-stu-id="bc6c9-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="bc6c9-120">Klicken Sie im Topologie-Generator mit der rechten Maustaste im obersten Knotens **Skype für Business Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bc6c9-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="bc6c9-121">Wählen Sie im linken Bereich, klicken Sie dann unten im Feld **URL für administrativen Zugriff** **Einfache URLs** aus, geben Sie die einfache URL für administrativen Zugriff auf die Skype Business Server-Systemsteuerung aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc6c9-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="bc6c9-122">Es wird empfohlen, die einfachstmögliche URL als Verwaltungs-URL zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bc6c9-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="bc6c9-123">Die einfachste Option ist https://admin. <em> \<Domäne\></em>.</span><span class="sxs-lookup"><span data-stu-id="bc6c9-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bc6c9-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc6c9-124">See also</span></span>

[<span data-ttu-id="bc6c9-125">DNS-Anforderungen für einfache URLs in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="bc6c9-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
