---
title: 'Lync Server 2013: Anzeigen des Status globaler Einstellungen für eine Gesamtstruktur'
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
ms.openlocfilehash: ec1dea4ad3d5052bc2ba23cccd9e19ab138414ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="1a792-102">Anzeigen des Status globaler Einstellungen für eine Gesamtstruktur in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a792-102">View status of global settings for a forest in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a792-103">_**Letztes Änderungsdatum des Themas:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="1a792-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="1a792-104">Administratoren sollten die globalen Einstellungen für eine lync Server 2013-Bereitstellung monatlich überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1a792-104">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="1a792-105">Das Ziel besteht darin, die implementierten Einstellungen für eine Reihe bekannter Konfigurationen zu überprüfen – eine Baseline-Konfiguration, um sicherzustellen, dass die Einstellungen gültig sind, und um festzustellen, ob die Baseline-Dokumentation aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1a792-105">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="1a792-106">Änderungen an der globalen Einstellung sollten über einen Änderungskontrollprozess implementiert werden, der die Dokumentation der neuen Einstellungen umfasst.</span><span class="sxs-lookup"><span data-stu-id="1a792-106">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="1a792-107">Die globalen Einstellungen, die überprüft werden sollten, werden in den folgenden Abschnitten beschrieben:</span><span class="sxs-lookup"><span data-stu-id="1a792-107">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="1a792-108">Allgemeine Einstellungen überprüfen</span><span class="sxs-lookup"><span data-stu-id="1a792-108">Check general settings</span></span>

<span data-ttu-id="1a792-109">Überprüfen Sie die allgemeinen Einstellungen, einschließlich der unterstützten SIP-Domänen (Session Initiation Protocol) für lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a792-109">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="1a792-110">SIP-Domäneninformationen können mithilfe von Windows PowerShell und dem Cmdlet **Get-CsSipDomain** zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1a792-110">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="1a792-111">Wenn Sie diese Informationen zurückgeben möchten `Get-CsSipDomain` , führen Sie den Windows PowerShell-Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="1a792-111">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="1a792-112">"Get-CsSipDomain" gibt ähnliche Informationen für alle autorisierten SIP-Domänen zurück:</span><span class="sxs-lookup"><span data-stu-id="1a792-112">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="1a792-113">Identitäts Name IsDefault</span><span class="sxs-lookup"><span data-stu-id="1a792-113">Identity Name IsDefault</span></span>

<span data-ttu-id="1a792-114">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="1a792-114">\-------- ---- ---------</span></span>

<span data-ttu-id="1a792-115">fabrikam.com fabrikam.com true</span><span class="sxs-lookup"><span data-stu-id="1a792-115">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="1a792-116">na.fabrikam.com na.fabrikam.com false</span><span class="sxs-lookup"><span data-stu-id="1a792-116">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="1a792-117">Wenn die IsDefault-Eigenschaft auf true festgelegt ist, ist die entsprechende Domäne Ihre standardmäßige SIP-Domäne.</span><span class="sxs-lookup"><span data-stu-id="1a792-117">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="1a792-118">Sie können das Cmdlet "Satz-CsSipDomain" verwenden, um die SIP-Standarddomäne für Ihre Organisation zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1a792-118">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="1a792-119">Sie können die standardmäßige SIP-Domäne jedoch nicht einfach löschen, da Sie ohne eine Standarddomäne verbleibt.</span><span class="sxs-lookup"><span data-stu-id="1a792-119">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="1a792-120">Wenn Sie die fabrikam.com-Domäne löschen möchten (wie im vorherigen Beispiel gezeigt), müssen Sie na.fabrikam.com zunächst so konfigurieren, dass es sich um Ihre Standarddomäne handelt.</span><span class="sxs-lookup"><span data-stu-id="1a792-120">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="1a792-121">Überprüfen von Besprechungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="1a792-121">Check meeting settings</span></span>

<span data-ttu-id="1a792-122">Zu den Besprechungseinstellungen gehören Richtlinien Definitionen für Besprechungen und die Unterstützung für die Teilnahme anonymer Benutzer an Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="1a792-122">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="1a792-123">Die Einstellungen für die besprechungskonfiguration können mithilfe von Windows PowerShell und dem Cmdlet **Get-CsMeetingConfiguration** abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1a792-123">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="1a792-124">Dieser Befehl gibt beispielsweise Informationen zu den Konfigurationseinstellungen für globale Besprechungen zurück:</span><span class="sxs-lookup"><span data-stu-id="1a792-124">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="1a792-125">Get-CsMeetingConfiguration – Identity "Global" die Konfigurationseinstellungen für Besprechungen können auch im Website Bereich konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1a792-125">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="1a792-126">Aus diesem Grund sollten Sie den folgenden Befehl verwenden, der Informationen zu allen Besprechungs Konfigurationseinstellungen zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="1a792-126">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="1a792-127">Das Cmdlet " **Get-CsMeetingConfiguration** " gibt Informationen ähnlich der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="1a792-127">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="1a792-128">Identität: Global</span><span class="sxs-lookup"><span data-stu-id="1a792-128">Identity : Global</span></span>

<span data-ttu-id="1a792-129">PstnCallersBypassLobby: true</span><span class="sxs-lookup"><span data-stu-id="1a792-129">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="1a792-130">EnableAssignedConferenceType: true</span><span class="sxs-lookup"><span data-stu-id="1a792-130">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="1a792-131">DesignateAsPresenter: Unternehmen</span><span class="sxs-lookup"><span data-stu-id="1a792-131">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="1a792-132">AssignedConferenceTypeByDefault: true</span><span class="sxs-lookup"><span data-stu-id="1a792-132">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="1a792-133">AdmitAnonymousUsersByDefault: true</span><span class="sxs-lookup"><span data-stu-id="1a792-133">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="1a792-134">Das letzte Element in der Liste, **AdmitAnonymousUsersByDefault**, aktiviert oder deaktiviert die Möglichkeit von anonymen Benutzern, an Besprechungen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="1a792-134">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="1a792-135">Wenn Sie die Einstellungen für die besprechungskonfiguration überprüfen, finden Sie es möglicherweise hilfreich, die aktuellen Einstellungen mit den Standard äquivalenten zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="1a792-135">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="1a792-136">Sie können die Standardeinstellungen für die besprechungskonfiguration anzeigen, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="1a792-136">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="1a792-137">Der vorherige Befehl erstellt eine speicherresidente Instanz der globalen Besprechungs Konfigurationseinstellungen, eine Instanz, die den Standardwert für jede Eigenschaft verwendet.</span><span class="sxs-lookup"><span data-stu-id="1a792-137">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="1a792-138">Wenn Sie den Befehl ausführen, werden keine tatsächlichen Besprechungs Konfigurationseinstellungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="1a792-138">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="1a792-139">Alle standardmäßigen Eigenschaftswerte werden jedoch auf dem Bildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a792-139">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="1a792-140">Überprüfen von Edgeserver und deren Einstellungen</span><span class="sxs-lookup"><span data-stu-id="1a792-140">Check Edge Servers and their settings</span></span>

<span data-ttu-id="1a792-141">Edge-Server Informationen können mithilfe von Windows PowerShell abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1a792-141">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="1a792-142">Dieser Befehl gibt Informationen zu allen Edge-Servern zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="1a792-142">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="1a792-143">Die zurückgegebenen Informationen enthalten alle FQDN-und Porteinstellungen für jeden Edgeserver:</span><span class="sxs-lookup"><span data-stu-id="1a792-143">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="1a792-144">Identity: EdgeServer: DC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1a792-144">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="1a792-145">Kanzler: Kanzler: LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1a792-145">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="1a792-146">AccessEdgeInternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="1a792-146">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="1a792-147">AccessEdgeExternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="1a792-147">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="1a792-148">AccessEdgeClientPort: 443</span><span class="sxs-lookup"><span data-stu-id="1a792-148">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="1a792-149">DataPsomServerPort: 8057</span><span class="sxs-lookup"><span data-stu-id="1a792-149">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="1a792-150">DataPsomClientPort: 444</span><span class="sxs-lookup"><span data-stu-id="1a792-150">DataPsomClientPort : 444</span></span>

<span data-ttu-id="1a792-151">MediaRelayAuthEdgePort: 5062</span><span class="sxs-lookup"><span data-stu-id="1a792-151">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="1a792-152">MediaRelayAuthInternalTurnTcpPort: 443</span><span class="sxs-lookup"><span data-stu-id="1a792-152">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="1a792-153">MediaRelayAuthExternalTurnTcpPort: 445</span><span class="sxs-lookup"><span data-stu-id="1a792-153">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="1a792-154">MediaRelayAuthInternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="1a792-154">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="1a792-155">MediaRelayAuthExternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="1a792-155">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="1a792-156">MediaCommunicationPortStart: 50000</span><span class="sxs-lookup"><span data-stu-id="1a792-156">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="1a792-157">MediaComunicationPortCount: 10000</span><span class="sxs-lookup"><span data-stu-id="1a792-157">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="1a792-158">AccessEdgeExternalFqdn: DC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1a792-158">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="1a792-159">DataEdgeExternalFqdn: DC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1a792-159">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="1a792-160">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="1a792-160">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="1a792-161">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="1a792-161">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="1a792-162">ExternalMrasFqdn: DC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1a792-162">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="1a792-163">DependentServiceList: {Registrar: LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="1a792-163">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="1a792-164">ConferencingServer: LYNC-SE. fabrikam</span><span class="sxs-lookup"><span data-stu-id="1a792-164">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="1a792-165">com, MediationServer: LYNC-SE.</span><span class="sxs-lookup"><span data-stu-id="1a792-165">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="1a792-166">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="1a792-166">fabrikam.com}</span></span>

<span data-ttu-id="1a792-167">Dienst-Nr: fabrikam.com-EdgeServer-2</span><span class="sxs-lookup"><span data-stu-id="1a792-167">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="1a792-168">Website-Nr: Website:fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="1a792-168">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="1a792-169">PoolFqdn: DC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1a792-169">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="1a792-170">Version: 5</span><span class="sxs-lookup"><span data-stu-id="1a792-170">Version : 5</span></span>

<span data-ttu-id="1a792-171">Rolle: EdgeServer</span><span class="sxs-lookup"><span data-stu-id="1a792-171">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="1a792-172">Überprüfen der Verbund Einstellungen</span><span class="sxs-lookup"><span data-stu-id="1a792-172">Check federation settings</span></span>

<span data-ttu-id="1a792-173">Überprüfen Sie die Verbund Einstellungen, beispielsweise ob Sie konfiguriert ist und, wenn die Antwort "Ja" lautet, den FQDN und den Port.</span><span class="sxs-lookup"><span data-stu-id="1a792-173">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="1a792-174">Der Verbund wird mithilfe der globalen Sammlung von Access Edge-Konfigurationseinstellungen aktiviert und deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1a792-174">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="1a792-175">Unter anderem bedeutet dies, dass der Verbund auf der Grundlage einer vollständigen oder gar nichts-Basis konfiguriert ist: entweder ist der Verbund für die gesamte Organisation aktiviert, oder der Verbund ist für die gesamte Organisation deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1a792-175">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="1a792-176">Ihre Access Edge-Konfigurationseinstellungen können mithilfe von Windows PowerShell zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1a792-176">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="1a792-177">Führen Sie dazu den folgenden Windows PowerShell-Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="1a792-177">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="1a792-178">Dieser Befehl gibt wiederum Daten zurück, die wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="1a792-178">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="1a792-179">Identität: Global</span><span class="sxs-lookup"><span data-stu-id="1a792-179">Identity : Global</span></span>

<span data-ttu-id="1a792-180">AllowAnonymousUsers: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-180">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="1a792-181">AllowFederatedUsers: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-181">AllowFederatedUsers : False</span></span>

<span data-ttu-id="1a792-182">AllowOutsideUsers: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-182">AllowOutsideUsers : False</span></span>

<span data-ttu-id="1a792-183">Beclearing: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-183">BeClearingHouse : False</span></span>

<span data-ttu-id="1a792-184">EnablePartnerDiscovery: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-184">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="1a792-185">EnableArchivingDisclaimer: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-185">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="1a792-186">KeepCrlsUpToDateForPeers: true</span><span class="sxs-lookup"><span data-stu-id="1a792-186">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="1a792-187">MarkSourceVerifiableOnOutgoingMessages: true</span><span class="sxs-lookup"><span data-stu-id="1a792-187">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="1a792-188">OutgoingTlsCountForFederatedPartners: 4</span><span class="sxs-lookup"><span data-stu-id="1a792-188">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="1a792-189">RoutingMethod : UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="1a792-189">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="1a792-190">Wenn die **AllowFederatedUsers** -Eigenschaft auf "true" festgelegt ist, bedeutet dies, dass der Verbund für Ihre Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1a792-190">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="1a792-191">(Wenn Sie **AllowFederatedUsers** auf "true" festlegen, bedeutet dies auch, dass Ihre lokalen Benutzer in einem geteilten Domänen Szenario nahtlos mit ihren in-the-Cloud-Benutzern kommunizieren können.)</span><span class="sxs-lookup"><span data-stu-id="1a792-191">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="1a792-192">Informationen zum Abrufen der FQDN-und Porteinstellungen für Ihren Edgeserver finden Sie in der vorherigen Aufgabe (Edgeserver und deren Einstellungen).</span><span class="sxs-lookup"><span data-stu-id="1a792-192">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="1a792-193">Das Aktivieren des Föderations Bereichs im globalen Bereich bedeutet nur, dass Benutzer potenziell mit Verbundbenutzern kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="1a792-193">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="1a792-194">Wenn Sie feststellen möchten, ob einzelne Benutzer tatsächlich mit Verbundbenutzern kommunizieren können, müssen Sie die Richtlinie für den externen Benutzer Zugriff untersuchen, die diesem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="1a792-194">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="1a792-195">Zugriffsinformationen für externe Benutzer können mithilfe von Windows PowerShell zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1a792-195">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="1a792-196">Dieser Befehl gibt beispielsweise Informationen für die globale Richtlinie für den externen Benutzer Zugriff zurück:</span><span class="sxs-lookup"><span data-stu-id="1a792-196">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="1a792-197">Und dieser Befehl gibt Informationen für alle Richtlinien für den externen Benutzer Zugriff zurück:</span><span class="sxs-lookup"><span data-stu-id="1a792-197">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="1a792-198">Die zurückgegebenen Informationen werden wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="1a792-198">The returned information will resemble this:</span></span>

<span data-ttu-id="1a792-199">Identität: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-199">Identity : False</span></span>

<span data-ttu-id="1a792-200">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a792-200">Description :</span></span>

<span data-ttu-id="1a792-201">EnableFederationAccess: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-201">EnableFederationAccess : False</span></span>

<span data-ttu-id="1a792-202">EnablePublicCloudAccess: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-202">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="1a792-203">EnablePublicCloudAccessAudioVideoAccess: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-203">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="1a792-204">EnableOutsideAccess: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-204">EnableOutsideAccess : False</span></span>

<span data-ttu-id="1a792-205">Wenn **EnableFederationAccess** auf "true" festgelegt ist, können Benutzer, die von der angegebenen Richtlinie verwaltet werden, mit Verbundbenutzern kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="1a792-205">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="1a792-206">Überprüfen der Archivierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="1a792-206">Check archiving settings</span></span>

<span data-ttu-id="1a792-207">Überprüfen Sie die Archivierungseinstellungen für die interne und die Verbundkommunikation. Bevor Sie die Einstellungen für die interne und externe Archivierung überprüfen, sollten Sie sicherstellen, dass die Archivierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1a792-207">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="1a792-208">Die Archivierungs Konfigurationseinstellungen können mithilfe von Windows PowerShell und dem Cmdlet Get-CsArchivingConfiguration überprüft werden:</span><span class="sxs-lookup"><span data-stu-id="1a792-208">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="1a792-209">Beachten Sie, dass Archivierungseinstellungen auch im Website Bereich konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="1a792-209">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="1a792-210">Wenn Sie Informationen zu allen Archivierungseinstellungen zurückgeben möchten, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="1a792-210">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="1a792-211">Das Cmdlet "Get-CsArchivingConfiguration" gibt Daten ähnlich wie folgt zurück:</span><span class="sxs-lookup"><span data-stu-id="1a792-211">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="1a792-212">Identität: Global</span><span class="sxs-lookup"><span data-stu-id="1a792-212">Identity : Global</span></span>

<span data-ttu-id="1a792-213">EnableArchiving: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-213">EnableArchiving : False</span></span>

<span data-ttu-id="1a792-214">EnablePurging: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-214">EnablePurging : False</span></span>

<span data-ttu-id="1a792-215">PurgeExportedArchivesOnly: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-215">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="1a792-216">BlockOnArchiveFailure: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-216">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="1a792-217">"Keeparchivingdatafordays": 14</span><span class="sxs-lookup"><span data-stu-id="1a792-217">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="1a792-218">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="1a792-218">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="1a792-219">ArchiveDuplicateMessages: true</span><span class="sxs-lookup"><span data-stu-id="1a792-219">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="1a792-220">CachePurgingInterval: 24</span><span class="sxs-lookup"><span data-stu-id="1a792-220">CachePurgingInterval : 24</span></span>

<span data-ttu-id="1a792-221">Wenn die EnableArchiving-Eigenschaft auf false festgelegt ist, bedeutet dies, dass keine Kommunikationssitzungen archiviert werden.</span><span class="sxs-lookup"><span data-stu-id="1a792-221">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="1a792-222">Wenn Sie nur Instant Messaging-Sitzungen archivieren möchten, verwenden Sie einen Befehl wie den folgenden, um die Archivierung von Chatsitzungen zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="1a792-222">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="1a792-223">Verwenden Sie den folgenden Befehl, um Konferenzsitzungen und Chatsitzungen zu archivieren:</span><span class="sxs-lookup"><span data-stu-id="1a792-223">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="1a792-224">Wenn Sie Ihre aktuellen Archivierungseinstellungen mit den Standardeinstellungen vergleichen möchten, führen Sie den folgenden Windows PowerShell-Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="1a792-224">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="1a792-225">Dieser Befehl erstellt eine speicherresidente Instanz der globalen Archivierungs Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="1a792-225">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="1a792-226">Hierbei handelt es sich nicht um eine echte Sammlung von Einstellungen, die von lync Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1a792-226">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="1a792-227">Es werden jedoch die Standardwerte für alle Archivierungs Konfigurationseigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a792-227">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="1a792-228">Sie können diesen Befehl auch verwenden, um den FQDN ihrer Archivierungsserver zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="1a792-228">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="1a792-229">Nachdem Sie überprüft haben, dass die Archivierung aktiviert ist, können Sie Ihre Archivierungsrichtlinien anzeigen, um festzustellen, ob interne und externe Kommunikationssitzungen archiviert werden.</span><span class="sxs-lookup"><span data-stu-id="1a792-229">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="1a792-230">Informationen zur Archivierungsrichtlinie können mit dem Cmdlet Get-CsArchivingPolicy abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1a792-230">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="1a792-231">Dieser Befehl gibt beispielsweise Informationen zur globalen Archivierungsrichtlinie zurück:</span><span class="sxs-lookup"><span data-stu-id="1a792-231">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="1a792-232">Da Archivierungsrichtlinien auch auf der Website und im Benutzerbereich konfiguriert werden können, möchten Sie möglicherweise auch diesen Befehl verwenden, der Informationen zu allen Archivierungsrichtlinien zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="1a792-232">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="1a792-233">Die Informationen, die Sie von Get-CsArchivingPolicy erhalten, werden wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="1a792-233">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="1a792-234">Identität: Global</span><span class="sxs-lookup"><span data-stu-id="1a792-234">Identity : Global</span></span>

<span data-ttu-id="1a792-235">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a792-235">Description :</span></span>

<span data-ttu-id="1a792-236">ArchiveInternal: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-236">ArchiveInternal : False</span></span>

<span data-ttu-id="1a792-237">ArchiveExternal: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-237">ArchiveExternal : False</span></span>

<span data-ttu-id="1a792-238">Beachten Sie, dass die interne und externe Archivierung standardmäßig in einer Archivierungsrichtlinie deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1a792-238">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="1a792-239">Überprüfen der CDR-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="1a792-239">Check CDR settings</span></span>

<span data-ttu-id="1a792-240">Überprüfen Sie die Einstellungen für den Anruf Detailsatz (CDR) für Peer-to-Peer-, Konferenz-und Sprachanruf Detail Aufzeichnung.</span><span class="sxs-lookup"><span data-stu-id="1a792-240">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="1a792-241">Detaillierte Informationen zu Ihren CDR-Einstellungen können mit dem Cmdlet **Get-CsCdrConfiguration** zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1a792-241">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="1a792-242">Dieser Befehl gibt beispielsweise Informationen zur globalen Sammlung von CDR-Konfigurationseinstellungen zurück:</span><span class="sxs-lookup"><span data-stu-id="1a792-242">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="1a792-243">Da CdR auch im Website Bereich konfiguriert werden kann, möchten Sie möglicherweise auch diesen Befehl ausführen, der Informationen zu allen CdR-Konfigurationseinstellungen zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="1a792-243">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="1a792-244">Das Cmdlet "Get-CsCdrConfiguration" gibt ähnliche Informationen für jede Sammlung von CDR-Konfigurationseinstellungen zurück:</span><span class="sxs-lookup"><span data-stu-id="1a792-244">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="1a792-245">Identität: Global</span><span class="sxs-lookup"><span data-stu-id="1a792-245">Identity : Global</span></span>

<span data-ttu-id="1a792-246">EnableCDR: true</span><span class="sxs-lookup"><span data-stu-id="1a792-246">EnableCDR : True</span></span>

<span data-ttu-id="1a792-247">EnablePurging: true</span><span class="sxs-lookup"><span data-stu-id="1a792-247">EnablePurging : True</span></span>

<span data-ttu-id="1a792-248">KeepCallDetailForDays: 60</span><span class="sxs-lookup"><span data-stu-id="1a792-248">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="1a792-249">KeepErrorReportForDays: 60</span><span class="sxs-lookup"><span data-stu-id="1a792-249">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="1a792-250">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="1a792-250">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="1a792-251">Ähnliche Informationen können für die QoE-Überwachung mit dem Cmdlet Get-CsQoEConfiguration zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1a792-251">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="1a792-252">Dieser Befehl gibt beispielsweise Informationen zur globalen Sammlung der QoE-Konfigurationseinstellungen zurück:</span><span class="sxs-lookup"><span data-stu-id="1a792-252">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="1a792-253">Diese Informationen werden wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="1a792-253">That information will resemble this:</span></span>

<span data-ttu-id="1a792-254">Identität: Global</span><span class="sxs-lookup"><span data-stu-id="1a792-254">Identity : Global</span></span>

<span data-ttu-id="1a792-255">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="1a792-255">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="1a792-256">EnablePurging: true</span><span class="sxs-lookup"><span data-stu-id="1a792-256">EnablePurging : True</span></span>

<span data-ttu-id="1a792-257">KeepQoEDataForDays: 60</span><span class="sxs-lookup"><span data-stu-id="1a792-257">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="1a792-258">PurgeHourOfDay: 1</span><span class="sxs-lookup"><span data-stu-id="1a792-258">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="1a792-259">EnableExternalConsumer: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-259">EnableExternalConsumer : False</span></span>

<span data-ttu-id="1a792-260">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="1a792-260">ExternalConsumerName :</span></span>

<span data-ttu-id="1a792-261">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="1a792-261">ExternalConsumerURL :</span></span>

<span data-ttu-id="1a792-262">EnableQoE: true</span><span class="sxs-lookup"><span data-stu-id="1a792-262">EnableQoE : True</span></span>

<span data-ttu-id="1a792-263">Wenn Sie Ihre aktuellen CdR-Einstellungen mit den standardmäßigen CdR-Einstellungen vergleichen möchten, können Sie die Standardwerte überprüfen, indem Sie folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="1a792-263">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="1a792-264">Ebenso können die Standardwerte für die QoE-Überwachung mithilfe dieses Befehls abgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="1a792-264">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="1a792-265">Sie können auch den FQDN ihrer Überwachungsserver zurückgeben, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="1a792-265">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="1a792-266">Spracheinstellungen überprüfen</span><span class="sxs-lookup"><span data-stu-id="1a792-266">Check voice settings</span></span>

<span data-ttu-id="1a792-267">Die in der Regel für Administratoren wichtigen Spracheinstellungen sind in VoIP-Richtlinien und VoIP-Routen enthalten: VoIP-Richtlinien enthalten die Einstellungen, die die für einzelne Benutzer verfügbar gemachten Funktionen (wie die Möglichkeit zum Weiterleiten oder übertragen von Anrufen) bestimmen, während VoIP-Routen legen fest, wie (und wenn) Anrufe über das PSTN weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="1a792-267">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="1a792-268">VoIP-Richtlinieninformationen können mithilfe von Windows PowerShell abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1a792-268">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="1a792-269">Dieser Befehl gibt beispielsweise Informationen zur globalen VoIP-Richtlinie zurück:</span><span class="sxs-lookup"><span data-stu-id="1a792-269">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="1a792-270">Und dieser Befehl gibt Informationen zu allen VoIP-Richtlinien zurück, die für die Verwendung in der Organisation konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="1a792-270">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="1a792-271">Die vom Cmdlet "Get-CsVoicePolicy" zurückgegebenen Informationen ähneln wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1a792-271">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="1a792-272">Identität: Global</span><span class="sxs-lookup"><span data-stu-id="1a792-272">Identity : Global</span></span>

<span data-ttu-id="1a792-273">PstnUsages :{}</span><span class="sxs-lookup"><span data-stu-id="1a792-273">PstnUsages : {}</span></span>

<span data-ttu-id="1a792-274">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a792-274">Description :</span></span>

<span data-ttu-id="1a792-275">AllowSimulRing: true</span><span class="sxs-lookup"><span data-stu-id="1a792-275">AllowSimulRing : True</span></span>

<span data-ttu-id="1a792-276">AllowCallForwarding: true</span><span class="sxs-lookup"><span data-stu-id="1a792-276">AllowCallForwarding : True</span></span>

<span data-ttu-id="1a792-277">AllowPSTNReRouting: true</span><span class="sxs-lookup"><span data-stu-id="1a792-277">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="1a792-278">Name: DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="1a792-278">Name : DefaultPolicy</span></span>

<span data-ttu-id="1a792-279">EnableDelegation: true</span><span class="sxs-lookup"><span data-stu-id="1a792-279">EnableDelegation : True</span></span>

<span data-ttu-id="1a792-280">EnableTeamCall: true</span><span class="sxs-lookup"><span data-stu-id="1a792-280">EnableTeamCall : True</span></span>

<span data-ttu-id="1a792-281">EnableCallTransfer: true</span><span class="sxs-lookup"><span data-stu-id="1a792-281">EnableCallTransfer : True</span></span>

<span data-ttu-id="1a792-282">EnableCallPark: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-282">EnableCallPark : False</span></span>

<span data-ttu-id="1a792-283">EnableMaliciousCallTracing: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-283">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="1a792-284">EnableBWPolicyOverride: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-284">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="1a792-285">PreventPSTNTollBypass: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-285">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="1a792-286">Sie können auch Abfragen erstellen, die eine Teilmenge ihrer VoIP-Richtlinien zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="1a792-286">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="1a792-287">Dieser Befehl gibt beispielsweise alle VoIP-Richtlinien zurück, die die Anrufweiterleitung zulassen:</span><span class="sxs-lookup"><span data-stu-id="1a792-287">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="1a792-288">Und dieser Befehl gibt alle VoIP-Richtlinien zurück, die keine Anrufweiterleitung zulassen:</span><span class="sxs-lookup"><span data-stu-id="1a792-288">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="1a792-289">Verwenden Sie in Windows PowerShell das Cmdlet "Get-CsVoiceRouting", um Informationen zu Ihren VoIP-Routen zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="1a792-289">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="1a792-290">Dieser Befehl gibt Informationen wie diesen für alle VoIP-Routen zurück:</span><span class="sxs-lookup"><span data-stu-id="1a792-290">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="1a792-291">Identität: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="1a792-291">Identity : LocalRoute</span></span>

<span data-ttu-id="1a792-292">Priorität: 0</span><span class="sxs-lookup"><span data-stu-id="1a792-292">Priority : 0</span></span>

<span data-ttu-id="1a792-293">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a792-293">Description :</span></span>

<span data-ttu-id="1a792-294">NumberPattern: ^ (\\+ 1\[0-9\]{10}) $</span><span class="sxs-lookup"><span data-stu-id="1a792-294">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="1a792-295">PstnUsages :{}</span><span class="sxs-lookup"><span data-stu-id="1a792-295">PstnUsages : {}</span></span>

<span data-ttu-id="1a792-296">PstnGatewayList :{}</span><span class="sxs-lookup"><span data-stu-id="1a792-296">PstnGatewayList : {}</span></span>

<span data-ttu-id="1a792-297">Name: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="1a792-297">Name : LocalRoute</span></span>

<span data-ttu-id="1a792-298">SuppressCallerId :</span><span class="sxs-lookup"><span data-stu-id="1a792-298">SuppressCallerId :</span></span>

<span data-ttu-id="1a792-299">AlternateCallerId :</span><span class="sxs-lookup"><span data-stu-id="1a792-299">AlternateCallerId :</span></span>

<span data-ttu-id="1a792-300">Mit lync Server können Sie VoIP-Routen erstellen, die keine PSTN-Nutzung aufweisen, und kein PSTN-Gateway angeben.</span><span class="sxs-lookup"><span data-stu-id="1a792-300">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="1a792-301">Sie können jedoch keine Anrufe über eine VoIP-Route weiterleiten, für die diese beiden Eigenschaftswerte nicht konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="1a792-301">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="1a792-302">Aus diesem Grund ist es möglicherweise hilfreich, diesen Befehl in regelmäßigen Abständen auszuführen, wodurch die Identität einer VoIP-Route zurückgegeben wird, die keine PSTN-Nutzung aufweist:</span><span class="sxs-lookup"><span data-stu-id="1a792-302">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="1a792-303">Ebenso gibt dieser Befehl die Identität einer VoIP-Route zurück, die nicht für ein PSTN-Gateway konfiguriert wurde:</span><span class="sxs-lookup"><span data-stu-id="1a792-303">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="1a792-304">Überprüfen der Einstellungen der Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="1a792-304">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="1a792-305">Überprüfen Sie die Einstellungen der Konferenzzentrale für PSTN-Einwahlkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="1a792-305">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="1a792-306">Einstellungen der Konferenzzentrale können nur mit dem Cmdlet **Get-CsDialInConferencingConfiguration** abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1a792-306">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="1a792-307">Diese Einstellungen stehen in der lync Server-Systemsteuerung nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1a792-307">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="1a792-308">Verwenden Sie zum Anzeigen der Einstellungen der Konferenzzentrale einen Windows PowerShell-Befehl ähnlich der folgenden, der die globale Sammlung der Konferenz Aufsichts Einstellungen zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="1a792-308">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="1a792-309">Beachten Sie, dass die Einstellungen der Konferenzzentrale auch im Website Bereich konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="1a792-309">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="1a792-310">Wenn Sie Informationen zu allen Einstellungen der Konferenzzentrale zurückgeben möchten, verwenden Sie stattdessen folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="1a792-310">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="1a792-311">Das Cmdlet "Get-CsDialInConferencingConfiguration" gibt Daten ähnlich wie folgt zurück:</span><span class="sxs-lookup"><span data-stu-id="1a792-311">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="1a792-312">Identität: Global</span><span class="sxs-lookup"><span data-stu-id="1a792-312">Identity : Global</span></span>

<span data-ttu-id="1a792-313">EntryExitAnnouncementsType : UseNames</span><span class="sxs-lookup"><span data-stu-id="1a792-313">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="1a792-314">EnableNameRecording: true</span><span class="sxs-lookup"><span data-stu-id="1a792-314">EnableNameRecording : True</span></span>

<span data-ttu-id="1a792-315">EntryExitAnnouncementsEnabledByDefault: falsch</span><span class="sxs-lookup"><span data-stu-id="1a792-315">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="1a792-316">Wenn EntryExitAnnouncementsEnabledByDefault auf "false" festgelegt ist, bedeutet dies, dass die Konferenz Ankündigungen deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="1a792-316">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="1a792-317">Führen Sie zum Aktivieren von Eingabe-und Beendigungs Ankündigungen einen Windows PowerShell-Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="1a792-317">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1a792-318">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a792-318">See Also</span></span>


[<span data-ttu-id="1a792-319">Get-CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="1a792-319">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="1a792-320">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a792-320">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="1a792-321">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="1a792-321">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="1a792-322">Get-csaccessedgeconfiguration nicht angeben</span><span class="sxs-lookup"><span data-stu-id="1a792-322">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="1a792-323">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="1a792-323">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="1a792-324">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a792-324">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="1a792-325">Get-CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a792-325">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="1a792-326">Get-CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a792-326">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="1a792-327">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="1a792-327">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="1a792-328">Get-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="1a792-328">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="1a792-329">Get-CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a792-329">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

