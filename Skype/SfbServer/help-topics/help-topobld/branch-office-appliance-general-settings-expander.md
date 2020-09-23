---
title: Allgemeine Einstellungen für Branch Office Appliance – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 'Die Einstellungen für eine vorhandene Survivable Branch Appliance oder einen Survivable Branch Server werden in den folgenden Abschnitten bearbeitet:'
ms.openlocfilehash: 40ebf4a22bcfc3392c2f1dc8238a46b610d22281
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216126"
---
# <a name="branch-office-appliance-general-settings-expander"></a><span data-ttu-id="b5564-103">Allgemeine Einstellungen für Branch Office Appliance – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="b5564-103">Branch Office Appliance General Settings Expander</span></span>

<span data-ttu-id="b5564-104">Die Einstellungen für eine vorhandene Survivable Branch Appliance oder einen Survivable Branch Server werden in den folgenden Abschnitten bearbeitet:</span><span class="sxs-lookup"><span data-stu-id="b5564-104">To edit the settings for an existing Survivable Branch Appliance or Survivable Branch Server, you are presented with the following sections:</span></span>

- <span data-ttu-id="b5564-105">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="b5564-105">General settings</span></span>

- <span data-ttu-id="b5564-106">Flexibilitätseinstellungen</span><span class="sxs-lookup"><span data-stu-id="b5564-106">Resiliency settings</span></span>

- <span data-ttu-id="b5564-107">Vermittlungsservereinstellungen</span><span class="sxs-lookup"><span data-stu-id="b5564-107">Mediation Server settings</span></span>



<span data-ttu-id="b5564-108">Für eine Survivable Branch Appliance oder einen Survivable Branch Server wird Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b5564-108">For a Survivable Branch Appliance or Survivable Branch Server, you are presented with the following:</span></span>

## <a name="general-settings"></a><span data-ttu-id="b5564-109">Allgemeine Einstellungen</span><span class="sxs-lookup"><span data-stu-id="b5564-109">General settings</span></span>

<span data-ttu-id="b5564-p101">Der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) der Survivable Branch Appliance oder des Survivable Branch Servers. Bearbeiten Sie den FQDN des Servers, um den Wert zu ändern. Sie müssen über einen DNS-A-Eintrag (Domain Name System) verfügen, der mit dem neuen Wert übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="b5564-p101">The fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>

<span data-ttu-id="b5564-p102">Sie können die Option **Alle konfigurierten IP-Adressen verwenden** oder **Dienstnutzung auf ausgewählte IP-Adressen beschränken** wählen. Wenn Sie den Dienst auf definierte IP-Adressen beschränken, definieren Sie die primäre IP-Adresse, die der Server für die gesamte Kommunikation verwendet (mit Ausnahme der PSTN-Kommunikation).\*\*\*\* Für die Verwendung mit dem Telefonfestnetz wird eine gesonderte IP-Adresse bestimmt.</span><span class="sxs-lookup"><span data-stu-id="b5564-p102">You can select to **Use all configured IP addresses** or to **Limit service usage to selected IP addresses**. If you select to **Limit the service to defined IP addresses**, you will define the primary IP address that the server will use for all communications, except for the public switched telephone network (PSTN) gateway. You define a separate IP address for PSTN usage.</span></span>

<span data-ttu-id="b5564-116">In **Zuordnungen** können Sie Folgendes bearbeiten oder angeben:</span><span class="sxs-lookup"><span data-stu-id="b5564-116">In **Associations**, you can edit or specify the following:</span></span>

- <span data-ttu-id="b5564-117">Mit zuordnen Archivierungsserver können Sie auswählen, ob ein Archivierungsserver dem Survivable Branch Appliance oder Survivable Branch Server zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b5564-117">Associate Archiving Server enables you to select to associate an Archiving Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="b5564-118">Sie können ein bereits definiertes Archivierungsserver auswählen, indem Sie den Server aus der Dropdownliste auswählen oder auf **neu** klicken, um einen neuen Archivierungsserver anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b5564-118">You can select from an already defined Archiving Server by selecting the server from the drop-down list, or click **New** to specify a new Archiving Server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b5564-119">Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein.</span><span class="sxs-lookup"><span data-stu-id="b5564-119">Before publishing the newly defined topology, the server that you specify must exist and must be joined to the domain.</span></span>

- <span data-ttu-id="b5564-120">Mit zuordnen Monitoring Server können Sie auswählen, ob ein Monitoring Server dem Survivable Branch Appliance oder Survivable Branch Server zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b5564-120">Associate Monitoring Server allows you to select to associate a Monitoring Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="b5564-121">Sie können ein bereits definiertes Monitoring Server auswählen, indem Sie den Server aus der Dropdownliste auswählen oder auf **neu** klicken, um einen neuen Monitoring Server anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b5564-121">You can select from an already defined Monitoring Server by selecting the server from the drop-down list, or click **New** to specify a new Monitoring Server.</span></span>

- <span data-ttu-id="b5564-122">Mit Associate Edgepool können Sie auswählen, ob eine Edgeserver oder ein Pool dem Survivable Branch Appliance oder Survivable Branch Server zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b5564-122">Associate Edge pool enables you to select to associate an Edge Server or pool with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="b5564-123">Sie können in der Dropdownliste einen bereits definierten Edgeserver oder -pool auswählen oder auf **Neu** klicken, um einen neuen Edgeserver oder -pool anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b5564-123">You can select from an already defined Edge Server or pool by selecting the server from the drop-down list, or click **New** to specify a new Edge Server or pool.</span></span>

## <a name="resiliency"></a><span data-ttu-id="b5564-124">Flexibilität</span><span class="sxs-lookup"><span data-stu-id="b5564-124">Resiliency</span></span>

<span data-ttu-id="b5564-p106">Dank der Flexibilität (Ausfallsicherheit) ist die hohe Verfügbarkeit des Registrierungspools gewährleistet. Durch Bereitstellung einer Sicherungsregistrierungsstelle für den Fall eines Ausfalls der primären Registrierungsstelle kann die Sicherungsregistrierungsstelle die Aufgabe der ausgefallenen Registrierung übernehmen und Benutzern die Anmeldung und Kommunikation ermöglichen. Bei Benutzern kann es, je nachdem, welche Systeme mit der primären Registrierung ausgefallen sind, möglicherweise zu einer eingeschränkten Funktionalität kommen.</span><span class="sxs-lookup"><span data-stu-id="b5564-p106">Resiliency provides high availability for the Registrar pool. By providing a backup Registrar, if the primary Registrar fails, the backup Registrar can take over for the failed Registrar, enabling users to log on and communicate. There may be reduced functionality for users, depending on what systems have failed with the primary Registrar.</span></span>

<span data-ttu-id="b5564-128">Wählen Sie in der Dropdownliste die Enterprise Edition-Front-End-Pool oder Standard Edition-Front-End-Server aus, die als Sicherungs Registrierungsstelle für die Survivable Branch Appliance oder Survivable Branch Server fungieren soll.</span><span class="sxs-lookup"><span data-stu-id="b5564-128">From the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that will act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="b5564-129">Sie können außerdem Zeitintervalle für Failover und Fallback auswählen.</span><span class="sxs-lookup"><span data-stu-id="b5564-129">You can also select to enable Failover and Fallback time intervals.</span></span> <span data-ttu-id="b5564-130">Die (in Sekunden angegebenen) Zeiteinstellungen für Failover und Fallback ermöglichen die automatische Erkennung einer ausgefallenen Registrierung und eines Zeitpuffers zur automatischen Bestimmung, dass die primäre Registrierung wieder betriebsbereit ist und den Registrierungsprozess übernehmen kann.</span><span class="sxs-lookup"><span data-stu-id="b5564-130">Enabling the failover and fallback time settings (specified in seconds) allows for the automatic detection of a failed Registrar, and a fallback time to allow for automatic determination that the primary is back up and can take over the Registrar process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5564-131">Achten Sie beim Definieren der Fehlererkennung und des Fallback-Intervalls darauf, kein Intervall einzugeben, das dazu führt, dass Failover und Fallback auftreten, wenn die Registrierungsstelle für einen kurzen Zeitraum nicht antwortet.</span><span class="sxs-lookup"><span data-stu-id="b5564-131">When defining the failure detection and the fallback interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="b5564-132">Möglicherweise reagiert die primäre Registrierungsstelle aufgrund des Ladens des Pools oder der Server nicht für kurze Zeiträume.</span><span class="sxs-lookup"><span data-stu-id="b5564-132">It is possible that the primary Registrar may not respond for short periods of time, based on the loading of the pool or servers.</span></span> <span data-ttu-id="b5564-133">Die Standardwerte für ein Survivable Branch Appliance oder ein Survivable Branch Server in einer Website zu einem Pool oder Standard Edition Front-End-Server beträgt 120 Sekunden für Failover und 240 Sekunden für Fallback.</span><span class="sxs-lookup"><span data-stu-id="b5564-133">The default values for a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition Front End Server is 120 seconds for failover and 240 seconds for fallback.</span></span>

## <a name="mediation-server"></a><span data-ttu-id="b5564-134">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="b5564-134">Mediation Server</span></span>

<span data-ttu-id="b5564-135">Für **Vermittlungsserver** können Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="b5564-135">For **Mediation Server** you can specify the following:</span></span>

<span data-ttu-id="b5564-136">Das Kontrollkästchen **Gemeinsam ausgeführter Vermittlungsserver aktiviert** steht für eine Survivable Branch Appliance oder einen Survivable Branch Server nicht zur Verfügung, da der Vermittlungsserver gemeinsam ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b5564-136">The check box for **Collocated Mediation Server enabled** is not available on a Survivable Branch Appliance or Survivable Branch Server because the Mediation Server is collocated.</span></span>

<span data-ttu-id="b5564-p109">Für TLS (Transport Layer Security) legen Sie den Überwachungsport für die Poolserver fest. Standardmäßig lautet dieser Port 5067. Wenn Sie **TCP-Port aktivieren** aktivieren, müssen Sie für den gemeinsam ausgeführten Vermittlungsserver einen TCP-Port (Transmission Control Protocol) angeben. Diese Einstellung ist optional. Überprüfen Sie die Gateway- bzw. PSTN-Anforderungen dahingehend, ob diese Einstellung erforderlich ist. Standardmäßig ist der Wert des TCP-Ports auf 5068 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b5564-p109">You define the listening port on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a TCP port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="b5564-p110">Sie definieren PSTN-Gateways, die dem gemeinsam ausgeführten Vermittlungsserver zugeordnet sind. Wenn bereits Gateways definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung. Falls noch keine Gateways definiert wurden, jedoch zur Definition zur Verfügung stehen, können Sie **Neu** auswählen. Sie können bereits für den jeweiligen Vermittlungsserver konfigurierte Gateways auch entfernen. Wählen Sie das Gateway aus, und klicken Sie dann auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="b5564-p110">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you have not defined any gateways, but you have them available to define, you can select **New**. You can also remove gateways that are already configured for this Mediation Server. Select the gateway, and then click **Remove**.</span></span>

<span data-ttu-id="b5564-p111">Wenn einem Vermittlungsserver mehrere Gateways zugeordnet sind, ist das erste zugeordnete Gateway das Standardgateway. Wenn Sie ein anderes Gateway als Standardgateway auswählen müssen, wählen Sie das gewünschte Gateway aus, und klicken Sie auf **Als Standard**.</span><span class="sxs-lookup"><span data-stu-id="b5564-p111">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you must choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5564-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5564-149">See also</span></span>

<span data-ttu-id="b5564-150">Weitere Informationen zum Definieren und Konfigurieren der Einstellungen für die Survivable Branch Appliance oder den Survivable Branch Server finden Sie unter [Branch-Site Resiliency Solutions](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).</span><span class="sxs-lookup"><span data-stu-id="b5564-150">For details about defining and configuring the settings for the Survivable Branch Appliance or Survivable Branch Server, see [Branch-Site Resiliency Solutions](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).</span></span>


