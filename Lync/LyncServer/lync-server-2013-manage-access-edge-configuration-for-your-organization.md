---
title: 'Lync Server 2013: Verwalten der Zugriffs-Edge-Konfiguration für Ihre Organisation'
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
ms.openlocfilehash: e54e74df2b965be3445b28dd5ca53a708a548c77
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a><span data-ttu-id="b938f-102">Verwalten der Zugriffs-Edge-Konfiguration für Ihre Organisation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b938f-102">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b938f-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b938f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b938f-104">Dies ist eine vorläufige Dokumentation und kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b938f-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="b938f-105">Leere Themen wurden als Platzhalter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b938f-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="b938f-106">Nachdem Sie einen oder mehrere Edgeserver bereitgestellt haben, müssen Sie die Typen des externen Domänen-oder Anbieter Zugriffs, den Remotebenutzerzugriff und den anonymen Benutzer Zugriff auf Konferenzen über die Edgeserver aktivieren, die für Ihre Organisation unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="b938f-106">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="b938f-107">Zu diesen Optionen gehören die folgenden Zugriffsarten, die auf der Seite **Zugriffs-Edgekonfiguration** konfiguriert werden können:</span><span class="sxs-lookup"><span data-stu-id="b938f-107">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="b938f-108">**Enable Federation and Public Chat Connectivity**   aktivieren Sie diese Option, wenn Sie den Benutzer Zugriff auf Verbundpartner Domänen unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="b938f-108">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="b938f-109">Diese Einstellung gilt gleichermaßen für SIP- und XMPP-Partnerverbunde, die auf der Seite **Externe Zugriffsrichtlinie** für die Bereiche "Global", "Standort" oder "Benutzer" konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="b938f-109">This setting applies to both SIP federation and XMPP federation that are configured for global, site or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="b938f-110">Damit die Partnerverbundeinstellungen gelten, müssen Sie die Partnerverbundunterstützung auf beiden Seiten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b938f-110">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="b938f-111">Es sind zwei Optionen vorhanden, bei denen es sich um optionale Einstellungen zur Erkennung von Verbundpartnern handelt. Damit wird auch festgelegt, ob Archivierungshaftungsausschlüsse (Benachrichtigung an Verbundkontakte, mit denen Sie kommunizieren, dass für Ihre Bereitstellung die Archivierung aktiviert ist und dass Kommunikationsdetails archiviert werden) an Kontakte gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="b938f-111">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts</span></span>
    
      - <span data-ttu-id="b938f-112">**Partnerdomänen Ermittlung**   aktivieren Wenn Sie diese Option auswählen, wird die automatische Erkennung von Domänen aktiviert, mit denen Sie eine Föderation durcharbeiten können.</span><span class="sxs-lookup"><span data-stu-id="b938f-112">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="b938f-113">Lync Server 2013 verwendet Domain Name System (DNS) Datensätze, um zu versuchen, Domänen zu ermitteln, die nicht in der Liste zugelassene Domänen aufgeführt sind, und den eingehenden Datenverkehr von erkannten Partner Partnern automatisch auswerten und den Datenverkehr basierend auf der Vertrauensebene einschränken oder blockieren Umfang des Datenverkehrs und Administratoreinstellungen.</span><span class="sxs-lookup"><span data-stu-id="b938f-113">Lync Server 2013 uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="b938f-114">Wenn Sie diese Option nicht auswählen, wird der Verbundbenutzer Zugriff nur für Benutzer in den Domänen aktiviert, die Sie in die Liste zugelassene Domänen einschließen.</span><span class="sxs-lookup"><span data-stu-id="b938f-114">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="b938f-115">Unabhängig davon, ob Sie diese Option auswählen, können Sie angeben, dass einzelne Domänen blockiert oder zugelassen werden sollen, einschließlich der Einschränkung des Zugriffs auf bestimmte Server, auf denen die Zugriffs-Edgedienst in der Verbunddomäne aufgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b938f-115">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="b938f-116">Ausführliche Informationen finden Sie unter [Konfigurieren der Unterstützung für zugelassene externe Domänen in lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="b938f-116">For details, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>
    
      - <span data-ttu-id="b938f-117">**Archivierungs Disclaimer an Verbundpartner**   senden wenn Sie diese Option auswählen, wird das Senden einer Archivierungs haftungsaus Schluss Nachricht an Verbundpartner ermöglicht, die Ihnen mitteilen, dass Kommunikationsdetails aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="b938f-117">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="b938f-118">Wenn Sie die externe Kommunikation mit Verbundpartnerdomänen archivieren, sollten Sie die Benachrichtigung über den Archivierungshaftungsausschluss aktivieren, um die Partner über die Archivierung ihrer Nachrichten und Kommunikationsdetails durch Ihre Bereitstellung in Kenntnis zu setzen.</span><span class="sxs-lookup"><span data-stu-id="b938f-118">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="b938f-119">Ausführliche Informationen zur Archivierung finden Sie unter [Definieren der Anforderungen für die Archivierung in lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="b938f-119">For details on archiving, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span></span>

  - <span data-ttu-id="b938f-120">**Remotebenutzerzugriff**   aktivieren aktivieren Sie diese Option, wenn Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, wie etwa Telearbeiter und Benutzer, die unterwegs sind, eine Verbindung mit lync Server herstellen können sollen.</span><span class="sxs-lookup"><span data-stu-id="b938f-120">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server.</span></span> <span data-ttu-id="b938f-121">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="b938f-121">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="b938f-122">**Aktivieren anonymer Benutzer für den Zugriff auf Konferenzen**   aktivieren Sie diese Option, wenn interne Benutzer externe anonyme Benutzer zu Konferenzen einladen möchten, die Sie organisieren.</span><span class="sxs-lookup"><span data-stu-id="b938f-122">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="b938f-123">Wenn Sie diese Einstellung aktivieren, sind nur anonyme Benutzer für Konferenzen zugelassen.</span><span class="sxs-lookup"><span data-stu-id="b938f-123">Enabling this setting only allows anonymous users for conferences.</span></span> <span data-ttu-id="b938f-124">Informationen zum Konfigurieren der Konferenzfunktionen und-Optionen, die definieren, wie und was Ihre Benutzer mit Konferenzen und für die Einbindung anonymer Benutzer tun können, finden Sie unter Details unter [Create or Modify Conferencing User Experience for a Site or users](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) and [Conferencing Policy Settings Reference for lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="b938f-124">To configure the conferencing experience and options that will define how and what your users can do with conferences and for the inclusion of anonymous users, see details at [Create or Modify Conferencing User Experience for a Site or Users](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b938f-125">Zusätzlich zur Unterstützung des Zugriffs externer Benutzer können Sie auch Richtlinien konfigurieren, mit denen die Verwendung des Remotebenutzerzugriffs in Ihrer Organisation gesteuert wird, bevor Benutzer den Zugriff für externe Benutzer verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b938f-125">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="b938f-126">Ausführliche Informationen zum Erstellen, konfigurieren und Anwenden von Richtlinien für den Zugriff durch externe Benutzer finden Sie unter <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage External Access Policy in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b938f-126">For details about creating, configuring, and applying policies for external user access, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b938f-127">**Anzeigen von Informationen zur Zugriffs-Edge-Konfiguration mithilfe von Windows PowerShell-Cmdlets**</span><span class="sxs-lookup"><span data-stu-id="b938f-127">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="b938f-128">Informationen zur Zugriffs-Edge-Konfiguration können mit Windows PowerShell und dem Cmdlet **Get-csaccessedgeconfiguration nicht angeben** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b938f-128">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="b938f-129">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b938f-129">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b938f-130">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="b938f-130">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="b938f-131">Geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE, um Informationen zu allen Einstellungen für die Zugriffs-Edge-Konfiguration anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="b938f-131">To view information about all your Access Edge configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsAccessEdgeConfiguration
    
    <span data-ttu-id="b938f-132">Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:</span><span class="sxs-lookup"><span data-stu-id="b938f-132">That will return information similar to this:</span></span>
    
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

## <a name="in-this-section"></a><span data-ttu-id="b938f-133">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b938f-133">In This Section</span></span>

  - [<span data-ttu-id="b938f-134">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b938f-134">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [<span data-ttu-id="b938f-135">Aktivieren oder Deaktivieren der Ermittlung von Partnerverbund Partnern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b938f-135">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [<span data-ttu-id="b938f-136">Aktivieren oder Deaktivieren des Sendens von Archivierungs Haftungsausschlüssen an Verbundpartner in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b938f-136">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="b938f-137">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b938f-137">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="b938f-138">Aktivieren oder Deaktivieren des Zugriffs anonymer Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b938f-138">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="b938f-139">Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b938f-139">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

