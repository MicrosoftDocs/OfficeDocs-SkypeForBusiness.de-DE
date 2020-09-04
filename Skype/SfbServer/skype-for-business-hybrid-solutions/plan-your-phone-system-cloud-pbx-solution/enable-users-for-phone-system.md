---
title: Ermöglichen, dass Benutzer des Telefonsystems eine lokale Festnetzanbindung in Skype for Business Server herstellen
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: In diesem Thema wird beschrieben, wie Sie Benutzer für das Telefon System mit lokaler PSTN-Konnektivität aktivieren. Bevor Sie die Schritte in diesem Thema durchführen, sollten Sie folgendes lesen:.
ms.openlocfilehash: 7fb1ae9ee013dafbf0de91611bacb68f685daac8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359141"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="ecb8f-104">Ermöglichen, dass Benutzer des Telefonsystems eine lokale Festnetzanbindung in Skype for Business Server herstellen</span><span class="sxs-lookup"><span data-stu-id="ecb8f-104">Enable users for Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="ecb8f-105">In diesem Thema wird beschrieben, wie Sie Benutzer für das Telefon System mit lokaler PSTN-Konnektivität aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ecb8f-105">This topic describes how to enable users for Phone System with on-premises PSTN connectivity.</span></span> <span data-ttu-id="ecb8f-106">Bevor Sie die Schritte in diesem Thema durchführen, sollten Sie folgendes lesen:.</span><span class="sxs-lookup"><span data-stu-id="ecb8f-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="ecb8f-107">Informationen zum Einrichten von Hybrid Konnektivität finden Sie unter [Planen der Hybrid Konnektivität zwischen Skype for Business Server und Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) und [Bereitstellen von Hybrid Konnektivität zwischen Skype for Business Server und Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="ecb8f-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="ecb8f-108">Informationen zum Planen der Bereitstellung finden Sie unter [Plan Phone System with on-premises PSTN Connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="ecb8f-108">To learn about planning your deployment, see [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="ecb8f-109">Weitere Informationen zum Telefon System einschließlich Lizenzierung und Plänen finden Sie unter [PSTN-Anrufpläne für Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span><span class="sxs-lookup"><span data-stu-id="ecb8f-109">To learn more about Phone System, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
> [!Important]
> <span data-ttu-id="ecb8f-110">Skype for Business Online werden am 31. Juli 2021 zurückgezogen, nach dem der Zugriff auf den Dienst nicht mehr möglich ist.</span><span class="sxs-lookup"><span data-stu-id="ecb8f-110">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="ecb8f-111">Darüber hinaus wird die PSTN-Konnektivität zwischen Ihrer lokalen Umgebung unabhängig davon, ob über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ecb8f-111">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="ecb8f-112">Hier erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.</span><span class="sxs-lookup"><span data-stu-id="ecb8f-112">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a><span data-ttu-id="ecb8f-113">Verschieben von Benutzern in ein Telefon System mit lokaler PSTN-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="ecb8f-113">Moving users to Phone System with on-premises PSTN connectivity</span></span>

<span data-ttu-id="ecb8f-114">Bevor Sie Ihre Benutzer in Skype for Business Online verschieben, wird empfohlen, dass Sie Ihre Benutzer lokal in Skype for Business Server oder lync Server 2013 aktivieren und dann Online verschieben.</span><span class="sxs-lookup"><span data-stu-id="ecb8f-114">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="ecb8f-115">Weitere Informationen finden Sie unter [Planen der Hybrid Konnektivität zwischen Skype for Business Server und Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) und im Abschnitt "spezielle Überlegungen" unter [Aktivieren der Benutzer für Enterprise-VoIP lokal](enable-the-users-for-enterprise-voice-on-premises.md) (durchgeführt, während die Benutzer lokal verwaltet werden).</span><span class="sxs-lookup"><span data-stu-id="ecb8f-115">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="ecb8f-116">Alle Benutzer müssen in Active Directory lokal erstellt und mit der unterstützten Version von Azure AD Connector mit Microsoft 365 oder Office 365 synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ecb8f-116">All users must be created in Active Directory on premises and synchronized to Microsoft 365 or Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="ecb8f-117">Sie können Benutzer für das Telefon System nicht in Office 365 aktivieren, die direkt in Azure AD erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="ecb8f-117">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="ecb8f-118">Wenn Sie das Telefon System mit lokaler PSTN-Konnektivität für einen Benutzer aktivieren möchten, der in Azure AD erstellt wurde, müssen Sie ein neues Konto für diesen Benutzer in Ihrer lokalen AD erstellen, das Konto lokal konfigurieren und dann das Konto mithilfe einer unterstützten Version des Azure AD Connector-Tools synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="ecb8f-118">If you want to enable Phone System with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="ecb8f-119">Wenn Sie einen Benutzer für das Telefon System mit lokaler PSTN-Konnektivität aktivieren und anschließend in Skype for Business Online verschieben möchten, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="ecb8f-119">Enabling a user for Phone System with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="ecb8f-120">[Aktivieren Sie die Benutzer für Enterprise-VoIP lokal](enable-the-users-for-enterprise-voice-on-premises.md) (durchgeführt, während die Benutzer lokal verwaltet werden).</span><span class="sxs-lookup"><span data-stu-id="ecb8f-120">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="ecb8f-121">[Zuweisen einer VoIP-Routing Richtlinie](assign-a-voice-routing-policy.md) (durchgeführt, während die Benutzer lokal verwaltet werden).</span><span class="sxs-lookup"><span data-stu-id="ecb8f-121">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="ecb8f-122">[Synchronisieren von Benutzern mit der Cloud und Zuweisen von Lizenzen](synchronize-users-to-the-cloud-and-assign-licenses.md) (erfolgt mithilfe von Office 365).</span><span class="sxs-lookup"><span data-stu-id="ecb8f-122">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="ecb8f-123">[Lokale Benutzer werden in Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (mit Windows PowerShell lokal, jedoch mit den Anmeldeinformationen des Office 365 Administrators) verlagert.</span><span class="sxs-lookup"><span data-stu-id="ecb8f-123">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="ecb8f-124">[Aktivieren von Benutzern für Enterprise-VoIP-Online-und Telefon System-Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (wird mithilfe von Remote-PowerShell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ecb8f-124">[Enable users for Enterprise Voice online and Phone System Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

