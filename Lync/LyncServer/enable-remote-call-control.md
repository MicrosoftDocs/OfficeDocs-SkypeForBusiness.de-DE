---
title: Aktivieren der Remoteanrufsteuerung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 310a140d3497a77ddcaeb8ba32403aa8f28b68e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a><span data-ttu-id="b0177-102">Aktivieren der Remoteanrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="b0177-102">Enable remote call control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0177-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b0177-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b0177-104">Die Remote Anrufsteuerung ermöglicht Benutzern, Ihre Desktop-PBX-Telefone (Private Branch Exchange) mithilfe von lync Server 2013 zu steuern.</span><span class="sxs-lookup"><span data-stu-id="b0177-104">Remote call control enables users to control their desktop private branch exchange (PBX) phones by using Lync Server 2013.</span></span> <span data-ttu-id="b0177-105">Wenn Sie die Remoteanrufsteuerung in ihrer Legacyumgebung bereitgestellt haben und lync Server 2013 migrieren möchten, müssen Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="b0177-105">If you deployed remote call control in your legacy environment and want to migrate it Lync Server 2013, you need to perform the following tasks:</span></span>

1.  <span data-ttu-id="b0177-106">Installieren Sie ein SIP/CSTA-Gateway, und konfigurieren Sie es für die Kommunikation mit Ihrer Telefonanlage.</span><span class="sxs-lookup"><span data-stu-id="b0177-106">Install a SIP/CSTA gateway and configure it to communicate with your PBX.</span></span> <span data-ttu-id="b0177-107">Sie müssen diesen Schritt ausführen, wenn Sie den lync Server 2013-Pilot Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b0177-107">You need to do this step when you deploy your Lync Server 2013 pilot pool.</span></span>

2.  <span data-ttu-id="b0177-108">Nachdem Sie Ihre Topologie zusammengeführt und ihre Richtlinien und Einstellungen migriert haben, konfigurieren Sie lync Server 2013 so, dass CSTA-Anforderungen an das SIP/CSTA-Gateway weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b0177-108">After you merge your topology and migrate your policies and settings, configure Lync Server 2013 to route CSTA requests to the SIP/CSTA gateway.</span></span> <span data-ttu-id="b0177-109">Dieser Schritt ist ein manueller Schritt, der der automatisierten Migration folgt.</span><span class="sxs-lookup"><span data-stu-id="b0177-109">This step is a manual step that follows the automated migration.</span></span> <span data-ttu-id="b0177-110">Gehen Sie wie folgt vor, um Routing für CSTA-Anforderungen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="b0177-110">To configure routing for CSTA requests, do the following:</span></span>
    
      - <span data-ttu-id="b0177-111">Entfernen Sie Legacy Authorized Host-Einträge (so genannte *Trusted Server-Einträge* in lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="b0177-111">Remove legacy authorized host entries (known as *trusted server entries* in Lync Server 2013).</span></span> <span data-ttu-id="b0177-112">Wenn Sie Benutzer aus Ihrer Legacy Bereitstellung migrieren, müssen Sie sicherstellen, dass Sie alle vorhandenen autorisierten Hosteinträge entfernen, die Sie für das SIP/CSTA-Gateway erstellt haben, bevor Sie neue Einträge für vertrauenswürdige Anwendungen im lync Server 2013-Pilot Pool konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b0177-112">If you are migrating users from your legacy deployment, ensure that you remove all existing authorized host entries that you created for the SIP/CSTA gateway before you configure new trusted application entries on the Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="b0177-113">Details zum Entfernen von Legacy autorisierten Hosteinträgen finden Sie unter [Entfernen eines autorisierten Hosteintrags](remove-an-authorized-host-entry.md).</span><span class="sxs-lookup"><span data-stu-id="b0177-113">For details about how to remove legacy authorized host entries, see [Remove an authorized host entry](remove-an-authorized-host-entry.md).</span></span>
    
      - <span data-ttu-id="b0177-114">Konfigurieren Sie eine statische Route für die Remoteanrufsteuerung.</span><span class="sxs-lookup"><span data-stu-id="b0177-114">Configure a static route for remote call control.</span></span> <span data-ttu-id="b0177-115">Sie können eine statische Route für einzelne Pools konfigurieren, die die Remoteanrufsteuerung unterstützen sollen, oder Sie können eine globale statische Route so konfigurieren, dass jeder Pool, der nicht mit einer statischen Route auf Poolebene konfiguriert ist, die globale statische Route verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0177-115">You can configure a static route for individual pools that you want to support remote call control, or you can configure a global static route so that each pool that is not configured with a pool-level static route uses the global static route.</span></span> <span data-ttu-id="b0177-116">Details zum Konfigurieren der statischen Route finden Sie unter [Konfigurieren einer statischen Route für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b0177-116">For details about how to configure the static route, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="b0177-117">Konfigurieren Sie einen Eintrag für die vertrauenswürdige Anwendung für die Remoteanrufsteuerung in jedem Pool, für den Sie die Remoteanrufsteuerung unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="b0177-117">Configure a trusted application entry for remote call control on each pool for which you want to support remote call control.</span></span> <span data-ttu-id="b0177-118">Details zum Konfigurieren eines Eintrags für vertrauenswürdige Anwendungen finden Sie unter [Konfigurieren eines Eintrags für eine vertrauenswürdige Anwendung für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b0177-118">For details about how to configure a trusted application entry, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="b0177-119">Wenn Sie ein SIP/CSTA-Gateway bereitgestellt haben, das Transmission Control Protocol (TCP) zum Herstellen einer Verbindung mit lync Server 2013 verwendet, definieren Sie die IP-Adresse des Gateways im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="b0177-119">If you deployed a SIP/CSTA gateway that uses Transmission Control Protocol (TCP) to connect to Lync Server 2013, define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="b0177-120">Details zum Definieren der IP-Adresse finden Sie unter [Definieren einer SIP/CSTA-Gateway-IP-Adresse in lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b0177-120">For details about defining the IP address, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in the Deployment documentation.</span></span>

4.  <span data-ttu-id="b0177-121">Konfigurieren Sie lync 2013-Benutzer für die Remoteanrufsteuerung, indem Sie die Remoteanrufsteuerung aktivieren und einen URI (Uniform Resource Identifier) und einen Leitungs-URI zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b0177-121">Configure Lync 2013 users for remote call control by enabling remote call control and assigning a line server Uniform Resource Identifier (URI) and a line URI.</span></span> <span data-ttu-id="b0177-122">Wenn Sie Benutzer aus Ihrer Legacy Bereitstellung zu lync Server 2013 migrieren, werden die Einstellungen für die Remoteanrufsteuerung zusammen mit den anderen Benutzereinstellungen migriert.</span><span class="sxs-lookup"><span data-stu-id="b0177-122">When you migrate users from your legacy deployment to Lync Server 2013, the remote call control settings are migrated along with the other user settings.</span></span>

5.  <span data-ttu-id="b0177-123">Wenn Sie die Normalisierungsregeln für Adressbuch-Telefonnummern in Ihrer Legacy Bereitstellung angepasst haben, müssen Sie nach Abschluss der automatisierten Migration von Richtlinien und Einstellungen einige manuelle Aufgaben ausführen, um die angepassten Normalisierungsregeln zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="b0177-123">If you customized Address Book phone number normalization rules in your legacy deployment, you need to perform some manual tasks after the automated migration of policies and settings is complete to migrate the customized normalization rules.</span></span> <span data-ttu-id="b0177-124">Wenn Sie die Normalisierungsregeln nicht angepasst haben, wird das Adressbuch zusammen mit der restlichen Topologie migriert.</span><span class="sxs-lookup"><span data-stu-id="b0177-124">If you did not customize normalization rules, Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="b0177-125">Details zum manuellen Migrieren von benutzerdefinierten Normalisierungsregeln finden Sie unter [Migrieren des Adressbuchs](migrate-address-book_1.md).</span><span class="sxs-lookup"><span data-stu-id="b0177-125">For details about manually migrating customized normalization rules, see [Migrate Address Book](migrate-address-book_1.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

