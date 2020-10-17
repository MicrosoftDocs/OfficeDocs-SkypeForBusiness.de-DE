---
title: Aktivieren der Remoteanrufsteuerung
description: Aktivieren Sie die Remoteanrufsteuerung.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8009ffc927ad3f7a4f83ad3505100f3a9d4e82d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551131"
---
# <a name="enable-remote-call-control"></a><span data-ttu-id="9cadf-103">Aktivieren der Remoteanrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="9cadf-103">Enable remote call control</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cadf-104">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="9cadf-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="9cadf-105">Die Remote Anrufsteuerung ermöglicht Benutzern das Steuern ihrer PBX-Telefone (Desktop Private Branch Exchange) mithilfe von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9cadf-105">Remote call control enables users to control their desktop private branch exchange (PBX) phones by using Lync Server 2013.</span></span> <span data-ttu-id="9cadf-106">Wenn Sie die Remoteanrufsteuerung in ihrer Vorgänger Umgebung bereitgestellt haben und diese lync Server 2013 migrieren möchten, müssen Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="9cadf-106">If you deployed remote call control in your legacy environment and want to migrate it Lync Server 2013, you need to perform the following tasks:</span></span>

1.  <span data-ttu-id="9cadf-107">Installieren Sie ein SIP/CSTA-Gateway, und konfigurieren Sie es für die Kommunikation mit dem Festnetztelefon.</span><span class="sxs-lookup"><span data-stu-id="9cadf-107">Install a SIP/CSTA gateway and configure it to communicate with your PBX.</span></span> <span data-ttu-id="9cadf-108">Sie müssen diesen Schritt ausführen, wenn Sie Ihren lync Server 2013 Pilot-Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9cadf-108">You need to do this step when you deploy your Lync Server 2013 pilot pool.</span></span>

2.  <span data-ttu-id="9cadf-109">Nachdem Sie Ihre Topologie zusammengeführt und ihre Richtlinien und Einstellungen migriert haben, konfigurieren Sie lync Server 2013, um CSTA-Anforderungen an das SIP/CSTA-Gateway weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="9cadf-109">After you merge your topology and migrate your policies and settings, configure Lync Server 2013 to route CSTA requests to the SIP/CSTA gateway.</span></span> <span data-ttu-id="9cadf-110">Es handelt sich hierbei um einen manuellen Schritt nach der automatischen Migration.</span><span class="sxs-lookup"><span data-stu-id="9cadf-110">This step is a manual step that follows the automated migration.</span></span> <span data-ttu-id="9cadf-111">Führen Sie zur Konfiguration des Routings für CSTA-Anforderungen Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="9cadf-111">To configure routing for CSTA requests, do the following:</span></span>
    
      - <span data-ttu-id="9cadf-112">Entfernen Sie Legacy-Autorisierungs Hosteinträge (als *vertrauenswürdige Server Einträge* in lync Server 2013 bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="9cadf-112">Remove legacy authorized host entries (known as *trusted server entries* in Lync Server 2013).</span></span> <span data-ttu-id="9cadf-113">Wenn Sie Benutzer von Ihrer Legacy Bereitstellung migrieren, müssen Sie sicherstellen, dass Sie alle vorhandenen autorisierten Hosteinträge entfernen, die Sie für das SIP/CSTA-Gateway erstellt haben, bevor Sie neue Einträge für vertrauenswürdige Anwendungen im lync Server 2013 Pilot-Pool konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9cadf-113">If you are migrating users from your legacy deployment, ensure that you remove all existing authorized host entries that you created for the SIP/CSTA gateway before you configure new trusted application entries on the Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="9cadf-114">Ausführliche Informationen zum Entfernen von autorisierten Legacy-Hosteinträgen finden Sie unter [Entfernen eines autorisierten Hosteintrags](remove-an-authorized-host-entry.md).</span><span class="sxs-lookup"><span data-stu-id="9cadf-114">For details about how to remove legacy authorized host entries, see [Remove an authorized host entry](remove-an-authorized-host-entry.md).</span></span>
    
      - <span data-ttu-id="9cadf-115">Konfigurieren einer statischen Route für die Remoteanrufsteuerung.</span><span class="sxs-lookup"><span data-stu-id="9cadf-115">Configure a static route for remote call control.</span></span> <span data-ttu-id="9cadf-116">Sie können eine statische Route für einzelne Pools konfigurieren, die die Remoteanrufsteuerung unterstützen sollen, oder Sie können eine globale statische Route konfigurieren, sodass für jeden Pool, der nicht mit einer statischen Route auf Poolebene konfiguriert ist, die globale statische Route verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9cadf-116">You can configure a static route for individual pools that you want to support remote call control, or you can configure a global static route so that each pool that is not configured with a pool-level static route uses the global static route.</span></span> <span data-ttu-id="9cadf-117">Ausführliche Informationen zum Konfigurieren der statischen Route finden Sie unter [Konfigurieren einer statischen Route für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9cadf-117">For details about how to configure the static route, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="9cadf-118">Konfigurieren Sie einen Eintrag einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in jedem Pool, der die Remoteanrufsteuerung unterstützen soll.</span><span class="sxs-lookup"><span data-stu-id="9cadf-118">Configure a trusted application entry for remote call control on each pool for which you want to support remote call control.</span></span> <span data-ttu-id="9cadf-119">Ausführliche Informationen zum Konfigurieren eines Eintrags für eine vertrauenswürdige Anwendung finden Sie unter [Konfigurieren eines Eintrags für eine vertrauenswürdige Anwendung für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9cadf-119">For details about how to configure a trusted application entry, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="9cadf-120">Wenn Sie ein SIP/CSTA-Gateway bereitgestellt haben, das TCP (Transmission Control Protocol) zum Herstellen einer Verbindung mit lync Server 2013 verwendet, definieren Sie die IP-Adresse des Gateways im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="9cadf-120">If you deployed a SIP/CSTA gateway that uses Transmission Control Protocol (TCP) to connect to Lync Server 2013, define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="9cadf-121">Ausführliche Informationen zum Definieren der IP-Adresse finden Sie unter [define a SIP/CSTA Gateway IP Address in lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9cadf-121">For details about defining the IP address, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in the Deployment documentation.</span></span>

4.  <span data-ttu-id="9cadf-122">Konfigurieren Sie lync 2013 Benutzer für die Remoteanrufsteuerung, indem Sie die Remoteanrufsteuerung aktivieren und einen Anschlussserver-URI (Uniform Resource Identifier) und einen Anschluss-URI zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9cadf-122">Configure Lync 2013 users for remote call control by enabling remote call control and assigning a line server Uniform Resource Identifier (URI) and a line URI.</span></span> <span data-ttu-id="9cadf-123">Wenn Sie Benutzer aus Ihrer Legacy Bereitstellung in lync Server 2013 migrieren, werden die Einstellungen für die Remoteanrufsteuerung zusammen mit den anderen Benutzereinstellungen migriert.</span><span class="sxs-lookup"><span data-stu-id="9cadf-123">When you migrate users from your legacy deployment to Lync Server 2013, the remote call control settings are migrated along with the other user settings.</span></span>

5.  <span data-ttu-id="9cadf-124">Wenn Sie die Normalisierungsregeln für Rufnummern im Adressbuch in Ihrer Vorversionsbereitstellung angepasst haben, müssen Sie nach der automatischen Migration der Richtlinien und Einstellungen einige manuelle Aufgaben durchführen, um die angepassten Normalisierungsregeln zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="9cadf-124">If you customized Address Book phone number normalization rules in your legacy deployment, you need to perform some manual tasks after the automated migration of policies and settings is complete to migrate the customized normalization rules.</span></span> <span data-ttu-id="9cadf-125">Wenn Sie die Normalisierungsregeln nicht angepasst haben, wird das Adressbuch mit der restlichen Topologie migriert.</span><span class="sxs-lookup"><span data-stu-id="9cadf-125">If you did not customize normalization rules, Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="9cadf-126">Ausführliche Informationen über die manuelle Migration benutzerdefinierter Normalisierungsregeln finden Sie unter [Migrate Address Book](migrate-address-book.md).</span><span class="sxs-lookup"><span data-stu-id="9cadf-126">For details about manually migrating customized normalization rules, see [Migrate Address Book](migrate-address-book.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

