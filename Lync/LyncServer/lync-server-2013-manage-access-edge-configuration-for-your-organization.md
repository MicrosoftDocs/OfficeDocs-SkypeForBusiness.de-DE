---
title: 'Lync Server 2013: Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4739599f92b9189a208e1bb320a53b82d66a3a9c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a><span data-ttu-id="ede52-102">Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ede52-102">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ede52-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ede52-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ede52-104">Diese Dokumentation ist vorläufig und kann geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ede52-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="ede52-105">Leere Themen sind als Platzhalter enthalten.</span><span class="sxs-lookup"><span data-stu-id="ede52-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="ede52-106">Nachdem Sie einen oder mehrere Edgeserver bereitgestellt haben, müssen Sie die Typen des externen Domänen-oder Anbieter Zugriffs, den Remotebenutzerzugriff und den anonymen Benutzer Zugriff auf Konferenzen über die Edgeserver aktivieren, die für Ihre Organisation unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="ede52-106">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="ede52-107">Zu diesen Optionen gehören die folgenden Zugriffsarten, die über die Seite " **Zugriffs-Edge-Konfiguration** " konfiguriert werden können:</span><span class="sxs-lookup"><span data-stu-id="ede52-107">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="ede52-108">**Aktivieren von Föderations-und öffentlichen Chat Verbindungen**   aktivieren Sie diese Option, wenn Sie den Benutzer Zugriff auf Partnerdomänen für Föderationen unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="ede52-108">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="ede52-109">Diese Einstellung gilt für SIP-Föderations-und XMPP-Föderationen, die für globale, Website-oder benutzerbereiche auf der Seite " **externe Zugriffsrichtlinie** " konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="ede52-109">This setting applies to both SIP federation and XMPP federation that are configured for global, site or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="ede52-110">Damit die Verbund Einstellungen angewendet werden, müssen Sie die Verbundunterstützung auf beiden Seiten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ede52-110">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="ede52-111">Es gibt zwei Optionen, die optionale Einstellungen für die Erkennung von Verbundpartnern sind, und ob Archivierungs verzichte (Benachrichtigung an verbundene Kontakte, mit denen Sie kommunizieren, dass Ihre Bereitstellung die Archivierung aktiviert hat und dass die Kommunikation Details werden archiviert) werden an Kontakte gesendet</span><span class="sxs-lookup"><span data-stu-id="ede52-111">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts</span></span>
    
      - <span data-ttu-id="ede52-112">**Aktivieren der Partnerdomänen Ermittlung**   durch Auswahl dieser Option wird die automatische Ermittlung von Domänen ermöglicht, mit denen Sie eine Föderation durchsetzen können.</span><span class="sxs-lookup"><span data-stu-id="ede52-112">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="ede52-113">Lync Server 2013 verwendet DNS-Einträge (Domain Name System), um zu versuchen, Domänen zu finden, die nicht in der Liste der zulässigen Domänen aufgeführt sind, den eingehenden Datenverkehr von ermittelten Partner Partnern automatisch auswerten und den Datenverkehr basierend auf der Vertrauensstufe einschränken oder blockieren. die Anzahl der Datenverkehr und die Administratoreinstellungen.</span><span class="sxs-lookup"><span data-stu-id="ede52-113">Lync Server 2013 uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="ede52-114">Wenn Sie diese Option nicht auswählen, wird der Verbundbenutzer Zugriff nur für Benutzer in den Domänen aktiviert, die Sie in die Liste zugelassene Domänen aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="ede52-114">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="ede52-115">Unabhängig davon, ob Sie diese Option auswählen, können Sie angeben, dass einzelne Domänen blockiert oder zulässig sein sollen, einschließlich der Beschränkung des Zugriffs auf bestimmte Server, auf denen der Access-Edgedienst in der Verbunddomäne ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ede52-115">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="ede52-116">Ausführliche Informationen finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen in lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="ede52-116">For details, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>
    
      - <span data-ttu-id="ede52-117">**Archivierungs Ausschluss an verbundene Partner**   senden wenn Sie diese Option aktivieren, können Sie eine Nachricht zur Archivierung des Disclaimers an verbundene Partner senden, die Ihnen mitteilt, dass Kommunikationsdetails aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="ede52-117">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="ede52-118">Wenn Sie die externe Kommunikation mit Verbundpartner Domänen archivieren, sollten Sie die Benachrichtigung über Archivierungs Verzicht aktivieren, um die Partner zu warnen, dass Ihre Nachrichten und Kommunikationsdetails von Ihrer Bereitstellung archiviert werden.</span><span class="sxs-lookup"><span data-stu-id="ede52-118">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="ede52-119">Details zur Archivierung finden Sie unter [Definieren Ihrer Anforderungen für die Archivierung in lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="ede52-119">For details on archiving, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span></span>

  - <span data-ttu-id="ede52-120">**Aktivieren des Remotebenutzerzugriffs**   aktivieren Sie diese Option, wenn Sie möchten, dass Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, wie Telecommuter und Benutzer, die unterwegs sind, eine Verbindung mit lync Server herstellen können.</span><span class="sxs-lookup"><span data-stu-id="ede52-120">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server.</span></span> <span data-ttu-id="ede52-121">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="ede52-121">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="ede52-122">**Aktivieren von anonymen Benutzern für den Zugriff auf Konferenzen**   aktivieren Sie diese Option, wenn interne Benutzer externe anonyme Benutzer zu Konferenzen einladen möchten, die Sie organisieren.</span><span class="sxs-lookup"><span data-stu-id="ede52-122">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="ede52-123">Wenn Sie diese Einstellung aktivieren, können anonyme Benutzer nur für Konferenzen zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="ede52-123">Enabling this setting only allows anonymous users for conferences.</span></span> <span data-ttu-id="ede52-124">Informationen zum Konfigurieren der Konferenzumgebung und der Optionen, die definieren, wie und was Ihre Benutzer mit Konferenzen und für die Einbeziehung anonymer Benutzer tun können, finden Sie unter Details unter [erstellen oder Ändern von Konferenzbenutzer Oberflächen für eine Website oder Benutzer](https://technet.microsoft.com/en-us/library/gg429715\(v=ocs.15\)) und [Konferenzrichtlinien Einstellungsreferenz für lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="ede52-124">To configure the conferencing experience and options that will define how and what your users can do with conferences and for the inclusion of anonymous users, see details at [Create or Modify Conferencing User Experience for a Site or Users](https://technet.microsoft.com/en-us/library/gg429715\(v=ocs.15\)) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ede52-125">Neben der Unterstützung für den Zugriff durch externe Benutzer können Sie auch Richtlinien konfigurieren, um die Verwendung des Remotebenutzerzugriffs in Ihrer Organisation zu steuern, bevor Benutzer Zugriff auf externe Benutzer erhalten.</span><span class="sxs-lookup"><span data-stu-id="ede52-125">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="ede52-126">Details zum Erstellen, konfigurieren und Anwenden von Richtlinien für den Zugriff durch externe Benutzer finden Sie unter Verwalten von Richtlinien für den <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">externen Zugriff in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ede52-126">For details about creating, configuring, and applying policies for external user access, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="ede52-127">**Anzeigen von Informationen zur Access-Edge-Konfiguration mithilfe von Windows PowerShell-Cmdlets**</span><span class="sxs-lookup"><span data-stu-id="ede52-127">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="ede52-128">Informationen zur Access-Edge-Konfiguration können mithilfe von Windows PowerShell und dem Cmdlet **Get-csaccessedgeconfiguration nicht angeben** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ede52-128">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="ede52-129">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ede52-129">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ede52-130">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="ede52-130">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="ede52-131">Wenn Sie Informationen zu allen Einstellungen für die Zugriffs-Edge-Konfiguration anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="ede52-131">To view information about all your Access Edge configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsAccessEdgeConfiguration
    
    <span data-ttu-id="ede52-132">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="ede52-132">That will return information similar to this:</span></span>
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

<div>

## <a name="in-this-section"></a><span data-ttu-id="ede52-133">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ede52-133">In This Section</span></span>

  - [<span data-ttu-id="ede52-134">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ede52-134">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [<span data-ttu-id="ede52-135">Aktivieren oder Deaktivieren der Suche von Verbundpartnern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ede52-135">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [<span data-ttu-id="ede52-136">Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ede52-136">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="ede52-137">Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ede52-137">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="ede52-138">Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ede52-138">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="ede52-139">Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ede52-139">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

