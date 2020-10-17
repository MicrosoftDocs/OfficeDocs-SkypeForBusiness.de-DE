---
title: 'Lync Server 2013: Anzeigen des Status globaler Einstellungen für eine Gesamtstruktur'
description: 'Lync Server 2013: Anzeigen des Status globaler Einstellungen für eine Gesamtstruktur.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9f722ea66f6c54c816703bd1af1d3def57bbd84
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567591"
---
# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="9baf7-103">Anzeigen des Status globaler Einstellungen für eine Gesamtstruktur in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9baf7-103">View status of global settings for a forest in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9baf7-104">_**Letztes Änderungsstand des Themas:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="9baf7-104">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="9baf7-105">Administratoren sollten die globalen Einstellungen für eine lync Server 2013-Bereitstellung monatlich überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9baf7-105">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="9baf7-106">Das Ziel besteht darin, die implementierten Einstellungen anhand einer Reihe bekannter Konfigurationen zu überprüfen – einer Basiskonfiguration, um sicherzustellen, dass die Einstellungen gültig sind, und um zu ermitteln, ob die Basisdokumentation aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9baf7-106">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="9baf7-107">Änderungen an der globalen Einstellung sollten über einen Änderungssteuerungsprozess implementiert werden, der die Dokumentierung der neuen Einstellungen umfassen sollte.</span><span class="sxs-lookup"><span data-stu-id="9baf7-107">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="9baf7-108">Globale Einstellungen, die überprüft werden sollten, werden in den folgenden Abschnitten beschrieben:</span><span class="sxs-lookup"><span data-stu-id="9baf7-108">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="9baf7-109">Allgemeine Einstellungen überprüfen</span><span class="sxs-lookup"><span data-stu-id="9baf7-109">Check general settings</span></span>

<span data-ttu-id="9baf7-110">Überprüfen Sie die allgemeinen Einstellungen, einschließlich der unterstützten SIP-Domänen (Session Initiation Protocol) für lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9baf7-110">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="9baf7-111">SIP-Domäneninformationen können mit Windows PowerShell und dem Cmdlet **Get-CsSipDomain** zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9baf7-111">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="9baf7-112">Führen Sie den Befehl Windows PowerShell aus, um diese Informationen zurückzugeben `Get-CsSipDomain` .</span><span class="sxs-lookup"><span data-stu-id="9baf7-112">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="9baf7-113">In Get-CsSipDomain werden für alle autorisierten SIP-Domänen ähnliche Informationen wie diese zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="9baf7-113">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="9baf7-114">Identitäts Name-IsDefault</span><span class="sxs-lookup"><span data-stu-id="9baf7-114">Identity Name IsDefault</span></span>

<span data-ttu-id="9baf7-115">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="9baf7-115">\-------- ---- ---------</span></span>

<span data-ttu-id="9baf7-116">fabrikam.com fabrikam.com true</span><span class="sxs-lookup"><span data-stu-id="9baf7-116">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="9baf7-117">na.fabrikam.com na.fabrikam.com false</span><span class="sxs-lookup"><span data-stu-id="9baf7-117">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="9baf7-118">Wenn die IsDefault-Eigenschaft auf true festgelegt ist, ist die entsprechende Domäne Ihre Standard-SIP-Domäne.</span><span class="sxs-lookup"><span data-stu-id="9baf7-118">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="9baf7-119">Sie können das Set-CsSipDomain-Cmdlet verwenden, um die Standard-SIP-Domäne für Ihre Organisation zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9baf7-119">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="9baf7-120">Allerdings können Sie die Standard-SIP-Domäne nicht einfach löschen, da Sie ohne Standarddomäne bleiben würde.</span><span class="sxs-lookup"><span data-stu-id="9baf7-120">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="9baf7-121">Wenn Sie die fabrikam.com-Domäne löschen wollten (wie im vorherigen Beispiel gezeigt), müssen Sie zunächst na.fabrikam.com so konfigurieren, dass Sie die Standarddomäne ist.</span><span class="sxs-lookup"><span data-stu-id="9baf7-121">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="9baf7-122">Überprüfen der Besprechungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="9baf7-122">Check meeting settings</span></span>

<span data-ttu-id="9baf7-123">Die Besprechungseinstellungen umfassen Richtlinien Definitionen für Besprechungen und Unterstützung für die Teilnahme anonymer Benutzer an Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="9baf7-123">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="9baf7-124">Die Besprechungs Konfigurationseinstellungen können mit Windows PowerShell und dem Cmdlet **Get-CsMeetingConfiguration** abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9baf7-124">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="9baf7-125">Mit diesem Befehl werden beispielsweise Informationen zu den globalen Besprechungs Konfigurationseinstellungen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="9baf7-125">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="9baf7-126">Get-CsMeetingConfiguration – Identity "globale" Besprechungs Konfigurationseinstellungen können auch auf Standortebene konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="9baf7-126">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="9baf7-127">Aus diesem Grund möchten Sie möglicherweise den folgenden Befehl verwenden, der Informationen zu allen Besprechungs Konfigurationseinstellungen zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="9baf7-127">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="9baf7-128">Mit dem Cmdlet **Get-CsMeetingConfiguration** werden Informationen wie die folgenden zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="9baf7-128">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="9baf7-129">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="9baf7-129">Identity : Global</span></span>

<span data-ttu-id="9baf7-130">PstnCallersBypassLobby: true</span><span class="sxs-lookup"><span data-stu-id="9baf7-130">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="9baf7-131">EnableAssignedConferenceType: true</span><span class="sxs-lookup"><span data-stu-id="9baf7-131">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="9baf7-132">DesignateAsPresenter: Unternehmen</span><span class="sxs-lookup"><span data-stu-id="9baf7-132">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="9baf7-133">AssignedConferenceTypeByDefault: true</span><span class="sxs-lookup"><span data-stu-id="9baf7-133">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="9baf7-134">AdmitAnonymousUsersByDefault: true</span><span class="sxs-lookup"><span data-stu-id="9baf7-134">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="9baf7-135">Das letzte Element in der Liste **AdmitAnonymousUsersByDefault**aktiviert oder deaktiviert die Möglichkeit anonymer Benutzer, an Besprechungen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="9baf7-135">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="9baf7-136">Bei der Überprüfung der Besprechungs Konfigurationseinstellungen ist es möglicherweise hilfreich, die aktuellen Einstellungen mit den Standard Entsprechungen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="9baf7-136">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="9baf7-137">Sie können die Standardeinstellungen für die besprechungskonfiguration anzeigen, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="9baf7-137">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="9baf7-138">Mit dem vorherigen Befehl wird eine nur im Arbeitsspeicher befindliche Instanz der globalen Besprechungs Konfigurationseinstellungen erstellt, eine Instanz, die den Standardwert für jede Eigenschaft verwendet.</span><span class="sxs-lookup"><span data-stu-id="9baf7-138">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="9baf7-139">Beim Ausführen des Befehls werden keine tatsächlichen Besprechungs Konfigurationseinstellungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="9baf7-139">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="9baf7-140">Allerdings werden alle standardmäßigen Eigenschaftswerte auf dem Bildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9baf7-140">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="9baf7-141">Überprüfen der Edgeserver und deren Einstellungen</span><span class="sxs-lookup"><span data-stu-id="9baf7-141">Check Edge Servers and their settings</span></span>

<span data-ttu-id="9baf7-142">Edgeserver Informationen können mithilfe von Windows PowerShell abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9baf7-142">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="9baf7-143">Dieser Befehl gibt Informationen zu allen für die Verwendung in Ihrer Organisation konfigurierten Edge-Servern zurück.</span><span class="sxs-lookup"><span data-stu-id="9baf7-143">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="9baf7-144">Die zurückgegebenen Informationen enthalten alle FQDN-und Porteinstellungen für jede Edgeserver:</span><span class="sxs-lookup"><span data-stu-id="9baf7-144">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="9baf7-145">Identity: EdgeServer: DC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9baf7-145">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="9baf7-146">Registrar: Registrar: LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9baf7-146">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="9baf7-147">AccessEdgeInternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="9baf7-147">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="9baf7-148">AccessEdgeExternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="9baf7-148">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="9baf7-149">AccessEdgeClientPort: 443</span><span class="sxs-lookup"><span data-stu-id="9baf7-149">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="9baf7-150">DataPsomServerPort: 8057</span><span class="sxs-lookup"><span data-stu-id="9baf7-150">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="9baf7-151">DataPsomClientPort: 444</span><span class="sxs-lookup"><span data-stu-id="9baf7-151">DataPsomClientPort : 444</span></span>

<span data-ttu-id="9baf7-152">MediaRelayAuthEdgePort: 5062</span><span class="sxs-lookup"><span data-stu-id="9baf7-152">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="9baf7-153">MediaRelayAuthInternalTurnTcpPort: 443</span><span class="sxs-lookup"><span data-stu-id="9baf7-153">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="9baf7-154">MediaRelayAuthExternalTurnTcpPort: 445</span><span class="sxs-lookup"><span data-stu-id="9baf7-154">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="9baf7-155">MediaRelayAuthInternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="9baf7-155">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="9baf7-156">MediaRelayAuthExternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="9baf7-156">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="9baf7-157">MediaCommunicationPortStart: 50000</span><span class="sxs-lookup"><span data-stu-id="9baf7-157">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="9baf7-158">MediaComunicationPortCount: 10000</span><span class="sxs-lookup"><span data-stu-id="9baf7-158">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="9baf7-159">AccessEdgeExternalFqdn: DC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9baf7-159">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="9baf7-160">DataEdgeExternalFqdn: DC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9baf7-160">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="9baf7-161">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="9baf7-161">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="9baf7-162">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="9baf7-162">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="9baf7-163">ExternalMrasFqdn: DC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9baf7-163">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="9baf7-164">DependentServiceList: {Registrar: LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="9baf7-164">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="9baf7-165">ConferencingServer: LYNC-SE. fabrikam</span><span class="sxs-lookup"><span data-stu-id="9baf7-165">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="9baf7-166">com, MediationServer: LYNC-SE.</span><span class="sxs-lookup"><span data-stu-id="9baf7-166">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="9baf7-167">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="9baf7-167">fabrikam.com}</span></span>

<span data-ttu-id="9baf7-168">Dienst-Nr: fabrikam.com-EdgeServer-2</span><span class="sxs-lookup"><span data-stu-id="9baf7-168">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="9baf7-169">Website-Nr: Website-:fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="9baf7-169">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="9baf7-170">Poolfqdn ": DC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9baf7-170">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="9baf7-171">Version: 5</span><span class="sxs-lookup"><span data-stu-id="9baf7-171">Version : 5</span></span>

<span data-ttu-id="9baf7-172">Rolle: EdgeServer</span><span class="sxs-lookup"><span data-stu-id="9baf7-172">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="9baf7-173">Überprüfen der Verbund Einstellungen</span><span class="sxs-lookup"><span data-stu-id="9baf7-173">Check federation settings</span></span>

<span data-ttu-id="9baf7-174">Überprüfen Sie die Verbund Einstellungen, beispielsweise ob Sie konfiguriert ist, und, wenn die Antwort "Ja" lautet, den FQDN und den Port.</span><span class="sxs-lookup"><span data-stu-id="9baf7-174">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="9baf7-175">Der Verbund wird mithilfe der globalen Sammlung von Access-Edge-Konfigurationseinstellungen aktiviert und deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9baf7-175">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="9baf7-176">Unter anderem bedeutet dies, dass der Verbund auf einer all-oder-Nothing-Basis konfiguriert ist: jeder Partnerverbund ist für die gesamte Organisation aktiviert, oder der Verbund ist für die gesamte Organisation deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9baf7-176">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="9baf7-177">Ihre Zugriffs-Edge-Konfigurationseinstellungen können mithilfe von Windows PowerShell zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9baf7-177">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="9baf7-178">Führen Sie dazu den folgenden Windows PowerShell Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="9baf7-178">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="9baf7-179">Dieser Befehl gibt wiederum Daten wie die folgende zurück:</span><span class="sxs-lookup"><span data-stu-id="9baf7-179">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="9baf7-180">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="9baf7-180">Identity : Global</span></span>

<span data-ttu-id="9baf7-181">AllowAnonymousUsers: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-181">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="9baf7-182">AllowFederatedUsers: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-182">AllowFederatedUsers : False</span></span>

<span data-ttu-id="9baf7-183">AllowOutsideUsers: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-183">AllowOutsideUsers : False</span></span>

<span data-ttu-id="9baf7-184">Beclearing: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-184">BeClearingHouse : False</span></span>

<span data-ttu-id="9baf7-185">EnablePartnerDiscovery: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-185">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="9baf7-186">EnableArchivingDisclaimer: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-186">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="9baf7-187">KeepCrlsUpToDateForPeers: true</span><span class="sxs-lookup"><span data-stu-id="9baf7-187">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="9baf7-188">MarkSourceVerifiableOnOutgoingMessages: true</span><span class="sxs-lookup"><span data-stu-id="9baf7-188">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="9baf7-189">OutgoingTlsCountForFederatedPartners: 4</span><span class="sxs-lookup"><span data-stu-id="9baf7-189">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="9baf7-190">RoutingMethod: UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="9baf7-190">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="9baf7-191">Wenn die **AllowFederatedUsers** -Eigenschaft auf true festgelegt ist, bedeutet dies, dass der Verbund für Ihre Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9baf7-191">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="9baf7-192">(Das Festlegen von **AllowFederatedUsers** auf "true" bedeutet auch, dass Ihre lokalen Benutzer in einem geteilten Domänen Szenario nahtlos mit ihren in-the-Cloud-Benutzern kommunizieren können.)</span><span class="sxs-lookup"><span data-stu-id="9baf7-192">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="9baf7-193">Informationen zum Abrufen der FQDN-und Porteinstellungen für Ihre Edgeserver finden Sie in der vorherigen Aufgabe (Edgeserver und deren Einstellungen).</span><span class="sxs-lookup"><span data-stu-id="9baf7-193">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="9baf7-194">Das Aktivieren von Verbund auf globaler Ebene bedeutet nur, dass Benutzer potenziell mit Verbundbenutzern kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="9baf7-194">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="9baf7-195">Um zu ermitteln, ob einzelne Benutzer tatsächlich mit Verbundbenutzern kommunizieren können, müssen Sie die Zugriffsrichtlinie für externe Benutzer überprüfen, die diesem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="9baf7-195">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="9baf7-196">Mithilfe von Windows PowerShell können externe Benutzerzugriffs Informationen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9baf7-196">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="9baf7-197">Mit diesem Befehl werden beispielsweise Informationen für die globale Richtlinie für den Zugriff auf externe Benutzer zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="9baf7-197">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="9baf7-198">Und dieser Befehl gibt Informationen zu allen Richtlinien für den externen Benutzer Zugriff zurück:</span><span class="sxs-lookup"><span data-stu-id="9baf7-198">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="9baf7-199">Die zurückgegebenen Informationen ähneln Folgendem:</span><span class="sxs-lookup"><span data-stu-id="9baf7-199">The returned information will resemble this:</span></span>

<span data-ttu-id="9baf7-200">Identity: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-200">Identity : False</span></span>

<span data-ttu-id="9baf7-201">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9baf7-201">Description :</span></span>

<span data-ttu-id="9baf7-202">EnableFederationAccess: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-202">EnableFederationAccess : False</span></span>

<span data-ttu-id="9baf7-203">EnablePublicCloudAccess: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-203">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="9baf7-204">EnablePublicCloudAccessAudioVideoAccess: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-204">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="9baf7-205">EnableOutsideAccess: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-205">EnableOutsideAccess : False</span></span>

<span data-ttu-id="9baf7-206">Wenn **EnableFederationAccess** auf true festgelegt ist, können Benutzer, die von der angegebenen Richtlinie verwaltet werden, mit Verbundbenutzern kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="9baf7-206">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="9baf7-207">Überprüfen der Archivierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="9baf7-207">Check archiving settings</span></span>

<span data-ttu-id="9baf7-208">Überprüfen Sie die Archivierungseinstellungen für die interne und die Verbundkommunikation. Bevor Sie die Einstellungen für die interne und externe Archivierung überprüfen, sollten Sie überprüfen, ob die Archivierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9baf7-208">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="9baf7-209">Die Archivierungs Konfigurationseinstellungen können mithilfe von Windows PowerShell und dem Get-CsArchivingConfiguration-Cmdlet überprüft werden:</span><span class="sxs-lookup"><span data-stu-id="9baf7-209">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="9baf7-210">Beachten Sie, dass Archivierungseinstellungen auch auf Standortebene konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="9baf7-210">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="9baf7-211">Verwenden Sie diesen Befehl, um Informationen zu allen Archivierungseinstellungen zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="9baf7-211">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="9baf7-212">Mit dem Get-CsArchivingConfiguration-Cmdlet werden Daten wie die folgende zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="9baf7-212">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="9baf7-213">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="9baf7-213">Identity : Global</span></span>

<span data-ttu-id="9baf7-214">Eigenschaft "enablearchiving: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-214">EnableArchiving : False</span></span>

<span data-ttu-id="9baf7-215">"Enablepurging": false</span><span class="sxs-lookup"><span data-stu-id="9baf7-215">EnablePurging : False</span></span>

<span data-ttu-id="9baf7-216">"Purgeexportedarchivesonly": false</span><span class="sxs-lookup"><span data-stu-id="9baf7-216">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="9baf7-217">BlockOnArchiveFailure: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-217">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="9baf7-218">"Keeparchivingdatafordays": 14</span><span class="sxs-lookup"><span data-stu-id="9baf7-218">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="9baf7-219">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="9baf7-219">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="9baf7-220">ArchiveDuplicateMessages: true</span><span class="sxs-lookup"><span data-stu-id="9baf7-220">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="9baf7-221">CachePurgingInterval: 24</span><span class="sxs-lookup"><span data-stu-id="9baf7-221">CachePurgingInterval : 24</span></span>

<span data-ttu-id="9baf7-222">Wenn die Eigenschaft "enablearchiving-Eigenschaft auf false festgelegt ist, bedeutet dies, dass keine Kommunikationssitzungen archiviert werden.</span><span class="sxs-lookup"><span data-stu-id="9baf7-222">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="9baf7-223">Wenn Sie nur Chatsitzungen archivieren möchten, verwenden Sie einen Befehl wie den folgenden, um die Archivierung von Sofortnachrichtensitzungen zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="9baf7-223">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="9baf7-224">Verwenden Sie diesen Befehl zum Archivieren von Konferenzsitzungen und Chatnachrichten Sitzungen:</span><span class="sxs-lookup"><span data-stu-id="9baf7-224">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="9baf7-225">Wenn Sie Ihre aktuellen Archivierungseinstellungen mit den Standardeinstellungen vergleichen möchten, führen Sie den folgenden Windows PowerShell Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="9baf7-225">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="9baf7-226">Mit diesem Befehl wird eine nur im Arbeitsspeicher vorhandene Instanz der globalen Archivierungs Konfigurationseinstellungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="9baf7-226">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="9baf7-227">Hierbei handelt es sich nicht um eine echte Sammlung von Einstellungen, die von lync Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9baf7-227">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="9baf7-228">Es werden jedoch die Standardwerte für alle Archivierungs Konfigurationseigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9baf7-228">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="9baf7-229">Sie können diesen Befehl auch verwenden, um den FQDN ihrer Archivierungsserver zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="9baf7-229">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="9baf7-230">Nachdem Sie überprüft haben, dass die Archivierung aktiviert ist, können Sie Ihre Archivierungsrichtlinien anzeigen, um festzustellen, ob interne und externe Kommunikationssitzungen archiviert werden.</span><span class="sxs-lookup"><span data-stu-id="9baf7-230">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="9baf7-231">Informationen zur Archivierungsrichtlinie können mithilfe des Get-CsArchivingPolicy-Cmdlets abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9baf7-231">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="9baf7-232">Mit diesem Befehl werden beispielsweise Informationen zur globalen Archivierungsrichtlinie zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="9baf7-232">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="9baf7-233">Da Archivierungsrichtlinien auch auf Standort-und Benutzerebene konfiguriert werden können, möchten Sie möglicherweise auch diesen Befehl verwenden, der Informationen zu allen Archivierungsrichtlinien zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="9baf7-233">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="9baf7-234">Die Informationen, die Sie von Get-CsArchivingPolicy erhalten, ähneln Ihnen:</span><span class="sxs-lookup"><span data-stu-id="9baf7-234">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="9baf7-235">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="9baf7-235">Identity : Global</span></span>

<span data-ttu-id="9baf7-236">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9baf7-236">Description :</span></span>

<span data-ttu-id="9baf7-237">"Archiveinternal": false</span><span class="sxs-lookup"><span data-stu-id="9baf7-237">ArchiveInternal : False</span></span>

<span data-ttu-id="9baf7-238">"Archiveexternal": false</span><span class="sxs-lookup"><span data-stu-id="9baf7-238">ArchiveExternal : False</span></span>

<span data-ttu-id="9baf7-239">Beachten Sie, dass die interne und externe Archivierung standardmäßig in einer Archivierungsrichtlinie deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9baf7-239">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="9baf7-240">Überprüfen der KDS-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="9baf7-240">Check CDR settings</span></span>

<span data-ttu-id="9baf7-241">Überprüfen Sie die KDS-Einstellungen (Call Detail Record) für die Aufzeichnung von Peer-zu-Peer-, Konferenz-und Sprachanruf Details.</span><span class="sxs-lookup"><span data-stu-id="9baf7-241">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="9baf7-242">Ausführliche Informationen zu ihren KDS-Einstellungen können mit dem Cmdlet **Get-CsCdrConfiguration** zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9baf7-242">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="9baf7-243">Mit diesem Befehl werden beispielsweise Informationen über die globale Auflistung von KDS-Konfigurationseinstellungen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="9baf7-243">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="9baf7-244">Da KDS auch auf Standortebene konfiguriert werden kann, möchten Sie möglicherweise auch diesen Befehl ausführen, der Informationen zu allen KDS-Konfigurationseinstellungen zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="9baf7-244">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="9baf7-245">Das Get-CsCdrConfiguration-Cmdlet gibt für jede Auflistung von KDS-Konfigurationseinstellungen ähnliche Informationen zurück:</span><span class="sxs-lookup"><span data-stu-id="9baf7-245">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="9baf7-246">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="9baf7-246">Identity : Global</span></span>

<span data-ttu-id="9baf7-247">"Enablecdr": true</span><span class="sxs-lookup"><span data-stu-id="9baf7-247">EnableCDR : True</span></span>

<span data-ttu-id="9baf7-248">"Enablepurging": true</span><span class="sxs-lookup"><span data-stu-id="9baf7-248">EnablePurging : True</span></span>

<span data-ttu-id="9baf7-249">"Keepcalldetailfordays": 60</span><span class="sxs-lookup"><span data-stu-id="9baf7-249">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="9baf7-250">KeepErrorReportForDays: 60</span><span class="sxs-lookup"><span data-stu-id="9baf7-250">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="9baf7-251">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="9baf7-251">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="9baf7-252">Ähnliche Informationen können für die QoE-Überwachung mithilfe des Get-CsQoEConfiguration-Cmdlets zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9baf7-252">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="9baf7-253">Mit diesem Befehl werden beispielsweise Informationen über die globale Auflistung von QoE-Konfigurationseinstellungen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="9baf7-253">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="9baf7-254">Diese Informationen ähneln Ihnen:</span><span class="sxs-lookup"><span data-stu-id="9baf7-254">That information will resemble this:</span></span>

<span data-ttu-id="9baf7-255">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="9baf7-255">Identity : Global</span></span>

<span data-ttu-id="9baf7-256">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="9baf7-256">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="9baf7-257">"Enablepurging": true</span><span class="sxs-lookup"><span data-stu-id="9baf7-257">EnablePurging : True</span></span>

<span data-ttu-id="9baf7-258">"Keepqoedatafordays": 60</span><span class="sxs-lookup"><span data-stu-id="9baf7-258">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="9baf7-259">PurgeHourOfDay: 1</span><span class="sxs-lookup"><span data-stu-id="9baf7-259">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="9baf7-260">EnableExternalConsumer: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-260">EnableExternalConsumer : False</span></span>

<span data-ttu-id="9baf7-261">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="9baf7-261">ExternalConsumerName :</span></span>

<span data-ttu-id="9baf7-262">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="9baf7-262">ExternalConsumerURL :</span></span>

<span data-ttu-id="9baf7-263">EnableQoE: true</span><span class="sxs-lookup"><span data-stu-id="9baf7-263">EnableQoE : True</span></span>

<span data-ttu-id="9baf7-264">Wenn Sie Ihre aktuellen KDS-Einstellungen mit den standardmäßigen KDS-Einstellungen vergleichen möchten, können Sie die Standardwerte überprüfen, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="9baf7-264">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="9baf7-265">Ebenso können die Standardwerte für die QoE-Überwachung mithilfe dieses Befehls abgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="9baf7-265">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="9baf7-266">Sie können den FQDN ihrer Monitoring Server auch zurückgeben, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="9baf7-266">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="9baf7-267">Spracheinstellungen überprüfen</span><span class="sxs-lookup"><span data-stu-id="9baf7-267">Check voice settings</span></span>

<span data-ttu-id="9baf7-268">Die VoIP-Einstellungen, die für Administratoren typischerweise wichtig sind, sind in VoIP-Richtlinien und VoIP-Routen enthalten: VoIP-Richtlinien enthalten die Einstellungen, die die für einzelne Benutzer verfügbaren Funktionen bestimmen (beispielsweise die Möglichkeit, Anrufe weiterzuleiten oder zu übertragen), während VoIP-Routen bestimmen, wie (und wenn) Anrufe über das PSTN weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="9baf7-268">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="9baf7-269">Informationen zur VoIP-Richtlinie können mithilfe von Windows PowerShell abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9baf7-269">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="9baf7-270">Mit diesem Befehl werden beispielsweise Informationen zur globalen VoIP-Richtlinie zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="9baf7-270">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="9baf7-271">Und dieser Befehl gibt Informationen zu allen VoIP-Richtlinien zurück, die für die Verwendung in der Organisation konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="9baf7-271">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="9baf7-272">Die vom Get-CsVoicePolicy-Cmdlet zurückgegebenen Informationen ähneln wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9baf7-272">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="9baf7-273">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="9baf7-273">Identity : Global</span></span>

<span data-ttu-id="9baf7-274">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="9baf7-274">PstnUsages : {}</span></span>

<span data-ttu-id="9baf7-275">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9baf7-275">Description :</span></span>

<span data-ttu-id="9baf7-276">AllowSimulRing: true</span><span class="sxs-lookup"><span data-stu-id="9baf7-276">AllowSimulRing : True</span></span>

<span data-ttu-id="9baf7-277">AllowCallForwarding: true</span><span class="sxs-lookup"><span data-stu-id="9baf7-277">AllowCallForwarding : True</span></span>

<span data-ttu-id="9baf7-278">AllowPSTNReRouting: true</span><span class="sxs-lookup"><span data-stu-id="9baf7-278">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="9baf7-279">Name: DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="9baf7-279">Name : DefaultPolicy</span></span>

<span data-ttu-id="9baf7-280">EnableDelegation: true</span><span class="sxs-lookup"><span data-stu-id="9baf7-280">EnableDelegation : True</span></span>

<span data-ttu-id="9baf7-281">EnableTeamCall: true</span><span class="sxs-lookup"><span data-stu-id="9baf7-281">EnableTeamCall : True</span></span>

<span data-ttu-id="9baf7-282">EnableCallTransfer: true</span><span class="sxs-lookup"><span data-stu-id="9baf7-282">EnableCallTransfer : True</span></span>

<span data-ttu-id="9baf7-283">EnableCallPark: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-283">EnableCallPark : False</span></span>

<span data-ttu-id="9baf7-284">EnableMaliciousCallTracing: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-284">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="9baf7-285">EnableBWPolicyOverride: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-285">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="9baf7-286">PreventPSTNTollBypass: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-286">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="9baf7-287">Sie können auch Abfragen erstellen, die eine Teilmenge ihrer VoIP-Richtlinien zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="9baf7-287">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="9baf7-288">Mit diesem Befehl werden beispielsweise alle VoIP-Richtlinien zurückgegeben, die die Anrufweiterleitung ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="9baf7-288">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="9baf7-289">Und dieser Befehl gibt alle VoIP-Richtlinien zurück, die die Anrufweiterleitung nicht zulassen:</span><span class="sxs-lookup"><span data-stu-id="9baf7-289">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="9baf7-290">Verwenden Sie in Windows PowerShell das Get-CsVoiceRouting-Cmdlet, um Informationen zu Ihren VoIP-Routen zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="9baf7-290">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="9baf7-291">Dieser Befehl gibt Informationen wie diese für alle VoIP-Routen zurück:</span><span class="sxs-lookup"><span data-stu-id="9baf7-291">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="9baf7-292">Identity: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="9baf7-292">Identity : LocalRoute</span></span>

<span data-ttu-id="9baf7-293">Priorität: 0</span><span class="sxs-lookup"><span data-stu-id="9baf7-293">Priority : 0</span></span>

<span data-ttu-id="9baf7-294">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9baf7-294">Description :</span></span>

<span data-ttu-id="9baf7-295">NumberPattern: ^ ( \\ + 1 \[ 0-9 \] {10} ) $</span><span class="sxs-lookup"><span data-stu-id="9baf7-295">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="9baf7-296">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="9baf7-296">PstnUsages : {}</span></span>

<span data-ttu-id="9baf7-297">PstnGatewayList : {}</span><span class="sxs-lookup"><span data-stu-id="9baf7-297">PstnGatewayList : {}</span></span>

<span data-ttu-id="9baf7-298">Name: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="9baf7-298">Name : LocalRoute</span></span>

<span data-ttu-id="9baf7-299">SuppressCallerId :</span><span class="sxs-lookup"><span data-stu-id="9baf7-299">SuppressCallerId :</span></span>

<span data-ttu-id="9baf7-300">AlternateCallerId :</span><span class="sxs-lookup"><span data-stu-id="9baf7-300">AlternateCallerId :</span></span>

<span data-ttu-id="9baf7-301">In lync Server können Sie VoIP-Routen erstellen, die nicht über ein PSTN verwendet werden und kein PSTN-Gateway angeben.</span><span class="sxs-lookup"><span data-stu-id="9baf7-301">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="9baf7-302">Es ist jedoch nicht möglich, Anrufe tatsächlich über eine VoIP-Route weiterzuleiten, für die diese beiden Eigenschaftswerte nicht konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="9baf7-302">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="9baf7-303">Aus diesem Grund kann es sinnvoll sein, diesen Befehl regelmäßig auszuführen, wodurch die Identität einer VoIP-Route zurückgegeben wird, die nicht über ein PSTN verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="9baf7-303">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="9baf7-304">Auf ähnliche Weise gibt dieser Befehl die Identität einer VoIP-Route zurück, die nicht für ein PSTN-Gateway konfiguriert wurde:</span><span class="sxs-lookup"><span data-stu-id="9baf7-304">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="9baf7-305">Überprüfen der Einstellungen für die Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="9baf7-305">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="9baf7-306">Überprüfen der Einstellungen für die Konferenzzentrale für PSTN-Einwahlkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="9baf7-306">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="9baf7-307">Einstellungen für die Konferenzzentrale können nur mithilfe des Cmdlets **Get-CsDialInConferencingConfiguration** abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9baf7-307">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="9baf7-308">Diese Einstellungen stehen im lync Server-Systemsteuerung nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9baf7-308">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="9baf7-309">Verwenden Sie zum Anzeigen der Einstellungen für die Konferenzzentrale einen Windows PowerShell Befehl wie den folgenden, der die globale Auflistung der Einstellungen für die Konferenzzentrale zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="9baf7-309">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="9baf7-310">Beachten Sie, dass die Einstellungen für die Konferenzzentrale auch auf Standortebene konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="9baf7-310">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="9baf7-311">Wenn Sie Informationen zu allen Einstellungen für die Konferenzzentrale zurückgeben möchten, verwenden Sie stattdessen den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="9baf7-311">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="9baf7-312">Mit dem Get-CsDialInConferencingConfiguration-Cmdlet werden Daten wie die folgende zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="9baf7-312">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="9baf7-313">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="9baf7-313">Identity : Global</span></span>

<span data-ttu-id="9baf7-314">EntryExitAnnouncementsType : UseNames</span><span class="sxs-lookup"><span data-stu-id="9baf7-314">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="9baf7-315">EnableNameRecording: true</span><span class="sxs-lookup"><span data-stu-id="9baf7-315">EnableNameRecording : True</span></span>

<span data-ttu-id="9baf7-316">EntryExitAnnouncementsEnabledByDefault: false</span><span class="sxs-lookup"><span data-stu-id="9baf7-316">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="9baf7-317">Wenn EntryExitAnnouncementsEnabledByDefault auf false festgelegt ist, bedeutet dies, dass die Ankündigungen für Konferenzen deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="9baf7-317">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="9baf7-318">Um ein-und Ausstiegs Ankündigungen zu aktivieren, führen Sie einen Windows PowerShell Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="9baf7-318">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9baf7-319">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9baf7-319">See Also</span></span>


[<span data-ttu-id="9baf7-320">Get-CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="9baf7-320">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="9baf7-321">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9baf7-321">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="9baf7-322">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="9baf7-322">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="9baf7-323">Get-csaccessedgeconfiguration nicht angeben</span><span class="sxs-lookup"><span data-stu-id="9baf7-323">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="9baf7-324">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9baf7-324">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="9baf7-325">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9baf7-325">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="9baf7-326">Get-CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="9baf7-326">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="9baf7-327">Get-CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="9baf7-327">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="9baf7-328">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="9baf7-328">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="9baf7-329">Get-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="9baf7-329">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="9baf7-330">Get-CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9baf7-330">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

