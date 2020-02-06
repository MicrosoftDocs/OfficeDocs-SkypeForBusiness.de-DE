---
title: Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Nachdem Sie einen oder mehrere Edgeserver bereitgestellt haben, müssen Sie die Typen des externen Domänen-oder Anbieter Zugriffs, den Remotebenutzerzugriff und den anonymen Benutzer Zugriff auf Konferenzen über die Edgeserver aktivieren, die für Ihre Organisation unterstützt werden.
ms.openlocfilehash: 7308d6914f3f6d79cd217a31c0246c6f2d189516
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818346"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="7e488-103">Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="7e488-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="7e488-104">Nachdem Sie einen oder mehrere Edgeserver bereitgestellt haben, müssen Sie die Typen des externen Domänen-oder Anbieter Zugriffs, den Remotebenutzerzugriff und den anonymen Benutzer Zugriff auf Konferenzen über die Edgeserver aktivieren, die für Ihre Organisation unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7e488-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="7e488-105">Zu diesen Optionen gehören die folgenden Zugriffsarten, die über die Seite " **Zugriffs-Edge-Konfiguration** " konfiguriert werden können:</span><span class="sxs-lookup"><span data-stu-id="7e488-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="7e488-106">**Aktivieren von Föderations-und öffentlichen Chat Verbindungen**   aktivieren Sie diese Option, wenn Sie den Benutzer Zugriff auf Partnerdomänen für Föderationen unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="7e488-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="7e488-107">Diese Einstellung gilt für SIP-Föderationen, die für globale, Website-oder benutzerbereiche auf der Seite " **externe Zugriffsrichtlinie** " konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="7e488-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="7e488-108">Damit die Verbund Einstellungen angewendet werden, müssen Sie die Verbundunterstützung auf beiden Seiten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7e488-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="7e488-109">Es gibt zwei Optionen, die optionale Einstellungen für die Erkennung von Verbundpartnern sind, und ob Archivierungs verzichte (Benachrichtigung an verbundene Kontakte, mit denen Sie kommunizieren, dass Ihre Bereitstellung die Archivierung aktiviert hat und dass die Kommunikation Details werden archiviert) werden an die Kontakte weitergeleitet:</span><span class="sxs-lookup"><span data-stu-id="7e488-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="7e488-110">**Aktivieren der Partnerdomänen Ermittlung**   durch Auswahl dieser Option wird die automatische Ermittlung von Domänen ermöglicht, mit denen Sie eine Föderation durchsetzen können.</span><span class="sxs-lookup"><span data-stu-id="7e488-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="7e488-111">Skype for Business Server verwendet DNS-Einträge (Domain Name System), um zu ermitteln, welche Domänen nicht in der Liste der zulässigen Domänen aufgeführt sind, und die eingehenden Datenverkehr von ermittelten Partner Partnern automatisch auswerten und den Datenverkehr basierend auf Vertrauen einschränken oder blockieren. Ebene, Umfang des Datenverkehrs und Administratoreinstellungen.</span><span class="sxs-lookup"><span data-stu-id="7e488-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="7e488-112">Wenn Sie diese Option nicht auswählen, wird der Verbundbenutzer Zugriff nur für Benutzer in den Domänen aktiviert, die Sie in die Liste zugelassene Domänen aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="7e488-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="7e488-113">Unabhängig davon, ob Sie diese Option auswählen, können Sie angeben, dass einzelne Domänen blockiert oder zulässig sein sollen, einschließlich der Beschränkung des Zugriffs auf bestimmte Server, auf denen der Access-Edgedienst in der Verbunddomäne ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7e488-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="7e488-114">Ausführliche Informationen finden Sie unter [Konfigurieren der Unterstützung für zugelassene externe Domänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="7e488-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="7e488-115">**Archivierungs Ausschluss an verbundene Partner**   senden wenn Sie diese Option aktivieren, können Sie eine Nachricht zur Archivierung des Disclaimers an verbundene Partner senden, die Ihnen mitteilt, dass Kommunikationsdetails aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="7e488-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="7e488-116">Wenn Sie die externe Kommunikation mit Verbundpartner Domänen archivieren, sollten Sie die Benachrichtigung über Archivierungs Verzicht aktivieren, um die Partner zu warnen, dass Ihre Nachrichten und Kommunikationsdetails von Ihrer Bereitstellung archiviert werden.</span><span class="sxs-lookup"><span data-stu-id="7e488-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="7e488-117">Details zur Archivierung finden Sie unter [Aktivieren oder Deaktivieren des Sendens einer Archivierungs Klausel an den Verbundpartner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="7e488-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="7e488-118">**Aktivieren des Remotebenutzerzugriffs**   aktivieren Sie diese Option, wenn Sie möchten, dass Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, wie Telecommuter und Benutzer, die unterwegs sind, eine Verbindung mit Skype for Business Server herstellen können.</span><span class="sxs-lookup"><span data-stu-id="7e488-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="7e488-119">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="7e488-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="7e488-120">**Aktivieren von anonymen Benutzern für den Zugriff auf Konferenzen**   aktivieren Sie diese Option, wenn interne Benutzer externe anonyme Benutzer zu Konferenzen einladen möchten, die Sie organisieren.</span><span class="sxs-lookup"><span data-stu-id="7e488-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="7e488-121">Wenn Sie diese Einstellung aktivieren, können anonyme Benutzer nur für Konferenzen zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="7e488-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="7e488-122">Neben der Unterstützung für den Zugriff durch externe Benutzer können Sie auch Richtlinien konfigurieren, um die Verwendung des Remotebenutzerzugriffs in Ihrer Organisation zu steuern, bevor Benutzer Zugriff auf externe Benutzer erhalten.</span><span class="sxs-lookup"><span data-stu-id="7e488-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="7e488-123">Details zum Erstellen, konfigurieren und Anwenden von Richtlinien für den Zugriff durch externe Benutzer finden Sie unter [Verwalten der Richtlinien für den externen Zugriff für Ihre Organisation](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="7e488-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="7e488-124">**Anzeigen von Informationen zur Access-Edge-Konfiguration mithilfe von Windows PowerShell-Cmdlets**</span><span class="sxs-lookup"><span data-stu-id="7e488-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="7e488-125">Informationen zur Access-Edge-Konfiguration können mithilfe von Windows PowerShell und dem Cmdlet **Get-csaccessedgeconfiguration nicht angeben** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7e488-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="7e488-126">Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7e488-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="7e488-127">Wenn Sie Informationen zu allen Einstellungen für die Zugriffs-Edge-Konfiguration anzeigen möchten, geben Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="7e488-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="7e488-128">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="7e488-128">That will return information similar to this:</span></span>
    
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

