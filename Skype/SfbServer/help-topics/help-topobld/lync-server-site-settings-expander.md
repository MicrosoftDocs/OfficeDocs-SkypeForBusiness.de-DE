---
title: Einstellungen für Lync Server-Standort – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: So ändern Sie die Eigenschaften eines vorhandenen Standorts
ms.openlocfilehash: 69555a04be4125e213ba2eca7afd7255100c0444
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217566"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="d6953-103">Einstellungen für Lync Server-Standort – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="d6953-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="d6953-104">So ändern Sie die Eigenschaften eines vorhandenen Standorts</span><span class="sxs-lookup"><span data-stu-id="d6953-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="d6953-105">Standorteigenschaften</span><span class="sxs-lookup"><span data-stu-id="d6953-105">Site properties</span></span>

<span data-ttu-id="d6953-106">In den Standorteigenschaften können Sie Folgendes ändern: den Standortnamen (erforderlich), Beschreibung (optional), Ort (optional), Bundesland/Kanton (optional) und Länder-/Regionscode (optional).</span><span class="sxs-lookup"><span data-stu-id="d6953-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="d6953-107">Ausführliche Informationen zu Standorteigenschaften finden Sie unter [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span><span class="sxs-lookup"><span data-stu-id="d6953-107">For details about site properties, see [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="d6953-108">Eigenschaften von Partnerverbundrouten</span><span class="sxs-lookup"><span data-stu-id="d6953-108">Federation Route properties</span></span>

<span data-ttu-id="d6953-p101">Zum Zuweisen einer Partnerverbundroute zu einem Standort muss für einen Edgeserver bzw. Edgeserverpool der Partnerverbund aktiviert sein. Ist dies nicht der Fall, können die Einstellungen für die Zuweisung einer Partnerverbundroute nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d6953-p101">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool. If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="d6953-p102">Wenn die Partnerverbundeinstellung für den Edgeserver oder -pool konfiguriert wurde, klicken Sie auf Standortebene auf **Aktivieren**. Wählen Sie anschließend einen Edge- oder Director-Server in der Dropdownliste aus, um diesen als Partnerverbundroute festzulegen.</span><span class="sxs-lookup"><span data-stu-id="d6953-p102">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level. Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="d6953-p103">Diese Einstellung gilt für alle Standorte. Vergewissern Sie sich, dass die Einstellung, die Sie für diesen Standort konfigurieren, für alle Standorte geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="d6953-p103">This setting will affect all sites. Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6953-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6953-115">See also</span></span>

<span data-ttu-id="d6953-116">Ausführliche Informationen finden Sie unter [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span><span class="sxs-lookup"><span data-stu-id="d6953-116">For details, see [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>


