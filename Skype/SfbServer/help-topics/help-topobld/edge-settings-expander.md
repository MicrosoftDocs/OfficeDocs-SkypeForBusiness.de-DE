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
- NOCSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 'Die Einstellungen für einen vorhandenen Edgepool mit einem oder mehreren Servern werden in den folgenden Abschnitten bearbeitet:'
ms.openlocfilehash: 963d396705bb2bc692cdd22e8857f23d351a95b0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820017"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="bd5a1-103">Edgeeinstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="bd5a1-103">Edge Settings Expander</span></span>

<span data-ttu-id="bd5a1-104">Die Einstellungen für einen vorhandenen Edgepool mit einem oder mehreren Servern werden in den folgenden Abschnitten bearbeitet:</span><span class="sxs-lookup"><span data-stu-id="bd5a1-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>

- <span data-ttu-id="bd5a1-105">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="bd5a1-105">General settings</span></span>

- <span data-ttu-id="bd5a1-106">Einstellungen für nächsten Hop</span><span class="sxs-lookup"><span data-stu-id="bd5a1-106">Next hop selection settings</span></span>

- <span data-ttu-id="bd5a1-107">Edgeserver-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="bd5a1-107">Edge Server configuration</span></span>



## <a name="general-settings"></a><span data-ttu-id="bd5a1-108">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="bd5a1-108">General settings</span></span>

<span data-ttu-id="bd5a1-p101">Vollqualifizierter Domänenname (Fully Qualified Domain Name, FQDN) des internen Pools für den Edgeserverpool. Bearbeiten Sie den FQDN des Pools, um diese Einstellung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-p101">Internal pool fully qualified domain name (FQDN) of the Edge Server pool. Edit the FQDN of the pool to change this setting.</span></span>

<span data-ttu-id="bd5a1-111">Aktivieren Sie das Kontrollkästchen **Föderation für diesen Edge-Pool aktivieren (Port 5061)** , wenn Sie einen Verbund mit einem vertrauenswürdigen Partner für lync Server 2013, Microsoft lync Server 2010 oder Microsoft Office Communications Server 2007 R2 einrichten möchten.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Lync Server 2013, Microsoft Lync Server 2010 or Microsoft Office Communications Server 2007 R2 trusted partner.</span></span>

<span data-ttu-id="bd5a1-112">Wählen Sie **XMPP-Partnerverbund für diesen Edgepool aktivieren** aus, um den XMPP-Partnerverbund zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-112">Select **Enable XMPP federation for this Edge pool** to enable XMPP federation.</span></span>

<span data-ttu-id="bd5a1-113">Geben Sie die Portnummer unter **Interner Port für die Konfigurationsreplikation (HTTPS)** an.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-113">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>

## <a name="next-hop-selection-settings"></a><span data-ttu-id="bd5a1-114">Einstellungen für nächsten Hop</span><span class="sxs-lookup"><span data-stu-id="bd5a1-114">Next hop selection settings</span></span>

<span data-ttu-id="bd5a1-115">Wählen Sie einen Director, Director-Pool, Front-End-Server oder Front-End-Serverpool aus dem Dropdown-Listenfeld aus, um den nächsten Hoppool\*\*\*\* anzugeben oder zu bearbeiten, den der Edgeserver für die Kommunikation mit der internen Infrastruktur verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-115">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="bd5a1-116">Nur Directors oder Front Ends, die im Topologie-Generator konfiguriert wurden, werden zur Auswahl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-116">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>

## <a name="edge-server-configuration"></a><span data-ttu-id="bd5a1-117">Edgeserver-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="bd5a1-117">Edge Server configuration</span></span>

<span data-ttu-id="bd5a1-118">Um die externen Einstellungen\*\*\*\* für die Edgeserver zu bearbeiten oder anzugeben, müssen Sie zunächst festlegen, ob separate IP-Adressen für den SIP-Zugriff, die Webkonferenzfunktion und den A/V-Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-118">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>

<span data-ttu-id="bd5a1-p103">Wenn separate IP-Adressen verwendet werden sollen, aktivieren Sie das Kontrollkästchen **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren**. Für jeden Dienst muss ein DNS-A-Eintrag (Host) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-p103">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding DNS host (A) record created for it.</span></span>

<span data-ttu-id="bd5a1-p104">Für jeden externen Dienst geben Sie einen FQDN und einen zugeordneten Port an. Für den **SIP-Zugriff** würden z. B. „sip.contoso.com“ und der Port 5061 verwendet.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-p104">For each of the external-facing services, you specify a FQDN and an associated port. For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd5a1-p105">Wenn Sie separate vollqualifizierte Domänennamen für die externen Dienste auswählen, muss jedem Dienst ein eindeutiger Portwert zugeordnet werden. Standardmäßig ist für SIP der Port 5061/TLS, für den Webkonferenz-Edgedienst der Port 444/TLS und für den A/V-Konferenzserver der Port 443/TLS festgelegt. Wenn Sie diese Einstellungen ändern (z. B. die Verwendung separater vollqualifizierter Domänennamen und IP-Adressen oder Ports festlegen), müssen Sie alle anderen Dienste aktualisieren, die von den ursprünglich konfigurierten Werten abhängen.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-p105">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="bd5a1-p106">Wenn Sie festlegen, dass Ihre Organisation einen einzigen FQDN und eine einzige IP-Adresse für die externen Dienste verwendet, deaktivieren Sie das Kontrollkästchen **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren**. Bei Bedarf können Sie anschließend die Werte für den Pool-FQDN und den Port für den **SIP-Zugriff** ändern.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd5a1-128">Wenn Sie diese Einstellungen ändern (z. B. die Verwendung separater vollqualifizierter Domänennamen und IP-Adressen oder Ports festlegen), müssen Sie alle anderen Dienste aktualisieren, die von den ursprünglich konfigurierten Werten abhängen.</span><span class="sxs-lookup"><span data-stu-id="bd5a1-128">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd5a1-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd5a1-129">See also</span></span>

<span data-ttu-id="bd5a1-130">Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für die Edgedienste finden Sie unter [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span><span class="sxs-lookup"><span data-stu-id="bd5a1-130">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>


