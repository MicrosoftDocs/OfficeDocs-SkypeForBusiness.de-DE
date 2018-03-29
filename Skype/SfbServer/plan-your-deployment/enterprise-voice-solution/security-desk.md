---
title: Einbinden des Sicherheitsdesks in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Planen der sicherheitsdesk Ihrer Organisation in einer E9-1-1-Bereitstellung in Skype für Business Server Enterprise-VoIP eingeschlossen.
ms.openlocfilehash: 952d10a4547ec91452e9ea60f43c58c70c04c7c6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="include-the-security-desk-in-skype-for-business-server-2015"></a><span data-ttu-id="663cb-103">Einbinden des Sicherheitsdesks in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="663cb-103">Include the security desk in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="663cb-104">Planen der sicherheitsdesk Ihrer Organisation in einer E9-1-1-Bereitstellung in Skype für Business Server Enterprise-VoIP eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="663cb-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="663cb-p101">In Ihrem Unternehmen soll möglicherweise das Sicherheitsdesk in die Konfiguration für Notrufe eingebunden werden. Um entscheiden zu können, wie das Sicherheitsdesk in Ihre E9-1-1-Bereitstellung integriert werden kann, müssen Sie die folgenden Fragen beantworten.</span><span class="sxs-lookup"><span data-stu-id="663cb-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="663cb-107">**Soll das Sicherheitsdesk benachrichtigt werden, wenn ein Notruf abgesetzt wird?**</span><span class="sxs-lookup"><span data-stu-id="663cb-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="663cb-108">Sie können die Standortrichtlinie konfigurieren, sodass Skype für Business Server instant messaging (IM)-Benachrichtigungen an die Skype für Business SIP-Adressen des Sicherheitspersonals für eine oder mehrere sendet.</span><span class="sxs-lookup"><span data-stu-id="663cb-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="663cb-109">Diese Warnungen enthalten die Namen sowie die Anzahl und Standort der Person, die den Notruf platzieren und Sicherheitspersonals Unterstützung bei der Notfallsituation erleichtern.</span><span class="sxs-lookup"><span data-stu-id="663cb-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="663cb-110">**Möchten Sie für Notrufe eine Konferenzschaltung mit dem Sicherheitsdesk einrichten?**</span><span class="sxs-lookup"><span data-stu-id="663cb-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="663cb-p103">Sofern dies vom Anbieter für die Notrufunterstützung unterstützt wird, können Sie in der Ortungsrichtlinie eine Rückrufnummer für Notrufe einschließen. Diese Nummer wird vom Anbieter verwendet, um für Notrufe eine Konferenzschaltung mit dem Sicherheitspersonal einzurichten.</span><span class="sxs-lookup"><span data-stu-id="663cb-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="663cb-p104">Falls erforderlich, können Sie für jede Ortungsrichtlinie unterschiedliches Notrufpersonal konfigurieren. Auf diese Weise können Sie die Maßnahmen für unterschiedliche Unternehmensbereiche anpassen oder ein unterschiedliches Verhalten für Notrufe konfigurieren, die von innerhalb oder von außerhalb des Netzwerks erfolgen. Geben Sie die Mitarbeiter, die benachrichtigt werden sollen, mithilfe von Verteilergruppen an.</span><span class="sxs-lookup"><span data-stu-id="663cb-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

