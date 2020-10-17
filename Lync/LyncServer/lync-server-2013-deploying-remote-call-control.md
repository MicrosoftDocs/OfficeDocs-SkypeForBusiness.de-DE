---
title: 'Lync Server 2013: Bereitstellen der Remoteanrufsteuerung'
description: 'Lync Server 2013: Bereitstellen der Remoteanrufsteuerung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying remote call control
ms:assetid: 763037f7-7a2a-49ae-acc3-9781b0bff7e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558664(v=OCS.15)
ms:contentKeyID: 48184536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cc5e79f3ee44c354baf435585d304574d6a980c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566081"
---
# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="45ef0-103">Bereitstellen der Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45ef0-103">Deploying remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45ef0-104">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="45ef0-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="45ef0-105">In diesem Abschnitt werden Sie durch die Schritte zur Bereitstellung der Remoteanrufsteuerung für Benutzer in Ihrer Organisation geleitet.</span><span class="sxs-lookup"><span data-stu-id="45ef0-105">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="45ef0-106">Wenngleich Remoteanrufsteuerungs-Funktionen für Remotebenutzer verfügbar sind, die sich außerhalb der Firewall Ihrer Organisation befinden, können im Rahmen dieser Dokumentation keine Einzelheiten zu Szenarien mit Zugriff durch externe Benutzer bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="45ef0-106">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="45ef0-107">Ausführliche Informationen zum Bereitstellen des Zugriffs durch externe Benutzer finden Sie unter <A href="lync-server-2013-deploying-external-user-access.md">Deploying External User Access in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="45ef0-107">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="45ef0-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="45ef0-108">In This Section</span></span>

  - [<span data-ttu-id="45ef0-109">Konfigurieren lync Server 2013 für die Weiterleitung an ein SIP/CSTA-Gateway</span><span class="sxs-lookup"><span data-stu-id="45ef0-109">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="45ef0-110">Konfigurieren einer statischen Route für die Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45ef0-110">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="45ef0-111">Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45ef0-111">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="45ef0-112">[Definieren einer IP-Adresse für SIP/CSTA-Gateways in lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (nur, wenn das Gateway für die Verwendung von TCP konfiguriert ist)</span><span class="sxs-lookup"><span data-stu-id="45ef0-112">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="45ef0-113">Aktivieren von lync-Benutzern für die Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45ef0-113">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="45ef0-114">Remote Anrufsteuerung und Telefonnummernnormalisierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45ef0-114">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="45ef0-115">[Entfernen eines autorisierten Legacyhosts in lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (nur, wenn Sie Benutzer migrieren, die zuvor für die Remoteanrufsteuerung aktiviert wurden)</span><span class="sxs-lookup"><span data-stu-id="45ef0-115">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="45ef0-116">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="45ef0-116">Related Sections</span></span>

[<span data-ttu-id="45ef0-117">Planen der Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45ef0-117">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

