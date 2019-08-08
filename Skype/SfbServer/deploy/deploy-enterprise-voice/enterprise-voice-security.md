---
title: Voraussetzungen für Sicherheit und Konfiguration für Enterprise-VoIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Zusammenfassung: Informationen zu den Sicherheits-und Konfigurationsvoraussetzungen für Enterprise-VoIP in Skype for Business Server.'
ms.openlocfilehash: 70acac97bd2a3554c0613f64bdbf93f64811a0b0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240324"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="d5794-103">Voraussetzungen für Sicherheit und Konfiguration für Enterprise-VoIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d5794-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="d5794-104">**Zusammenfassung:** Informieren Sie sich über die Voraussetzungen für Sicherheit und Konfiguration für Enterprise-VoIP in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d5794-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="d5794-105">Überprüfen Sie vor der Bereitstellung von Enterprise-VoIP, ob Ihre Infrastruktur die folgenden Sicherheits-, Benutzer Konfigurations-und Szenario-spezifischen Hardwarevoraussetzungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="d5794-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="d5794-106">Administrative Rechte und Zertifikatinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="d5794-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="d5794-107">Überprüfen Sie vor der Bereitstellung die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="d5794-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="d5794-108">Administratoren, die Enterprise-VoIP bereitstellen, sollten Mitglieder der RTCUniversalServerAdmins-Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="d5794-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="d5794-109">Administratoren, die die Konfigurationsaufgaben ausführen, müssen über geeignete Rechte verfügen:</span><span class="sxs-lookup"><span data-stu-id="d5794-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="d5794-110">**CsVoiceAdministrator:** Diese Administratorrolle kann VoIP-Konfigurationsaufgaben ausführen, VoIP-Anwendungen verwalten und Endbenutzern VoIP-Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d5794-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="d5794-p101">**CsUserAdministrator:** Diese Administratorrolle kann Benutzereigenschaften verwalten, z. B. die Aktivierung von Enterprise-VoIP für einen Benutzer. Diese Administratorrolle kann außerdem benutzerbasierte Richtlinien zuweisen. Hiervon ausgenommen sind die Archivierungsrichtlinie, das Verschieben von Benutzern, das Verwalten von Telefonen in öffentlichen Bereichen und das Verwalten von analogen Geräten.</span><span class="sxs-lookup"><span data-stu-id="d5794-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="d5794-113">**CsAdministrator:** Diese Administratorrolle kann sämtliche Aufgaben ausführen, die mit „CsVoiceAdministrator“ und „CsUserAdministrator“ ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="d5794-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="d5794-114">Eine Managed Key-Infrastruktur (MKI) wurde mithilfe einer Zertifizierungsstelleninfrastruktur von Microsoft oder einem Drittanbieter bereitgestellt und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="d5794-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d5794-115">Details zu den Zertifikatanforderungen in Skype for Business Server finden Sie unter [Umweltanforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder [Server Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5794-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="d5794-116">Benutzerkonfiguration</span><span class="sxs-lookup"><span data-stu-id="d5794-116">User configuration</span></span>

<span data-ttu-id="d5794-117">Wenn Sie den Vermittlungsserver mit jedem Front-End-Pool oder Standard Edition-Server während der Front-End-Bereitstellung zusammengestellt haben, wurden die für Enterprise-VoIP erforderlichen Benutzereinstellungen während der Installation der Dateien für diese Server Rollen automatisch konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="d5794-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="d5794-118">Wenn Sie die Enterprise-VoIP-Arbeitsauslastung zu diesem Zeitpunkt neu bereitstellen, bevor Sie mit dem Bereitstellungsprozess beginnen, legen Sie für jeden Benutzer, den Sie für Enterprise-VoIP aktivieren möchten, eine primäre Telefonnummer fest.</span><span class="sxs-lookup"><span data-stu-id="d5794-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="d5794-119">Als Administrator sind Sie dafür verantwortlich, die Eindeutigkeit dieser Nummer sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="d5794-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="d5794-120">Vor der Implementierung müssen alle primären Telefonnummern normalisiert (korrekt formatiert) und mithilfe der Skype for Business Server-Systemsteuerung in die Eigenschaft des jeweiligen Benutzer- **URI** kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="d5794-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d5794-121">Beispiele für primäre Rufnummern, die für eine Enterprise-VoIP-Bereitstellung erforderlich sind, finden Sie unter [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span><span class="sxs-lookup"><span data-stu-id="d5794-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="d5794-122">Nächste Schritte: Installieren von Dateien oder Konfigurieren der PSTN-Anbindung</span><span class="sxs-lookup"><span data-stu-id="d5794-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="d5794-123">Nach der Überprüfung der Software-und Umgebungsvoraussetzungen für Enterprise-VoIP können Sie entweder:</span><span class="sxs-lookup"><span data-stu-id="d5794-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="d5794-124">Installieren Sie den Vermittlungsserver, wie unter [Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server](deploy-a-mediation-server.md)beschrieben, aber nur, wenn Sie einen eigenständigen Vermittlungsserver oder-Pool bereitstellen möchten, weil Vermittlungsserver als Teil des Front-End installiert werden. Pool-oder Standard Edition-Serverbereitstellungsprozess, wenn diese zusammengestellt sind.</span><span class="sxs-lookup"><span data-stu-id="d5794-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="d5794-125">Oder beginnen Sie mit der Konfiguration von Einstellungen für die Weiterleitung von Anrufen für Enterprise-VoIP-Benutzer, wie unter [Konfigurieren von Trunks in Skype for Business Server](configure-trunks.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d5794-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

