---
title: Edgeeinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 'Um die Einstellungen für eine vorhandene Edgepool mit einem oder mehreren Servern zu bearbeiten, werden die folgenden Abschnitte angezeigt:'
ms.openlocfilehash: c2d4ec8e97557a584821bb82ef1d24b9bfa7a9bb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218896"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="449bf-103">Edgeeinstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="449bf-103">Edge Settings Expander</span></span>

<span data-ttu-id="449bf-104">Um die Einstellungen für eine vorhandene Edgepool mit einem oder mehreren Servern zu bearbeiten, werden die folgenden Abschnitte angezeigt:</span><span class="sxs-lookup"><span data-stu-id="449bf-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>

- <span data-ttu-id="449bf-105">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="449bf-105">General settings</span></span>

- <span data-ttu-id="449bf-106">Auswahl Einstellungen für den nächsten Hop</span><span class="sxs-lookup"><span data-stu-id="449bf-106">Next hop selection settings</span></span>

- <span data-ttu-id="449bf-107">Edgeserver Konfiguration</span><span class="sxs-lookup"><span data-stu-id="449bf-107">Edge Server configuration</span></span>



## <a name="general-settings"></a><span data-ttu-id="449bf-108">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="449bf-108">General settings</span></span>

<span data-ttu-id="449bf-109">Interner Pool vollqualifizierter Domänenname (FQDN) des Edgeserver Pools.</span><span class="sxs-lookup"><span data-stu-id="449bf-109">Internal pool fully qualified domain name (FQDN) of the Edge Server pool.</span></span> <span data-ttu-id="449bf-110">Bearbeiten Sie den FQDN des Pools, um diese Einstellung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="449bf-110">Edit the FQDN of the pool to change this setting.</span></span>

<span data-ttu-id="449bf-111">Aktivieren Sie das Kontrollkästchen Partner **Verbund für diesen Edgepool aktivieren (Port 5061)** , wenn Sie einen Verbund mit einem lync Server 2013, Microsoft lync Server 2010 oder Microsoft Office Communications Server 2007 R2 vertrauenswürdigen Partner einrichten möchten.</span><span class="sxs-lookup"><span data-stu-id="449bf-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Lync Server 2013, Microsoft Lync Server 2010 or Microsoft Office Communications Server 2007 R2 trusted partner.</span></span>

<span data-ttu-id="449bf-112">Wählen Sie XMPP-Partner **Verbund für diesen Edgepool aktivieren** aus, um den XMPP-Partnerverbund zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="449bf-112">Select **Enable XMPP federation for this Edge pool** to enable XMPP federation.</span></span>

<span data-ttu-id="449bf-113">Geben Sie die Portnummer für den **Port der internen Konfigurations Replikation (HTTPS)** an.</span><span class="sxs-lookup"><span data-stu-id="449bf-113">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>

## <a name="next-hop-selection-settings"></a><span data-ttu-id="449bf-114">Auswahl Einstellungen für den nächsten Hop</span><span class="sxs-lookup"><span data-stu-id="449bf-114">Next hop selection settings</span></span>

<span data-ttu-id="449bf-115">Um den Pool für den **nächsten Hop** festzulegen oder zu ändern, den die Edgeserver für die Kommunikation mit der internen Infrastruktur verwenden, wählen Sie im Dropdown-Listenfeld einen Director-, Directorpool-, Front-End-Server-oder Front-End-Server-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="449bf-115">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="449bf-116">Für die Auswahl werden nur Directors oder Front-Ends angezeigt, die im Topologie-Generator konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="449bf-116">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>

## <a name="edge-server-configuration"></a><span data-ttu-id="449bf-117">Edgeserver Konfiguration</span><span class="sxs-lookup"><span data-stu-id="449bf-117">Edge Server configuration</span></span>

<span data-ttu-id="449bf-118">Um Einstellungen für die **externen Einstellungen** für die Edgeserver zu bearbeiten oder anzugeben, müssen Sie zunächst feststellen, ob Sie separate IP-Adressen für SIP-Zugriff, Webkonferenzen und den Audio/Video-Dienst verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="449bf-118">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>

<span data-ttu-id="449bf-119">Wenn separate IP-Adressen verwendet werden sollen, aktivieren Sie das Kontrollkästchen **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="449bf-119">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**.</span></span> <span data-ttu-id="449bf-120">Für jeden Dienst muss ein entsprechender DNS-Hosteintrag (a) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="449bf-120">Each service must have a corresponding DNS host (A) record created for it.</span></span>

<span data-ttu-id="449bf-121">Für jeden der extern angerichteten Dienste geben Sie einen FQDN und einen zugeordneten Port an.</span><span class="sxs-lookup"><span data-stu-id="449bf-121">For each of the external-facing services, you specify a FQDN and an associated port.</span></span> <span data-ttu-id="449bf-122">Beispielsweise würde der **SIP-Zugriff** SIP.contoso.com mit einem zugeordneten Port von 5061 verwenden.</span><span class="sxs-lookup"><span data-stu-id="449bf-122">For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="449bf-123">Wenn Sie separate vollqualifizierte Domänennamen für die externen Dienste auswählen, muss jedem Dienst ein eindeutiger Portwert zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="449bf-123">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it.</span></span> <span data-ttu-id="449bf-124">Standardmäßig befindet sich das SIP auf Port 5061/TLS, der Webkonferenz-Edgedienst befindet sich auf Port 444/TLS, und der A/V-Konferenzserver befindet sich auf Port 443/TLS.</span><span class="sxs-lookup"><span data-stu-id="449bf-124">By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS.</span></span> <span data-ttu-id="449bf-125">Wenn Sie Änderungen an diesen Einstellungen vornehmen, einschließlich der Verwendung separater FQDN-und IP-Adressen oder Ports, müssen Sie alle anderen Dienste aktualisieren, die auf die anfänglich konfigurierten Werte angewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="449bf-125">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="449bf-p106">Wenn Sie festlegen, dass Ihre Organisation einen einzigen FQDN und eine einzige IP-Adresse für die externen Dienste verwendet, deaktivieren Sie das Kontrollkästchen **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren**. Bei Bedarf können Sie anschließend die Werte für den Pool-FQDN und den Port für den SIP-Zugriff\*\*\*\* ändern.</span><span class="sxs-lookup"><span data-stu-id="449bf-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="449bf-128">Wenn Sie diese Einstellungen ändern (z. B. die Verwendung separater vollqualifizierter Domänennamen und IP-Adressen oder Ports festlegen), müssen Sie alle anderen Dienste aktualisieren, die von den ursprünglich konfigurierten Werten abhängen.</span><span class="sxs-lookup"><span data-stu-id="449bf-128">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

## <a name="see-also"></a><span data-ttu-id="449bf-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="449bf-129">See also</span></span>

<span data-ttu-id="449bf-130">Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für die Edge-Dienste finden Sie unter [define your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span><span class="sxs-lookup"><span data-stu-id="449bf-130">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>


