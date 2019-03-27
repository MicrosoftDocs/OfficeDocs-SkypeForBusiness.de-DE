---
title: Warum verwenden kann nicht ich die Skype für Business Online Administrationscenter sofort?
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c182d564-1674-4491-b1d9-3e0cb657d4cc
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.lync.lac.TenantInMigration
ms.custom:
- Setup
description: 'Hier erfahren Sie, was Sie können und nicht in Skype für Business-Verwaltungskonsole und andere Features verwenden, wenn Ihren Dienst auf einem anderen Microsoft-Rechenzentrum migriert wird. '
ms.openlocfilehash: 57ffa6e37c18de8e87e5af00750eef276649f4f5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885639"
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="e12b5-103">Warum verwenden kann nicht ich die Skype für Business Online Administrationscenter sofort?</span><span class="sxs-lookup"><span data-stu-id="e12b5-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="e12b5-104">Wir wissen, dass es frustrierend ist, wenn Sie, Ihre Arbeit vermitteln ist nicht möglich, also wir wird erläutert, was geschieht hier wird und warum sich warten werden.</span><span class="sxs-lookup"><span data-stu-id="e12b5-104">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="e12b5-105">Zunächst wird die Erklärung hier:</span><span class="sxs-lookup"><span data-stu-id="e12b5-105">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="e12b5-106">Wir sind Ihre Skype für Business Online-Dienst (d. h., Ihren Benutzern und organisatorische Settings) in einer anderen Microsoft-Rechenzentrum migrieren, die Sie näher ist.</span><span class="sxs-lookup"><span data-stu-id="e12b5-106">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="e12b5-107">Verbessern des Diensts dadurch und Wartezeit reduzieren.</span><span class="sxs-lookup"><span data-stu-id="e12b5-107">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="e12b5-108">Weitere technische Details finden Sie unter [während und nach der Daten verschoben]( https://go.microsoft.com/fwlink/?LinkId=526418).</span><span class="sxs-lookup"><span data-stu-id="e12b5-108">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="e12b5-109">OK, also was bedeutet das?</span><span class="sxs-lookup"><span data-stu-id="e12b5-109">OK, so what does that mean?</span></span>

<span data-ttu-id="e12b5-110">Zunächst ein paar Begriffe aufgegliedert.</span><span class="sxs-lookup"><span data-stu-id="e12b5-110">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="e12b5-111">**Rechenzentrum** Dies ist die physischen Standort, auf dem die Informationen aus der Office 365-Organisation, wie Ihre Dateien und e-Mail-Nachrichten gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="e12b5-111">**Data center** This is the physical location where the information from your Office 365 organization is stored, such as your files and email messages.</span></span> <span data-ttu-id="e12b5-112">Wenn Sie befasst was Office 365 Rechenzentren werden möchten, sehen Sie sich[in diesem Artikel](https://www.microsoft.com/online/legal/v2/?docid=25).</span><span class="sxs-lookup"><span data-stu-id="e12b5-112">If you really want to dig in to what Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="e12b5-113">**Migrieren** Dies ist ziemlich identisch mit dem "verschieben".</span><span class="sxs-lookup"><span data-stu-id="e12b5-113">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="e12b5-114">In diesem Fall bedeutet dies, dass wir Ihre Skype Business Online-Benutzern und Einstellungen für von einem Datencenter an eine andere verschoben wird, die Sie zur Verbesserung des Diensts näher ist.</span><span class="sxs-lookup"><span data-stu-id="e12b5-114">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="e12b5-115">**Wartezeit** Dies ist die Menge der Zeit, die Sie für den Zugriff auf das Office 365 Administrationscenter stellen eine Einstellungen ändern, und speichern Sie diese Änderungen.</span><span class="sxs-lookup"><span data-stu-id="e12b5-115">**Latency** This is amount of time it takes you to access the Office 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="e12b5-116">**Korrelations-ID** Möglicherweise haben Sie gesehen, dass dies in der Nachricht aufgeführt, die Sie soeben stammt.</span><span class="sxs-lookup"><span data-stu-id="e12b5-116">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="e12b5-117">Diese Informationen werden von Microsoft-Supporttechniker verwendet, können Sie einen Fehler beheben.</span><span class="sxs-lookup"><span data-stu-id="e12b5-117">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="e12b5-118">Wenn Sie Microsoft-Supportmitarbeiter kontaktieren, können Sie nach der Korrelations-ID. gefragt werden</span><span class="sxs-lookup"><span data-stu-id="e12b5-118">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="e12b5-119">Damit Was ist in allen bedeutet, dass wir gerade alle Ihre Skype für Business Online-Benutzer verschieben und webdiensteinstellungen an einen anderen Speicherort, der Ihnen näher ist.</span><span class="sxs-lookup"><span data-stu-id="e12b5-119">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="e12b5-120">Je näher der besser.</span><span class="sxs-lookup"><span data-stu-id="e12b5-120">The closer the better.</span></span> <span data-ttu-id="e12b5-121">Die gute Nachricht ist, dass nach kurzer Zeit Ihrer Skype für Business Onlinedienst verbessert wird.</span><span class="sxs-lookup"><span data-stu-id="e12b5-121">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![Service-Migration in Office 365](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="e12b5-123">Was Skype für Business Online-Funktionen weiterhin funktionsfähig sind?</span><span class="sxs-lookup"><span data-stu-id="e12b5-123">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="e12b5-124">Obwohl Sie die Skype für Business Online Administrationscenter zugreifen können, werden nicht, wird während der Migration die folgenden Skype für Business Online-Features funktionieren:</span><span class="sxs-lookup"><span data-stu-id="e12b5-124">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="e12b5-125">Onlinebesprechungen</span><span class="sxs-lookup"><span data-stu-id="e12b5-125">Online meetings</span></span>
    
- <span data-ttu-id="e12b5-126">Anwesenheitsinformationen</span><span class="sxs-lookup"><span data-stu-id="e12b5-126">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="e12b5-127">Erhalte ich andere Arbeit?</span><span class="sxs-lookup"><span data-stu-id="e12b5-127">Can I get other work done?</span></span>

<span data-ttu-id="e12b5-128">Sicher.</span><span class="sxs-lookup"><span data-stu-id="e12b5-128">Sure.</span></span> <span data-ttu-id="e12b5-129">Während wir Ihre Skype für Business Onlinedienst migrieren, können Sie weiterhin die anderen Admin Center in Office 365 (beispielsweise die Office 365 und Exchange Admin Center).</span><span class="sxs-lookup"><span data-stu-id="e12b5-129">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Office 365 (for example, the Office 365 and Exchange admin centers).</span></span> <span data-ttu-id="e12b5-130">Jedoch wird nicht zusammen mit der Skype für Business Online Administrationscenter, Sie während der Migration der Skype für Business Online Remote-PowerShell-Cmdlets verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e12b5-130">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="e12b5-131">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e12b5-131">Related topics</span></span>
[<span data-ttu-id="e12b5-132">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e12b5-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="e12b5-133">Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen</span><span class="sxs-lookup"><span data-stu-id="e12b5-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
