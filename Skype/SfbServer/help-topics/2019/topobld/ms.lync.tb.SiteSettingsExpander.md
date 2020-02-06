---
title: Einstellungen für Lync Server-Standort – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Gehen Sie wie folgt vor, um die Eigenschaften einer vorhandenen Website zu bearbeiten:'
ms.openlocfilehash: a8240030bd05ae865cb54343a460c8be414546a3
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798292"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="2b25d-103">Einstellungen für Lync Server-Standort – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="2b25d-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="2b25d-104">Gehen Sie wie folgt vor, um die Eigenschaften einer vorhandenen Website zu bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="2b25d-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="2b25d-105">Websiteeigenschaften</span><span class="sxs-lookup"><span data-stu-id="2b25d-105">Site properties</span></span>

<span data-ttu-id="2b25d-106">In Websiteeigenschaften können Sie den Websitenamen (erforderlich), Beschreibung (optional), Ort (optional), Bundesland/Kanton (optional) und den Code für Land/Region (optional) ändern oder ändern.</span><span class="sxs-lookup"><span data-stu-id="2b25d-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="2b25d-107">Ausführliche Informationen zu Websiteeigenschaften finden Sie unter [Hinzufügen von Verzweigungs Websites zu Ihrer Topologie](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span><span class="sxs-lookup"><span data-stu-id="2b25d-107">For details about site properties, see [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="2b25d-108">Verbund Routeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="2b25d-108">Federation Route properties</span></span>

<span data-ttu-id="2b25d-109">Zum Einrichten einer Standort Verbund-Routenzuordnung müssen Sie zuerst den Verbund auf einem Edgeserver oder einem Edgeserver-Pool aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2b25d-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="2b25d-110">Wenn der Verbund auf einem Edgeserver oder Pool nicht aktiviert ist, stehen die Zuordnungseinstellungen für die Verbund Route für die Website nicht zur Änderung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2b25d-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="2b25d-111">Wenn die Verbund Einstellung auf dem Edgeserver oder Pool konfiguriert wurde, wählen Sie auf Websiteebene **aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="2b25d-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="2b25d-112">Wählen Sie dann in der Dropdownliste eine Kante oder einen Regisseur aus, um die Föderations Route festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2b25d-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="2b25d-113">Diese Einstellung wirkt sich auf alle Websites aus.</span><span class="sxs-lookup"><span data-stu-id="2b25d-113">This setting will affect all sites.</span></span> <span data-ttu-id="2b25d-114">Stellen Sie sicher, dass die Einstellungen, die Sie auf dieser Website konfigurieren, für alle Websites geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="2b25d-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b25d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b25d-115">See also</span></span>

<span data-ttu-id="2b25d-116">Ausführliche Informationen finden Sie unter [Topologien für den Zugriff durch externe Benutzer](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span><span class="sxs-lookup"><span data-stu-id="2b25d-116">For details, see [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>


