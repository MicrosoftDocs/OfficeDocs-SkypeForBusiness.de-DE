---
title: 'Lync Server 2013: Konfigurieren der Unterstützung für blockierte externe Domänen'
description: 'Lync Server 2013: Konfigurieren der Unterstützung für blockierte externe Domänen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81c2c76dc32dd5e8d458dad4e91ff375d2ab005c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576681"
---
# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a><span data-ttu-id="ebd40-103">Konfigurieren der Unterstützung für blockierte externe Domänen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebd40-103">Configure support for blocked external domains in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebd40-104">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ebd40-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ebd40-105">Wenn Sie die Unterstützung für Verbundpartner konfiguriert haben, können Sie verwalten, welche Domänen für die Zusammenführung mit Ihrer Organisation blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="ebd40-105">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="ebd40-106">Die Liste der blockierten Domänen fungiert als Sperrliste (Auflistung expliziter Einträge, die nicht zulässig sind) und wird bei der Ermittlung der Verbunddomäne angewendet, wenn diese Option aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ebd40-106">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="ebd40-107">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern in lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span><span class="sxs-lookup"><span data-stu-id="ebd40-107">For details, see [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="ebd40-p102">Blockieren Sie eine oder mehrere externe Domänen vom Herstellen einer Verbindung mit Ihrer Organisation. Fügen Sie hierzu die Domäne der Liste blockierter Domänen hinzu.</span><span class="sxs-lookup"><span data-stu-id="ebd40-p102">Block one or more external domains from connecting to your organization. To do this, add the domain to the list of blocked domains.</span></span>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="ebd40-110">So fügen Sie der Liste blockierter Domänen eine externe Domäne hinzu</span><span class="sxs-lookup"><span data-stu-id="ebd40-110">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="ebd40-111">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="ebd40-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ebd40-112">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ebd40-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ebd40-113">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ebd40-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ebd40-114">Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="ebd40-114">In the left navigation bar, click **External User Access**.</span></span>

4.  <span data-ttu-id="ebd40-115">Klicken Sie auf **Partnerdomänen**, auf **Neu** und dann auf **Blockierte Domäne**.</span><span class="sxs-lookup"><span data-stu-id="ebd40-115">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>

5.  <span data-ttu-id="ebd40-116">Führen Sie unter **Neue Partnerdomänen** die folgende Aktion aus:</span><span class="sxs-lookup"><span data-stu-id="ebd40-116">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="ebd40-117">Geben Sie im Feld **Domänenname (oder FQDN)** den Namen der Verbundpartnerdomäne ein, die blockiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ebd40-117">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ebd40-118">Der Name darf maximal 256 Zeichen umfassen.</span><span class="sxs-lookup"><span data-stu-id="ebd40-118">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="ebd40-p104">Bei der Suche nach dem Namen der Verbundpartnerdomäne wird ein Suffixabgleich durchgeführt. Wenn Sie beispielsweise <STRONG>contoso.com</STRONG> eingeben, wird als Suchergebnis auch die Domäne <STRONG>it.contoso.com</STRONG> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ebd40-p104">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="ebd40-121">Eine Verbundpartnerdomäne kann nicht gleichzeitig blockiert und zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="ebd40-121">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="ebd40-122">Lync Server 2013 verhindert, dass dies geschieht, damit Sie Ihre Listen nicht synchronisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="ebd40-122">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="ebd40-123">Im Feld **Kommentar** können Sie Informationen zur Konfiguration eingeben, die Sie mit anderen Systemadministratoren teilen möchten. Dieses Feld ist optional.</span><span class="sxs-lookup"><span data-stu-id="ebd40-123">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="ebd40-124">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="ebd40-124">Click **Commit**.</span></span>

7.  <span data-ttu-id="ebd40-125">Wiederholen Sie die Schritte 4 bis 6 für jeden Verbundpartner, den Sie blockieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ebd40-125">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="ebd40-126">Um den Zugriff durch Partnerbenutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Partnerbenutzerzugriff in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ebd40-126">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="ebd40-127">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="ebd40-127">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="ebd40-128">Zusätzlich müssen Sie die Richtlinie konfigurieren und auf Benutzer anwenden, die mit Partnerbenutzern zusammenarbeiten sollen.</span><span class="sxs-lookup"><span data-stu-id="ebd40-128">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="ebd40-129">Ausführliche Informationen finden Sie unter [configure Policies to Control Federated User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="ebd40-129">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

