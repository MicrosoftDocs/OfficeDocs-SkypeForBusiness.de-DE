---
title: Skype Room System- und Skype for Business-Verbundpartner
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Lesen Sie dieses Thema, um zu erfahren, wie Sie Skype Room System für Skype for Business-Verbundpartner einrichten.
ms.openlocfilehash: 7bf67a910b2c0d73cf3e068e9524500804ca87f4
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775274"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="ba86f-103">Skype Room System- und Skype for Business-Verbundpartner</span><span class="sxs-lookup"><span data-stu-id="ba86f-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="ba86f-104">Lesen Sie dieses Thema, um zu erfahren, wie Sie Skype Room System für Skype for Business-Verbundpartner einrichten.</span><span class="sxs-lookup"><span data-stu-id="ba86f-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="ba86f-105">Skype Room System- und Skype for Business-Verbundpartner</span><span class="sxs-lookup"><span data-stu-id="ba86f-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="ba86f-106">Das Skype Room-System basiert auf dem Link "an Skype for Business-Besprechung teilnehmen" in der Besprechungsanfrage des Kalenders.</span><span class="sxs-lookup"><span data-stu-id="ba86f-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="ba86f-107">Der Link für die Teilnahme ist normalerweise im Textkörper der Besprechungsanfrage zu finden.</span><span class="sxs-lookup"><span data-stu-id="ba86f-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="ba86f-108">Das Skype Room-System hängt jedoch davon ab, dass dieser Link in den MAPI-Eigenschaften der Nachricht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ba86f-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="ba86f-109">Wenn diese Besprechungsanfrage an Remote Organisationen (Skype for Business-Verbundpartner) gesendet wird, wird standardmäßig im Skype Room-System der Remoteorganisation der Link "Besprechungsteilnahme" im Kalender nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba86f-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="ba86f-110">In der Tat können Outlook-Benutzer in der Remoteorganisation mit einem Rechtsklick auf das Kalenderelement oder innerhalb der Besprechungserinnerung nicht an der Skype for Business-Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="ba86f-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="ba86f-111">Sie müssen die Besprechungseinladung öffnen und im Textkörper der Nachricht auf an Skype for Business-Besprechung teilnehmen klicken.</span><span class="sxs-lookup"><span data-stu-id="ba86f-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="ba86f-112">Der Grund für dieses Einschränkung ist, dass Outlook und Microsoft Exchange keine spezielle Methode dafür kennen, Informationen für den Versand von Nachrichten über das Internet mit einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="ba86f-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="ba86f-113">Diese Methode, die als „Transport Neutral Encapsulation Format“ (TNEF) bezeichnet wird, ist für Nachrichten, die aus einem Exchange-Unternehmen extern versendet werden, standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ba86f-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="ba86f-114">Damit ein Link zur Besprechungsteilnahme in einem Remote-Skype-Raum System angezeigt wird, muss die sendende Organisation TNEF mithilfe des folgenden Befehls aktivieren:</span><span class="sxs-lookup"><span data-stu-id="ba86f-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="ba86f-115">Nachdem TNEF für das Remote-Unternehmen aktiviert worden ist, wird jede über das Internet an das Unternehmen gesendete Nachricht als Anlage im TNEF-Format geschickt.</span><span class="sxs-lookup"><span data-stu-id="ba86f-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="ba86f-116">Wenn die TNEF-Funktion aktiviert ist und eine Skype for Business-Besprechungsanfrage an den Skype for Business-Verbundpartner gesendet wird, kann Skype Room System die Teilnahme an Skype for Business-Besprechungen wiedergeben, und Remotebenutzer können an Skype for Business-Besprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="ba86f-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 
