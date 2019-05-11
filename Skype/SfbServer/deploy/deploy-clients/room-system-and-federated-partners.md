---
title: Skype Room System- und Skype for Business-Verbundpartner
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Lesen Sie dieses Thema, um zu erfahren, wie Sie Skype Room System für Skype for Business-Verbundpartner einrichten.
ms.openlocfilehash: 30668641f2c43981485531722861647fdeffc710
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895019"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="bd3a8-103">Skype Room System- und Skype for Business-Verbundpartner</span><span class="sxs-lookup"><span data-stu-id="bd3a8-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="bd3a8-104">Lesen Sie dieses Thema, um zu erfahren, wie Sie Skype Room System für Skype for Business-Verbundpartner einrichten.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="bd3a8-105">Skype Room System- und Skype for Business-Verbundpartner</span><span class="sxs-lookup"><span data-stu-id="bd3a8-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="bd3a8-106">Skype Raum System nutzt die Teilnahme Skype für Business besprechungslink in der Besprechungsanfrage Kalender.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="bd3a8-107">Der Link für die Teilnahme ist normalerweise im Textkörper der Besprechungsanfrage zu finden.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="bd3a8-108">Skype Raum System hängt jedoch diesen Link, um in die MAPI-Eigenschaften der Nachricht vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="bd3a8-109">Wenn diese Besprechungsanfrage werden an remote Organisationen (Skype für Geschäftspartner federated), standardmäßig gesendet die Remoteorganisation Skype Raum System wird nicht angezeigt, die die Teilnahme an einer Besprechung im Kalender zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="bd3a8-110">Tatsächlich Outlook-Benutzer, die in der Remoteorganisation nicht an die Skype für Business-Besprechung mit einem Klick rechts des Kalenders item oder aus teilnehmen können innerhalb einer besprechungserinnerung.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="bd3a8-111">Sie öffnen Besprechung einladen, und klicken Sie auf teilnehmen Skype für Business Besprechung im Textkörper der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="bd3a8-112">Der Grund für dieses Einschränkung ist, dass Outlook und Microsoft Exchange keine spezielle Methode dafür kennen, Informationen für den Versand von Nachrichten über das Internet mit einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="bd3a8-113">Diese Methode, die als „Transport Neutral Encapsulation Format“ (TNEF) bezeichnet wird, ist für Nachrichten, die aus einem Exchange-Unternehmen extern versendet werden, standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="bd3a8-114">Für eine Besprechung teilnehmen Hyperlink einfügen auf einem Skype Raum Remotesystem, muss die sendende Organisation TNEF mithilfe des folgenden Befehls aktivieren:</span><span class="sxs-lookup"><span data-stu-id="bd3a8-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="bd3a8-115">Nachdem TNEF für das Remote-Unternehmen aktiviert worden ist, wird jede über das Internet an das Unternehmen gesendete Nachricht als Anlage im TNEF-Format geschickt.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="bd3a8-116">Mit TNEF aktiviert Wenn eine Skype für wird Business Besprechungsanfrage gesendet, der Skype für Verbundpartner Business, Skype Raum System sind in der Lage, die Verknüpfung Skype für Business Besprechung Rendern und Remotebenutzer können Skype für Business-Besprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 
