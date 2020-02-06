---
title: Ändern einfacher URLs nach der Migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server unterstützt einfache URLs.
ms.openlocfilehash: ab820c1b24eb9b2e8befc85a34e82d068c9083ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813883"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="80dcd-103">Ändern einfacher URLs nach der Migration</span><span class="sxs-lookup"><span data-stu-id="80dcd-103">Change simple URLs after migration</span></span>

<span data-ttu-id="80dcd-104">Skype for Business Server unterstützt drei einfache URLs:</span><span class="sxs-lookup"><span data-stu-id="80dcd-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="80dcd-105">**Meet** wird als Basis-URL für alle Konferenzen auf der Website oder Organisation verwendet.</span><span class="sxs-lookup"><span data-stu-id="80dcd-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="80dcd-106">Mit der einfachen URL für Besprechungen sind Links zu Besprechungen einfach zu verstehen und einfach zu kommunizieren und zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="80dcd-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="80dcd-107">**Einwahl** ermöglicht den Zugriff auf die Webseite für Einwahlkonferenzeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="80dcd-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="80dcd-108">Die Einwahl einfache URL ist in allen Besprechungseinladungen enthalten, damit Benutzer, die sich in die Besprechung einwählen möchten, auf die erforderlichen Telefonnummern und PIN-Informationen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="80dcd-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="80dcd-109">Der **Administrator** ermöglicht den schnellen Zugriff auf das Skype for Business Server-Control Panel.</span><span class="sxs-lookup"><span data-stu-id="80dcd-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="80dcd-110">Die einfache Admin-URL dient der internen Verwendung in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="80dcd-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="80dcd-111">Nach der Migration zu Skype for Business Server müssen Sie wissen, wie sich die Änderung auf Ihre DNS-Einträge und Zertifikate für einfache URLs auswirkt.</span><span class="sxs-lookup"><span data-stu-id="80dcd-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="80dcd-112">Wenn der Legacy-Manager von Skype for Business Server in der Topologie weiterhin verwendet wird, sind keine Änderungen an ihren einfachen URLs erforderlich.</span><span class="sxs-lookup"><span data-stu-id="80dcd-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="80dcd-113">Wenn der Skype for Business Server-Director nach der Migration aus der Topologie entfernt wird, müssen die einfachen URL-DNS-Einträge aktualisiert werden, sodass Sie auf einen der Skype for Business Server-Pools verweisen.</span><span class="sxs-lookup"><span data-stu-id="80dcd-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="80dcd-114">Wenn Sie jedoch einen einfachen URL-Namen ändern, müssen Sie Enable-CsComputer auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="80dcd-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="80dcd-115">So aktualisieren Sie die einfache URL für Besprechungen</span><span class="sxs-lookup"><span data-stu-id="80dcd-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="80dcd-116">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den obersten Knoten **von Skype for Business Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="80dcd-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="80dcd-117">Wählen Sie im linken Bereich und dann unter Besprechungs- **URLs** **einfache URLs** aus: Wählen Sie die URL erfüllen aus, und klicken Sie dann auf **URL bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="80dcd-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="80dcd-118">Aktualisieren Sie die URL auf den gewünschten Wert, und klicken Sie dann auf **OK** , um die bearbeitete URL zu speichern.</span><span class="sxs-lookup"><span data-stu-id="80dcd-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="80dcd-119">So aktualisieren Sie die einfache Administrator-URL</span><span class="sxs-lookup"><span data-stu-id="80dcd-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="80dcd-120">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den obersten Knoten **von Skype for Business Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="80dcd-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="80dcd-121">Wählen Sie im linken Bereich **einfache URLs** aus, und geben Sie dann unter **Administratorzugriff-URL** die einfache URL ein, die Sie für den administrativen Zugriff auf die Skype for Business Server-Systemsteuerung benötigen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="80dcd-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="80dcd-122">Es wird empfohlen, die einfachstmögliche URL als Verwaltungs-URL zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="80dcd-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="80dcd-123">Die einfachste Option ist https://admin. <em> \<Domäne\></em>aus.</span><span class="sxs-lookup"><span data-stu-id="80dcd-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="80dcd-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80dcd-124">See also</span></span>

[<span data-ttu-id="80dcd-125">DNS-Anforderungen für einfache URLs in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="80dcd-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
