---
title: Anforderungen an Sicherheit und Konfiguration für Enterprise-VoIP in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Zusammenfassung: Informationen Sie zu den Voraussetzungen für Sicherheit und Konfiguration für Enterprise-VoIP in Skype für Business Server 2015.'
ms.openlocfilehash: 400af6d42026007315e30a7706e9730901f90708
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="20ea8-103">Anforderungen an Sicherheit und Konfiguration für Enterprise-VoIP in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="20ea8-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="20ea8-104">**Zusammenfassung:** Informationen Sie zu den erforderlichen Komponenten Sicherheit und Konfiguration für Enterprise-VoIP in Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="20ea8-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="20ea8-105">Vor der Bereitstellung von Enterprise-VoIP, stellen Sie sicher, dass Ihre Infrastruktur die folgenden Anforderungen an Sicherheit, Benutzerkonfiguration, und szenariospezifische Hardware erfüllt.</span><span class="sxs-lookup"><span data-stu-id="20ea8-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="20ea8-106">Administrative Rechte und Zertifikatinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="20ea8-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="20ea8-107">Überprüfen Sie vor der Bereitstellung die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="20ea8-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="20ea8-108">Administratoren, die Enterprise-VoIP bereitstellen, sollten Mitglied der Gruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="20ea8-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="20ea8-109">Administratoren, die die Konfigurationsaufgaben ausführen, müssen über geeignete Rechte verfügen:</span><span class="sxs-lookup"><span data-stu-id="20ea8-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="20ea8-110">**CsVoiceAdministrator:** Diese Administratorrolle kann VoIP-Konfigurationsaufgaben ausführen, VoIP-Anwendungen verwalten und Endbenutzern VoIP-Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="20ea8-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="20ea8-p101">**CsUserAdministrator:** Diese Administratorrolle kann Benutzereigenschaften verwalten, z. B. die Aktivierung von Enterprise-VoIP für einen Benutzer. Diese Administratorrolle kann außerdem benutzerbasierte Richtlinien zuweisen. Hiervon ausgenommen sind die Archivierungsrichtlinie, das Verschieben von Benutzern, das Verwalten von Telefonen in öffentlichen Bereichen und das Verwalten von analogen Geräten.</span><span class="sxs-lookup"><span data-stu-id="20ea8-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="20ea8-113">**CsAdministrator:** Diese Administratorrolle kann sämtliche Aufgaben ausführen, die mit „CsVoiceAdministrator“ und „CsUserAdministrator“ ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="20ea8-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="20ea8-114">Eine Managed Key-Infrastruktur (MKI) wurde mithilfe einer Zertifizierungsstelleninfrastruktur von Microsoft oder einem Drittanbieter bereitgestellt und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="20ea8-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="20ea8-115">Ausführliche Informationen zu zertifikatanforderungen in Skype für Business Server finden Sie unter [umgebungsanforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20ea8-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="20ea8-116">Benutzerkonfiguration</span><span class="sxs-lookup"><span data-stu-id="20ea8-116">User configuration</span></span>

<span data-ttu-id="20ea8-117">Wenn Sie während der Front-End-Bereitstellung des Vermittlungsservers mit jedem Front-End-Pool oder Standard Edition-Server verbunden, wurden benutzereinstellungen für Enterprise-VoIP automatisch während der Installation der Dateien für diese Serverrollen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="20ea8-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="20ea8-118">Wenn Sie neu die Enterprise-VoIP-Arbeitslast zu diesem Zeitpunkt bereitstellen, bevor Sie mit der Bereitstellung beginnen, legen Sie eine primäre Rufnummer für jeden Benutzer, die Sie für Enterprise-VoIP aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="20ea8-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="20ea8-119">Als Administrator sind Sie dafür verantwortlich, die Eindeutigkeit dieser Nummer sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="20ea8-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="20ea8-120">Vor der Implementierung alle primären Telefon, dass Zahlen normalisiert werden müssen (ordnungsgemäß formatiert) und auf **Anschluss-URI** -Eigenschaft des Benutzers mithilfe der Skype für Business Server-Systemsteuerung kopiert.</span><span class="sxs-lookup"><span data-stu-id="20ea8-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="20ea8-121">Beispiele für primäre Rufnummern, die für eine Enterprise-VoIP-Bereitstellung erforderlich sind, finden Sie unter [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span><span class="sxs-lookup"><span data-stu-id="20ea8-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="20ea8-122">Nächste Schritte: Installieren von Dateien oder Konfigurieren der PSTN-Anbindung</span><span class="sxs-lookup"><span data-stu-id="20ea8-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="20ea8-123">Nachdem Sie sichergestellt haben, Software und der Umwelt Voraussetzungen für Enterprise-VoIP können Sie entweder:</span><span class="sxs-lookup"><span data-stu-id="20ea8-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="20ea8-124">Installieren Sie der Vermittlungsserver, wie unter [Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype für Business Server 2015](deploy-a-mediation-server.md), aber nur, wenn Sie einen eigenständigen Vermittlungsserver oder einen Pool bereitstellen, da der Vermittlungsserver installiert sind, als Teil der Vorderseite möchten End-Pool oder Standard Edition-Server-Bereitstellungsprozess beim kombiniert.</span><span class="sxs-lookup"><span data-stu-id="20ea8-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server 2015](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="20ea8-125">Oder: Konfigurieren von Einstellungen für das Anrufrouting für Enterprise-VoIP-Benutzer, wie beschrieben unter [Konfigurieren von Trunks in Skype für Business Server 2015](configure-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="20ea8-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server 2015](configure-trunks.md).</span></span>
    

