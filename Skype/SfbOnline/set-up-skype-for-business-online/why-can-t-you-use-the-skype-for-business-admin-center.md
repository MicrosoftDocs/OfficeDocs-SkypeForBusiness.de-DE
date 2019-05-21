---
title: Warum kann ich das Skype for Business Online Admin Center gerade nicht verwenden?
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.lync.lac.TenantInMigration
ms.custom:
- Setup
description: 'Erfahren Sie, was Sie in Skype for Business Admin Center und anderen Features nutzen können, wenn Ihr Dienst zu einem anderen Microsoft-Rechenzentrum migriert wird. '
ms.openlocfilehash: 006caf6542abfeeb38e9563b6866fb119c47b88f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284877"
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="7e2d5-103">Warum kann ich das Skype for Business Online Admin Center gerade nicht verwenden?</span><span class="sxs-lookup"><span data-stu-id="7e2d5-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="7e2d5-104">Wir wissen, dass es frustrierend ist, wenn Sie Ihre Arbeit nicht erledigen können, und deshalb werden wir Ihnen erläutern, was hier passiert und warum es das warten Wert ist.</span><span class="sxs-lookup"><span data-stu-id="7e2d5-104">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="7e2d5-105">Zunächst folgt die technische Erläuterung:</span><span class="sxs-lookup"><span data-stu-id="7e2d5-105">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="7e2d5-106">Wir migrieren Ihren Skype for Business Online-Dienst (also Ihre Benutzer und organisatorischen Einstellungen) zu einem anderen Microsoft-Rechenzentrum, das Ihnen näher steht.</span><span class="sxs-lookup"><span data-stu-id="7e2d5-106">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="7e2d5-107">Dadurch wird der Service verbessert und die Latenz verkürzt.</span><span class="sxs-lookup"><span data-stu-id="7e2d5-107">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="7e2d5-108">Weitere technische Details finden Sie unter [während und nach dem Verschieben von Daten]( https://go.microsoft.com/fwlink/?LinkId=526418).</span><span class="sxs-lookup"><span data-stu-id="7e2d5-108">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="7e2d5-109">OK, was bedeutet das?</span><span class="sxs-lookup"><span data-stu-id="7e2d5-109">OK, so what does that mean?</span></span>

<span data-ttu-id="7e2d5-110">Als erstes brechen wir einige Begriffe auf.</span><span class="sxs-lookup"><span data-stu-id="7e2d5-110">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="7e2d5-111">**Rechenzentrum** Dies ist der physikalische Standort, an dem die Informationen aus Ihrer Office 365-Organisation gespeichert werden, beispielsweise Ihre Dateien und e-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="7e2d5-111">**Data center** This is the physical location where the information from your Office 365 organization is stored, such as your files and email messages.</span></span> <span data-ttu-id="7e2d5-112">Wenn Sie sich wirklich mit den Office 365-Rechenzentren ausgraben möchten, lesen Sie[diesen Artikel](https://www.microsoft.com/online/legal/v2/?docid=25).</span><span class="sxs-lookup"><span data-stu-id="7e2d5-112">If you really want to dig in to what Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="7e2d5-113">**Migrieren** von Das ist ziemlich ähnlich wie "verschieben".</span><span class="sxs-lookup"><span data-stu-id="7e2d5-113">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="7e2d5-114">In diesem Fall bedeutet dies, dass wir Ihre Skype for Business Online-Benutzer und-Einstellungen von einem Rechenzentrum in ein anderes verschieben, das Ihnen näher steht, um Ihren Service zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="7e2d5-114">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="7e2d5-115">**Latenz** Dies ist die Zeitdauer, die Sie für den Zugriff auf das Office 365 Admin Center benötigt, um die Einstellungen zu ändern und diese Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7e2d5-115">**Latency** This is amount of time it takes you to access the Office 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="7e2d5-116">**Korrelations-ID** Möglicherweise haben Sie dies in der Nachricht angezeigt, von der Sie gerade gekommen sind.</span><span class="sxs-lookup"><span data-stu-id="7e2d5-116">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="7e2d5-117">Diese Informationen werden von Microsoft-Supportmitarbeitern verwendet, um Ihnen bei der Behebung eines Fehlers zu helfen.</span><span class="sxs-lookup"><span data-stu-id="7e2d5-117">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="7e2d5-118">Wenn Sie sich an den Microsoft-Support wenden, werden Sie möglicherweise nach der Korrelations-ID gefragt.</span><span class="sxs-lookup"><span data-stu-id="7e2d5-118">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="7e2d5-119">Das bedeutet also, dass wir gerade dabei sind, alle Ihre Skype for Business Online-Benutzer und-Diensteinstellungen an einen anderen Ort zu verschieben, der Ihnen näher steht.</span><span class="sxs-lookup"><span data-stu-id="7e2d5-119">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="7e2d5-120">Je näher, desto besser.</span><span class="sxs-lookup"><span data-stu-id="7e2d5-120">The closer the better.</span></span> <span data-ttu-id="7e2d5-121">Die gute Nachricht ist, dass Ihr Skype for Business Online-Service nach dieser kurzen Zeitspanne verbessert wird.</span><span class="sxs-lookup"><span data-stu-id="7e2d5-121">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![Dienst Migration in Office 365](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="7e2d5-123">Welche Funktionen von Skype for Business Online funktionieren weiterhin?</span><span class="sxs-lookup"><span data-stu-id="7e2d5-123">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="7e2d5-124">Auch wenn Sie nicht in der Lage sind, auf das Skype for Business Online Admin Center zuzugreifen, funktionieren die folgenden Skype for Business Online-Features während der Migration weiterhin:</span><span class="sxs-lookup"><span data-stu-id="7e2d5-124">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="7e2d5-125">Online Besprechungen</span><span class="sxs-lookup"><span data-stu-id="7e2d5-125">Online meetings</span></span>
    
- <span data-ttu-id="7e2d5-126">Anwesenheitsinformationen</span><span class="sxs-lookup"><span data-stu-id="7e2d5-126">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="7e2d5-127">Kann ich andere Aufgaben erledigen?</span><span class="sxs-lookup"><span data-stu-id="7e2d5-127">Can I get other work done?</span></span>

<span data-ttu-id="7e2d5-128">Sicher.</span><span class="sxs-lookup"><span data-stu-id="7e2d5-128">Sure.</span></span> <span data-ttu-id="7e2d5-129">Während der Migration Ihres Skype for Business Online-Diensts können Sie weiterhin die anderen Admin Center in Office 365 verwenden (beispielsweise die Office 365-und Exchange Admin Center).</span><span class="sxs-lookup"><span data-stu-id="7e2d5-129">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Office 365 (for example, the Office 365 and Exchange admin centers).</span></span> <span data-ttu-id="7e2d5-130">Zusammen mit dem Skype for Business Online Admin Center können Sie die Skype for Business Online-Remote-PowerShell-Cmdlets während der Migration nicht mehr verwenden.</span><span class="sxs-lookup"><span data-stu-id="7e2d5-130">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="7e2d5-131">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7e2d5-131">Related topics</span></span>
[<span data-ttu-id="7e2d5-132">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7e2d5-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="7e2d5-133">Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen</span><span class="sxs-lookup"><span data-stu-id="7e2d5-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
