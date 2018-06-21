---
title: Lync Server-Website-Einstellungen – Erweiterung
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Führen Sie folgende Schritte aus, um die Eigenschaften einer vorhandenen Website zu bearbeiten:'
ms.openlocfilehash: da25eb65d041f52668c9b854d48da3d7894d193b
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "19988474"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="f6e58-103">Lync Server-Website-Einstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="f6e58-103">Lync Server Site Settings Expander</span></span>
 
<span data-ttu-id="f6e58-104">Führen Sie folgende Schritte aus, um die Eigenschaften einer vorhandenen Website zu bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="f6e58-104">To edit the properties of an existing site, do the following:</span></span>
  
## 

### <a name="site-properties"></a><span data-ttu-id="f6e58-105">Site-Standardeigenschaften</span><span class="sxs-lookup"><span data-stu-id="f6e58-105">Site properties</span></span>

<span data-ttu-id="f6e58-106">In Site-Standardeigenschaften können Sie ändern oder ändern den Standortnamen (erforderlich), Beschreibung (optional), Ort (optional), Bundesland/Kanton (optional) und Länder-/Regionscode (optional).</span><span class="sxs-lookup"><span data-stu-id="f6e58-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>
  
<span data-ttu-id="f6e58-107">Ausführliche Informationen zu Standorteigenschaften finden Sie unter [Add Branch Sites to Your Topology](http://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span><span class="sxs-lookup"><span data-stu-id="f6e58-107">For details about site properties, see [Add Branch Sites to Your Topology](http://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>
  
### <a name="federation-route-properties"></a><span data-ttu-id="f6e58-108">Eigenschaften von Partnerverbundrouten</span><span class="sxs-lookup"><span data-stu-id="f6e58-108">Federation Route properties</span></span>

<span data-ttu-id="f6e58-109">Wenn eine Zuweisung der partnerverbundroute Route festlegen möchten, müssen Sie zuerst den Verbund aktiviert auf einem Edge-Server oder einem Edge-Server-Pool verfügen.</span><span class="sxs-lookup"><span data-stu-id="f6e58-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="f6e58-110">Wenn Verbund auf einem Edge-Server oder Pool nicht aktiviert ist, werden die Federation Route Zuordnung Einstellungen für die Website nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f6e58-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>
  
<span data-ttu-id="f6e58-111">Wenn die partnerverbundeinstellung für den Edge-Server oder Pool konfiguriert wurde, wählen Sie auf der Websiteebene **Aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="f6e58-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="f6e58-112">Wählen Sie dann aus der Dropdown-Liste als partnerverbundroute Festlegen einer Kante oder einen Director aus.</span><span class="sxs-lookup"><span data-stu-id="f6e58-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="f6e58-113">Diese Einstellung wirkt sich auf alle Websites.</span><span class="sxs-lookup"><span data-stu-id="f6e58-113">This setting will affect all sites.</span></span> <span data-ttu-id="f6e58-114">Stellen Sie sicher, dass die Einstellung, die Sie an diesem Standort konfigurieren für alle Websites geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="f6e58-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span> 
  
### 

<span data-ttu-id="f6e58-115">Weitere Informationen hierzu finden Sie unter [Topologien für den Zugriff externer Benutzer](http://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span><span class="sxs-lookup"><span data-stu-id="f6e58-115">For details, see [Topologies for External User Access](http://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>
  

