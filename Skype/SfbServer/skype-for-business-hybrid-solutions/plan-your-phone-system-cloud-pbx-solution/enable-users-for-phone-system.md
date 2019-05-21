---
title: Aktivieren von Benutzern für das Telefon System in Office 365 mit lokalem PSTN-Konnektivität in Skype for Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
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
description: 'In diesem Thema wird beschrieben, wie Benutzer für Telefonsysteme in Office 365 mit lokalen PSTN-Konnektivität aktiviert werden. Bevor Sie die Schritte in diesem Thema ausführen, sollten Sie folgendes lesen:'
ms.openlocfilehash: c8870cce90963e3a8d4e42de008df3eee779e52a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287461"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="7bfce-104">Aktivieren von Benutzern für das Telefon System in Office 365 mit lokalem PSTN-Konnektivität in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7bfce-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="7bfce-105">In diesem Thema wird beschrieben, wie Benutzer für Telefonsysteme in Office 365 mit lokalen PSTN-Konnektivität aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="7bfce-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="7bfce-106">Bevor Sie die Schritte in diesem Thema ausführen, sollten Sie folgendes lesen:</span><span class="sxs-lookup"><span data-stu-id="7bfce-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="7bfce-107">Informationen zum Einrichten von Hybrid Konnektivität finden Sie unter [Planen der Hybrid Konnektivität zwischen Skype for Business Server und Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) und [Bereitstellen von Hybrid Konnektivität zwischen Skype for Business Server und Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="7bfce-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="7bfce-108">Informationen zum Planen der Bereitstellung finden Sie unter [Planen des Telefonsystems in Office 365 mit lokalem PSTN-Konnektivität in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="7bfce-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="7bfce-109">Weitere Informationen zu Telefonsystemen in Office 365, einschließlich Lizenzierung und Pläne, finden Sie unter [PSTN-Anrufpläne für Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span><span class="sxs-lookup"><span data-stu-id="7bfce-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="7bfce-110">Verschieben von Benutzern in das Telefon System in Office 365 mit lokalen PSTN-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="7bfce-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="7bfce-111">Bevor Sie Ihre Benutzer in Skype for Business Online verschieben, empfiehlt es sich, die Benutzer lokal in Skype for Business Server oder lync Server 2013 zu aktivieren und dann online zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="7bfce-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="7bfce-112">Weitere Informationen finden Sie unter [Planen einer hybriden Konnektivität zwischen Skype for Business Server und Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) und dem Abschnitt "besondere Aspekte" des Abschnitts " [Benutzer für Enterprise-VoIP aktivieren](enable-the-users-for-enterprise-voice-on-premises.md) " (durchgeführt, während die Benutzer verwaltet werden Lokal).</span><span class="sxs-lookup"><span data-stu-id="7bfce-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="7bfce-113">Alle Benutzer müssen mit der unterstützten Version von Azure AD Connector in Active Directory lokal erstellt und mit Office 365 synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7bfce-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="7bfce-114">Sie können Benutzer für Telefonsysteme in Office 365, die direkt in Azure AD erstellt wurden, nicht aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7bfce-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="7bfce-115">Wenn Sie das Telefon System in Office 365 mit lokalen PSTN-Konnektivität für einen Benutzer aktivieren möchten, der in Azure AD erstellt wurde, müssen Sie ein neues Konto für diesen Benutzer in Ihrer lokalen Anzeige erstellen, das Konto lokal konfigurieren und dann das Konto mithilfe von eine unterstützte Version des Azure AD Connector-Tools.</span><span class="sxs-lookup"><span data-stu-id="7bfce-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="7bfce-116">Wenn Sie einen Benutzer für das Telefon System in Office 365 mit lokalen PSTN-Konnektivität aktivieren und dann in Skype for Business Online verschieben, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="7bfce-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="7bfce-117">[Aktivieren der Benutzer für Enterprise-VoIP lokal](enable-the-users-for-enterprise-voice-on-premises.md) (durchgeführt, während die Benutzer lokal gehostet werden).</span><span class="sxs-lookup"><span data-stu-id="7bfce-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="7bfce-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (durchgeführt, während die Benutzer lokal verwaltet werden).</span><span class="sxs-lookup"><span data-stu-id="7bfce-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="7bfce-119">[Synchronisieren von Benutzern mit der Cloud und Zuweisen von Lizenzen](synchronize-users-to-the-cloud-and-assign-licenses.md) (durchgeführt mit Office 365).</span><span class="sxs-lookup"><span data-stu-id="7bfce-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="7bfce-120">[Lokale Benutzer in Skype for Business Online verschieben](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (durchgeführt mit Windows PowerShell lokal, aber mit den Office 365-Administratoranmeldeinformationen).</span><span class="sxs-lookup"><span data-stu-id="7bfce-120">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="7bfce-121">[Aktivieren von Benutzern für Enterprise Voice Online und Telefon System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (wird mithilfe von Remote-PowerShell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7bfce-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

