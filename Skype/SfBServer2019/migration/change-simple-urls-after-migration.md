---
title: Ändern einfacher URLs nach der Migration
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
description: Skype for Business Server unterstützt einfache URLs.
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753905"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="d331c-103">Ändern einfacher URLs nach der Migration</span><span class="sxs-lookup"><span data-stu-id="d331c-103">Change simple URLs after migration</span></span>

<span data-ttu-id="d331c-104">Skype for Business Server unterstützt drei einfache URLs:</span><span class="sxs-lookup"><span data-stu-id="d331c-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="d331c-105">**Meet** is used as the base URL for all conferences in the site or organization.</span><span class="sxs-lookup"><span data-stu-id="d331c-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="d331c-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span><span class="sxs-lookup"><span data-stu-id="d331c-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="d331c-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span><span class="sxs-lookup"><span data-stu-id="d331c-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="d331c-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span><span class="sxs-lookup"><span data-stu-id="d331c-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="d331c-109">Der **Administrator** ermöglicht den schnellen Zugriff auf die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="d331c-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="d331c-110">Die einfache Admin-URL wird innerhalb Ihrer Organisation verwendet.</span><span class="sxs-lookup"><span data-stu-id="d331c-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="d331c-111">Nach der Migration zu Skype for Business Server müssen Sie wissen, wie sich die Änderung auf Ihre DNS-Einträge und Zertifikate für einfache URLs auswirkt.</span><span class="sxs-lookup"><span data-stu-id="d331c-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="d331c-112">Wenn der Legacy Skype for Business Server Director in der Topologie weiterhin verwendet wird, sind keine Änderungen an ihren einfachen URLs erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d331c-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="d331c-113">Wenn der Skype for Business Server Director nach der Migration aus der Topologie entfernt wird, müssen die DNS-Einträge für einfache URLs so aktualisiert werden, dass Sie auf einen der Skype for Business Server-Pools verweist.</span><span class="sxs-lookup"><span data-stu-id="d331c-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="d331c-114">Bei jeder Namensänderung für eine einfache URL müssen Sie jedoch das Cmdlet "Enable-CsComputer" auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="d331c-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="d331c-115">So aktualisieren Sie die einfache Meet-URL</span><span class="sxs-lookup"><span data-stu-id="d331c-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="d331c-116">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den obersten Knoten **Skype for Business Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d331c-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="d331c-117">Wählen Sie im linken Bereich **einfache URLs** und dann unter **Besprechungs-URLs:** wählen Sie die URL "Meet" aus, und klicken Sie dann auf **URL bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d331c-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="d331c-118">Aktualisieren Sie die URL auf den gewünschten Wert, und klicken Sie auf **OK**, um die bearbeitete URL zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d331c-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="d331c-119">So aktualisieren Sie die einfache Admin-URL</span><span class="sxs-lookup"><span data-stu-id="d331c-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="d331c-120">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den obersten Knoten **Skype for Business Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d331c-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="d331c-121">Wählen Sie **einfache URLs** im linken Bereich aus, und geben Sie dann unterhalb des Felds **Administrative Zugriffs-URL** die einfache URL ein, die Sie für den administrativen Zugriff auf Skype for Business Server Systemsteuerung wünschen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d331c-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="d331c-122">Es wird empfohlen, eine möglichst einfache URL als Admin-URL zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d331c-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="d331c-123">Die einfachste Option ist https://admin . <em>\<domain\></em> .</span><span class="sxs-lookup"><span data-stu-id="d331c-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d331c-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d331c-124">See also</span></span>

[<span data-ttu-id="d331c-125">DNS-Anforderungen für einfache URLs in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d331c-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
