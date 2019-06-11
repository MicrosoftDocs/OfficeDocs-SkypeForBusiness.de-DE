---
title: 'Lync Server 2013: Bereitstellen der Remoteanrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying remote call control
ms:assetid: 763037f7-7a2a-49ae-acc3-9781b0bff7e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558664(v=OCS.15)
ms:contentKeyID: 48184536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8583a8f2e8c95ce9b12ad19d8a8e5369ba756ddd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="b7a6a-102">Bereitstellen der Remoteanrufsteuerung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7a6a-102">Deploying remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7a6a-103">_**Letztes Änderungsdatum des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b7a6a-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b7a6a-104">Dieser Abschnitt führt Sie durch den Prozess der Bereitstellung von Funktionen für die Remoteanrufsteuerung für Benutzer in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="b7a6a-104">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7a6a-105">Obwohl Remote-Anrufsteuerungsfeatures für Remotebenutzer verfügbar sind, während Sie sich außerhalb der Firewall Ihrer Organisation befinden, gehen Details zum Bereitstellen von externen Zugriffsszenarien nicht in diesen Dokumentationsbereich ein.</span><span class="sxs-lookup"><span data-stu-id="b7a6a-105">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="b7a6a-106">Details zum Bereitstellen des Zugriffs externer Benutzer finden Sie unter <A href="lync-server-2013-deploying-external-user-access.md">Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b7a6a-106">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b7a6a-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b7a6a-107">In This Section</span></span>

  - [<span data-ttu-id="b7a6a-108">Konfigurieren von Lync Server 2013 für das Routing an ein SIP/CSTA-Gateway</span><span class="sxs-lookup"><span data-stu-id="b7a6a-108">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="b7a6a-109">Konfigurieren einer statischen Route für die Remoteanrufsteuerung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7a6a-109">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="b7a6a-110">Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7a6a-110">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="b7a6a-111">[Definieren einer SIP/CSTA-Gateway-IP-Adresse in lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (nur, wenn das Gateway für die Verwendung von TCP konfiguriert ist)</span><span class="sxs-lookup"><span data-stu-id="b7a6a-111">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="b7a6a-112">Aktivieren von Lync-Benutzern für die Remoteanrufsteuerung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7a6a-112">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="b7a6a-113">Remoteanrufsteuerung und Normalisieren von Rufnummern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7a6a-113">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="b7a6a-114">[Entfernen eines autorisierten Legacyhosts in lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (nur wenn Sie Benutzer migrieren, die zuvor für die Remoteanrufsteuerung aktiviert wurden)</span><span class="sxs-lookup"><span data-stu-id="b7a6a-114">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="b7a6a-115">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b7a6a-115">Related Sections</span></span>

[<span data-ttu-id="b7a6a-116">Planen der Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7a6a-116">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

