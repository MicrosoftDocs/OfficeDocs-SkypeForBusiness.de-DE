---
title: Einbeziehen des Security Desks in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Planen Sie, wie Sie den Security Desk Ihrer Organisation in eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP einbeziehen möchten.
ms.openlocfilehash: 19fc8a01fcb51be3ce36435a5a657c3253716b2c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802455"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a><span data-ttu-id="42850-103">Einbeziehen des Security Desks in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="42850-103">Include the security desk in Skype for Business Server</span></span>
 
<span data-ttu-id="42850-104">Planen Sie, wie Sie den Security Desk Ihrer Organisation in eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP einbeziehen möchten.</span><span class="sxs-lookup"><span data-stu-id="42850-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="42850-p101">In Ihrem Unternehmen soll möglicherweise das Sicherheitsdesk in die Konfiguration für Notrufe eingebunden werden. Um entscheiden zu können, wie das Sicherheitsdesk in Ihre E9-1-1-Bereitstellung integriert werden kann, müssen Sie die folgenden Fragen beantworten.</span><span class="sxs-lookup"><span data-stu-id="42850-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="42850-107">**Soll das Sicherheitsdesk benachrichtigt werden, wenn ein Notruf abgesetzt wird?**</span><span class="sxs-lookup"><span data-stu-id="42850-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="42850-108">Sie können die ortungsrichtlinie so konfigurieren, dass Skype for Business Server Sofortnachrichten (im) an die Skype for Business-SIP-Adressen von einem oder mehreren Sicherheitspersonal sendet.</span><span class="sxs-lookup"><span data-stu-id="42850-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="42850-109">Diese Benachrichtigungen enthalten den Namen, die Nummer und den Standort der Person, die den Notruf durchführt, und erleichtert das Sicherheitspersonal bei der Unterstützung der Notfallsituation.</span><span class="sxs-lookup"><span data-stu-id="42850-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="42850-110">**Möchten Sie für Notrufe eine Konferenzschaltung mit dem Sicherheitsdesk einrichten?**</span><span class="sxs-lookup"><span data-stu-id="42850-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="42850-p103">Sofern dies vom Anbieter für die Notrufunterstützung unterstützt wird, können Sie in der Ortungsrichtlinie eine Rückrufnummer für Notrufe einschließen. Diese Nummer wird vom Anbieter verwendet, um für Notrufe eine Konferenzschaltung mit dem Sicherheitspersonal einzurichten.</span><span class="sxs-lookup"><span data-stu-id="42850-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="42850-p104">Falls erforderlich, können Sie für jede Ortungsrichtlinie unterschiedliches Notrufpersonal konfigurieren. Auf diese Weise können Sie die Maßnahmen für unterschiedliche Unternehmensbereiche anpassen oder ein unterschiedliches Verhalten für Notrufe konfigurieren, die von innerhalb oder von außerhalb des Netzwerks erfolgen. Geben Sie die Mitarbeiter, die benachrichtigt werden sollen, mithilfe von Verteilergruppen an.</span><span class="sxs-lookup"><span data-stu-id="42850-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

