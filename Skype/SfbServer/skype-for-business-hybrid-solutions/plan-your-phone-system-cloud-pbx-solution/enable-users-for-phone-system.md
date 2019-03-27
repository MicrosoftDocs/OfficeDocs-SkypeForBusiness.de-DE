---
title: Aktivieren von Benutzern für Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität in Skype für Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: In diesem Thema wird beschrieben, wie Benutzer mit lokalen PSTN-Anbindung für Telefonsystem in Office 365 zu aktivieren. Vor dem Durchführen der Schritte in diesem Thema sollten Sie Folgendes lesen:.
ms.openlocfilehash: a3eec7adbd4897889cbc2ef8c7e985231c53bc99
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889217"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="9243f-104">Aktivieren von Benutzern für Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="9243f-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="9243f-105">In diesem Thema wird beschrieben, wie Benutzer mit lokalen PSTN-Anbindung für Telefonsystem in Office 365 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9243f-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="9243f-106">Vor dem Durchführen der Schritte in diesem Thema sollten Sie Folgendes lesen:.</span><span class="sxs-lookup"><span data-stu-id="9243f-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="9243f-107">Weitere Informationen zum Einrichten von hybridkonnektivität finden Sie unter [hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online planen](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) und [Bereitstellen von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="9243f-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="9243f-108">Informationen zur Planung der Bereitstellung finden Sie [Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität in Skype für Business Server planen](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="9243f-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="9243f-109">Weitere Informationen zum Telefonsystem in Office 365, einschließlich der Lizenzierung und Pläne, finden Sie unter [PSTN aufrufen Abonnements Skype für Unternehmen](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span><span class="sxs-lookup"><span data-stu-id="9243f-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="9243f-110">Migrieren von Benutzern zu Telefonsystem in Office 365 mit lokalen PSTN-Anbindung</span><span class="sxs-lookup"><span data-stu-id="9243f-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="9243f-111">Bevor Sie Ihre Benutzer in Skype für Business Online verschieben, wird empfohlen, dass Sie Ihre Benutzer lokal in Skype für Business Server oder Lync Server 2013 aktivieren, und verschieben Sie sie online.</span><span class="sxs-lookup"><span data-stu-id="9243f-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="9243f-112">Weitere Informationen finden Sie unter [Planen von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) und im Abschnitt besondere Aspekte [aktivieren die Benutzer für Enterprise-VoIP lokal](enable-the-users-for-enterprise-voice-on-premises.md) ausgeführt wird (während der Benutzer verwaltet werden lokal).</span><span class="sxs-lookup"><span data-stu-id="9243f-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="9243f-113">Alle Benutzer müssen in Active Directory lokal erstellt und zu Office 365 mit der unterstützten Version des Azure AD-Connector synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9243f-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="9243f-114">Benutzer kann nicht aktiviert werden, für Telefonsystem in Office 365, die direkt in Azure AD erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="9243f-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="9243f-115">Wenn Sie möchten Telefonsystem in Office 365 mit lokalen PSTN-Anbindung für einen Benutzer zu aktivieren, die in Azure AD erstellt wurde, müssen Sie zum Erstellen eines neuen Kontos für diesen Benutzer in Ihrer lokalen AD, Konto lokale konfigurieren, und klicken Sie dann synchronisieren das Konto verwenden eine unterstützte Version des Azure AD Verbinder.</span><span class="sxs-lookup"><span data-stu-id="9243f-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="9243f-116">Aktivieren eines Benutzers für Telefonsystem in Office 365 mit lokalen PSTN-Anbindung und anschließendes Verschieben auf Skype für Business Online müssen die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9243f-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="9243f-117">[Aktivieren Sie die Benutzer für Enterprise-VoIP lokal](enable-the-users-for-enterprise-voice-on-premises.md) (ausgeführt, während die Benutzer befinden sich lokal).</span><span class="sxs-lookup"><span data-stu-id="9243f-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="9243f-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (durchgeführt, während die Benutzer lokal verwaltet werden).</span><span class="sxs-lookup"><span data-stu-id="9243f-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="9243f-119">[Synchronisieren von Benutzern, die Lizenzen Cloud und zuweisen](synchronize-users-to-the-cloud-and-assign-licenses.md) (erfolgt mithilfe von Office 365).</span><span class="sxs-lookup"><span data-stu-id="9243f-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="9243f-120">[Verschieben Sie lokale Benutzer in Skype für Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (erfolgt mithilfe von Windows PowerShell: lokal, aber Ihre Office 365-Administrator-Anmeldeinformationen verwenden).</span><span class="sxs-lookup"><span data-stu-id="9243f-120">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="9243f-121">[Aktivieren von Benutzern für Enterprise-VoIP online und Telefonsystem in Office 365-Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (mithilfe von Remote-PowerShell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9243f-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

