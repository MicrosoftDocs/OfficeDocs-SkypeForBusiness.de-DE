---
title: Verwalten von Exchange Unified Messaging und Voicemail gehostet
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Use PowerShell to manage Exchange Unified Messaging capabilities such as Auto Attendant and Subscriber Access and hosted voicemail in Skype for Business Online.
ms.openlocfilehash: 33fe3c7a3c19916a8a70008f467035c832e5ecb3
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a><span data-ttu-id="6975d-103">Verwalten von Exchange Unified Messaging und Voicemail gehostet</span><span class="sxs-lookup"><span data-stu-id="6975d-103">Manage Exchange Unified Messaging and hosted voicemail</span></span>

<span data-ttu-id="6975d-104">Sie können Exchange Unified Messaging und gehostete Voicemails in Skype for Business Online mit einer Reihe von Cmdlets verwalten.</span><span class="sxs-lookup"><span data-stu-id="6975d-104">You can manage Exchange Unified Messaging and hosted voicemail in Skype for Business Online by using a set of cmdlets.</span></span>
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a><span data-ttu-id="6975d-105">Verwalten von Exchange Unified Messaging und gehosteten Voicemails</span><span class="sxs-lookup"><span data-stu-id="6975d-105">Manage Exchange unified messaging and hosted voice mail</span></span>

<span data-ttu-id="6975d-106">Die folgenden Cmdlets können zum Verwalten von Exchange Unified Messaging (UM) und Richtlinien für gehostete Voicemails verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="6975d-106">The following cmdlets can be used to manage Exchange Unified Messaging (UM) and hosted voicemail policies:</span></span>
  
|<span data-ttu-id="6975d-107">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="6975d-107">**Cmdlet**</span></span>|<span data-ttu-id="6975d-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="6975d-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="6975d-109">Get-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="6975d-109">Get-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [<span data-ttu-id="6975d-110">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="6975d-110">New-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[<span data-ttu-id="6975d-111">Remove-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="6975d-111">Remove-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[<span data-ttu-id="6975d-112">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="6975d-112">Set-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |<span data-ttu-id="6975d-113">Erstellt und verwaltet Kontaktobjekte, die für die automatische Telefonzentrale und für Abonnentenzugriffsdienste verwendet werden, wenn Exchange UM als gehosteter Dienst bereitgestellt ist.</span><span class="sxs-lookup"><span data-stu-id="6975d-113">Creates and manages contact objects used for Auto Attendant and Subscriber Access services, when Exchange UM is a hosted service.</span></span>  <br/><br/> <span data-ttu-id="6975d-p101">Skype for Business Online stellt gemeinsam mit Exchange UM verschiedene Funktionen im Zusammenhang mit VoIP bereit, darunter automatische Telefonzentrale und Abonnentenzugriff. Mit der automatischen Telefonzentrale können Anrufe automatisch angenommen und an die richtige Person weitergeleitet werden. Über den Abonnentenzugriff können Benutzer eine Verbindung mit Exchange UM herstellen und E-Mails, Sprachnachrichten, Kontakte und Kalenderinformationen abrufen.</span><span class="sxs-lookup"><span data-stu-id="6975d-p101">Skype for Business Online works with Exchange UM to provide several voice-related capabilities, including Auto Attendant and Subscriber Access. Auto Attendant provides a way for calls to automatically be answered and routed to the correct person. Subscriber Access enables users to connect to Exchange UM and retrieve email, voice messages, contacts, and calendar information.  </span></span><br/><br/> <span data-ttu-id="6975d-p102">Wenn Exchange UM als gehosteter Dienst bereitgestellt ist, müssen Kontaktobjekte, die für die automatische Telefonzentrale und für Abonnentenzugriffsdienste verwendet werden, mit Microsoft PowerShell erstellt werden. Diese Objekte werden mit den **CsExUmContact** -Cmdlets erstellt und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="6975d-p102">When Exchange UM is provided as a hosted service, contact objects used for the Auto Attendant and Subscriber Access services must be created by using Microsoft PowerShell. These objects are created and managed by using the **CsExUmContact** cmdlets. </span></span><br/> |
|[<span data-ttu-id="6975d-119">Get-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="6975d-119">Get-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[<span data-ttu-id="6975d-120">GRANT-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="6975d-120">Grant-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |<span data-ttu-id="6975d-p103">Verwaltet in der Organisation verwendete Richtlinien für gehostete Voicemails. Richtlinien für gehostete Voicemails legen fest, wie nicht angenommene Anrufe an den Exchange UM-Dienst weitergeleitet werden. Diese Richtlinien wirken sich nur auf Benutzer aus, die für gehostete Voicemails in Exchange UM aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="6975d-p103">Manages hosted voicemail policies used in the organization. Hosted voicemail policies specify how unanswered calls are routed to the Exchange UM service. These policies affect only users who have been enabled for Exchange UM hosted voicemail.</span></span>  <br/><br/> <span data-ttu-id="6975d-124">Um zu überprüfen, ob ein Benutzer für gehostete Voicemails aktiviert ist, führen Sie an der PowerShell-Eingabeaufforderung etwa den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="6975d-124">To verify whether a user is enabled for hosted voicemail, run a command similar to the following from the PowerShell prompt.</span></span>  <br/> <span data-ttu-id="6975d-125">"Get-CsOnlineUser-Identity"kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="6975d-125">\`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"</span></span> | <span data-ttu-id="6975d-126">Select-Object HostedVoiceMail'</span><span class="sxs-lookup"><span data-stu-id="6975d-126">Select-Object HostedVoiceMail\`</span></span>|
   

## <a name="related-topics"></a><span data-ttu-id="6975d-127">See Also</span><span class="sxs-lookup"><span data-stu-id="6975d-127">Related topics</span></span>
[<span data-ttu-id="6975d-128">Einrichten des Computers für Skype für das Business online Management mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6975d-128">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 