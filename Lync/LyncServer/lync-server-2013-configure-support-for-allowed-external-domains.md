---
title: 'Lync Server 2013: Konfigurieren der Unterstützung für zugelassene externe Domänen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eaa9da579561464c46776662cacaca80dafe016
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517682"
---
# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a><span data-ttu-id="f1a09-102">Konfigurieren der Unterstützung für zugelassene externe Domänen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1a09-102">Configure support for allowed external domains in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1a09-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f1a09-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f1a09-p101">Wenn Sie die Unterstützung für Verbundpartner konfiguriert haben, können Sie verwalten, welche spezifischen Domänen einen Partnerverbund mit Ihrer Organisation eingehen können. Konfigurieren Sie eine oder mehrere spezifische externe Domänen als zulässige Partnerdomänen. Fügen Sie hierzu jede Domäne der Liste zulässiger Domänen hinzu. Selbst wenn die Suche von Verbundpartnern für Ihre Organisation aktiviert ist, führen Sie diesen Schritt aus, wenn es sich bei der Domäne um einen Verbundpartner handelt, der mit mehr als 1.000 Ihrer Benutzer kommunizieren oder mehr als 20 Nachrichten pro Sekunde senden muss. Ist die Suche von Verbundpartnern für Ihre Organisation nicht aktiviert, können nur Benutzer aus externen Domänen am Instant Messaging und an Konferenzen mit Benutzern Ihrer Organisation teilnehmen, die Sie der Liste zulässiger Domänen hinzugefügt haben. Wenn Sie den Zugriff einer Partnerdomäne auf einen bestimmten Server beschränken möchten, auf dem der Zugriffs-Edgedienst des Verbundpartners ausgeführt wird, können Sie für jede Domäne in der Liste zulässiger Domänen den Domänennamen des Servers angeben, auf dem der Zugriffs-Edgedienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f1a09-p101">If you have configured support for federated partners, you can manage which specific domains can federate with your organization. You configure one or more specific external domains as allowed federated domains. To do this, add each domain to the list of allowed domains. Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second. If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization. If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1a09-110">In diesem Verfahren wird beschrieben, wie Sie die Unterstützung für bestimmte Domänen konfigurieren, aber das Implementieren der Unterstützung für Partnerverbund Benutzer erfordert auch, dass Sie die Unterstützung für Partnerverbund Benutzer für Ihre Organisation aktivieren und Richtlinien konfigurieren und anwenden, um zu steuern, welche Benutzer mit Partnerverbund Benutzern zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="f1a09-110">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="f1a09-111">Ausführliche Informationen zum Aktivieren der Unterstützung für Partnerverbund Benutzer finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f1a09-111">For details about enabling support for federated users, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="f1a09-112">Ausführliche Informationen zum Konfigurieren von Richtlinien zur Steuerung des Verbunds finden Sie unter <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">configure Policies to Control Federated User Access in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f1a09-112">For details about configuring policies to control federation, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="f1a09-113">So fügen Sie eine externe Domäne der Liste zulässiger Domänen hinzu</span><span class="sxs-lookup"><span data-stu-id="f1a09-113">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="f1a09-114">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f1a09-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f1a09-115">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f1a09-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f1a09-116">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f1a09-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f1a09-117">Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Partnerdomänen**.</span><span class="sxs-lookup"><span data-stu-id="f1a09-117">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>

4.  <span data-ttu-id="f1a09-118">Klicken Sie auf der Seite **Partnerdomänen** auf **Neu** und anschließend auf **Zulässige Domäne**.</span><span class="sxs-lookup"><span data-stu-id="f1a09-118">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>

5.  <span data-ttu-id="f1a09-119">Führen Sie unter **Neue Partnerdomänen** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="f1a09-119">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="f1a09-120">Geben Sie unter **Domänenname (oder FQDN)** den Namen der Verbundpartnerdomäne ein.</span><span class="sxs-lookup"><span data-stu-id="f1a09-120">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f1a09-p104">Dieser Name muss eindeutig sein und darf noch nicht als zulässige Domäne für diesen Server vorliegen, auf dem der Zugriffs-Edgedienst ausgeführt wird. Der Name darf höchstens 256 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="f1a09-p104">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service. The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="f1a09-p105">Bei der Suche nach dem Namen der Verbundpartnerdomäne wird ein Suffixabgleich durchgeführt. Wenn Sie beispielsweise <STRONG>contoso.com</STRONG> eingeben, wird als Suchergebnis auch die Domäne <STRONG>it.contoso.com</STRONG> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f1a09-p105">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="f1a09-125">Eine Verbundpartnerdomäne kann nicht gleichzeitig blockiert und zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="f1a09-125">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="f1a09-126">Lync Server 2013 verhindert, dass dies geschieht, damit Sie Ihre Listen nicht synchronisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="f1a09-126">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="f1a09-127">Wenn Sie den Zugriff für diese Partnerdomäne auf Benutzer eines bestimmten Servers beschränken möchten, auf dem der Zugriffs-Edgedienst ausgeführt wird, geben Sie unter **Zugriffs-Edgedienst (FQDN)** den FQDN des Servers der Partnerdomäne ein, auf dem der Zugriffs-Edgedienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f1a09-127">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>
    
      - <span data-ttu-id="f1a09-128">Wenn Sie zusätzliche Informationen bereitstellen möchten, geben Sie unter **Kommentar** Informationen ein, die Sie anderen Systemadministratoren über diese Konfiguration mitteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="f1a09-128">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="f1a09-129">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f1a09-129">Click **Commit**.</span></span>

7.  <span data-ttu-id="f1a09-130">Wiederholen Sie die Schritte 4 bis 6 für jede Verbundpartnerdomäne, die Sie zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="f1a09-130">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="f1a09-131">Um den Zugriff durch Partnerbenutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Partnerbenutzerzugriff in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f1a09-131">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="f1a09-132">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f1a09-132">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="f1a09-133">Zusätzlich müssen Sie die Richtlinie konfigurieren und auf Benutzer anwenden, die mit Partnerbenutzern zusammenarbeiten sollen.</span><span class="sxs-lookup"><span data-stu-id="f1a09-133">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="f1a09-134">Ausführliche Informationen finden Sie unter [configure Policies to Control Federated User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f1a09-134">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

