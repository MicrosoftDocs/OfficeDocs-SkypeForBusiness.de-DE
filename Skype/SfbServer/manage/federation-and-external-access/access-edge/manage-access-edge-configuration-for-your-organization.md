---
title: Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem eine oder mehrere Edgeserver bereitstellen, müssen Sie die Typen von externen Domäne oder Anbieter zugreifen, Zugriff durch Remotebenutzer und Zugriff anonymer Benutzer auf Konferenzen über die Edge-Server, die für Ihre Organisation unterstützt werden aktivieren.
ms.openlocfilehash: 40fdbd6e728276897e4901c849dc0e2284635ecf
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222919"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="88474-103">Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="88474-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="88474-104">Nachdem eine oder mehrere Edgeserver bereitstellen, müssen Sie die Typen von externen Domäne oder Anbieter zugreifen, Zugriff durch Remotebenutzer und Zugriff anonymer Benutzer auf Konferenzen über die Edge-Server, die für Ihre Organisation unterstützt werden aktivieren.</span><span class="sxs-lookup"><span data-stu-id="88474-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="88474-105">Zu diesen Optionen gehören die folgenden Zugriffsarten, die über die Seite **Konfiguration für Zugriffsedge** konfiguriert werden können:</span><span class="sxs-lookup"><span data-stu-id="88474-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="88474-106">**Aktivieren Sie den Verbund und Verbindung mit öffentlichen Sofortnachrichtendiensten**   aktivieren Sie diese Option, wenn Sie Benutzerzugriff auf verbundpartnerdomänen unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="88474-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="88474-107">Diese Einstellung gilt für SIP den Verbund konfiguriert für globale, Standort- oder Benutzer Bereiche auf der Seite **Richtlinie für den externen Zugriff** .</span><span class="sxs-lookup"><span data-stu-id="88474-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="88474-108">Bei verbundeinstellungen anwenden müssen Sie die verbundunterstützung auf beiden Seiten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="88474-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="88474-109">Zwei Optionen vorhanden, die optionale Einstellungen für sind wie Verbundpartnern erkannt werden, und ob Haftungsausschlüsse Archivierung (Benachrichtigung den Verbundkontakten angezeigt, dass Sie mit die Bereitstellung kommunizieren muss Archivierung aktiviert und die Kommunikation Details archiviert werden) an Kontakte gesendet:</span><span class="sxs-lookup"><span data-stu-id="88474-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="88474-110">**Aktivieren Sie Partner Domäne Discovery**   Wenn diese Option aktiviert die automatische Ermittlung von Domänen, die Sie einen Verbund mit konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="88474-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="88474-111">Skype für Business Server verwendet Domain Name System (DNS) Datensätze versuchen, nicht in der Liste zugelassener Domänen aufgeführte Domänen erkennen automatisch Auswerten von eingehenden Datenverkehr von Verbundpartnern ermittelten und eingeschränkt oder blockieren, die basierend auf der Vertrauenswürdigkeit Datenverkehr die Ebene, Umfang des Datenverkehrs und administratoreinstellungen.</span><span class="sxs-lookup"><span data-stu-id="88474-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="88474-112">Wenn Sie diese Option nicht auswählen, wird partnerbenutzerzugriff für Benutzer in den Domänen nur aktiviert, die Sie in der Liste der zugelassenen Domänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="88474-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="88474-113">Unabhängig davon, ob Sie diese Option auswählen, können Sie angeben, dass diese Person Domänen blockiert oder zulässig, einschließlich Einschränken des Zugriffs auf bestimmten Servern in der Partnerdomäne Zugriffs-edgedienst ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="88474-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="88474-114">Weitere Informationen hierzu finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="88474-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="88474-115">**Archivierungshaftungsausschlusses an Verbundpartner senden**   durch Auswählen dieser Option ermöglicht das Senden einer Archivierung Haftungsausschluss-Nachricht an Verbundpartner, die sie darüber informiert, dass Communications Details aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="88474-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="88474-116">Wenn Sie mit verbundpartnerdomänen externe Kommunikation archivieren, sollten Sie den Archivierungshaftungsausschluss für Partner zu warnen, wenn ihre Nachrichten und Kommunikation Details von Ihrer Bereitstellung archiviert werden aktivieren.</span><span class="sxs-lookup"><span data-stu-id="88474-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="88474-117">Ausführliche Informationen zum Archivierung finden Sie unter [Aktivieren oder Deaktivieren einer Archiving Disclaimer an Verbundpartner senden](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="88474-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="88474-118">**Aktivieren des Zugriffs durch Remotebenutzer**   aktivieren Sie diese Option aus, wenn Sie möchten, dass Benutzer in Ihrer Organisation, die außerhalb der Firewall, wie Telearbeiter und Benutzer, die viel unterwegs sind Skype für Business Server herstellen können, sind.</span><span class="sxs-lookup"><span data-stu-id="88474-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="88474-119">Weitere Informationen hierzu finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="88474-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="88474-120">**Aktivieren Sie anonyme Benutzern Konferenzen Zugriff auf**   aktivieren Sie diese Option aus, wenn Sie interne Benutzern an externe anonyme Benutzer zu Konferenzen einladen, die sie organisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="88474-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="88474-121">Durch Aktivieren dieser Einstellung kann anonyme Benutzer nur für Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="88474-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="88474-122">Neben der Aktivierung Zugriff durch externe Benutzer unterstützen, auch konfigurieren Sie Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Ihrer Organisation der Verwendung bevor keinerlei Zugriff durch externe Benutzer für Benutzer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="88474-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="88474-123">Ausführliche Informationen zum Erstellen, konfigurieren und Anwenden von Richtlinien für den Zugriff externer Benutzer finden Sie unter [Manage externe Zugriffsrichtlinie für Ihre Organisation](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="88474-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="88474-124">**Anzeigen von Zugriffs-Edgeservers-Konfigurationsinformationen mithilfe von Windows PowerShell-cmdlets**</span><span class="sxs-lookup"><span data-stu-id="88474-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="88474-125">Zugreifen auf Edge-Konfigurationsinformationen kann mithilfe von Windows PowerShell und das Cmdlet " **Get-CsAccessEdgeConfiguration** " angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="88474-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="88474-126">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="88474-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="88474-127">Anzeigen von Informationen zu allen Access Edge-Konfigurationseinstellungen, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="88474-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="88474-128">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="88474-128">That will return information similar to this:</span></span>
    
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

