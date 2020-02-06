---
title: Bewährte Methoden für Ihre Kerninfrastruktur in Skype for Business Server
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
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Sie haben wahrscheinlich bereits Schritte unternommen, um Fehlertoleranz in Ihrem System zu entwerfen, und Verfahren wie das Sicherstellen von Hardwareredundanz, Schutzmaßnahmen gegen Stromausfälle, Routineinstallation von Sicherheitsupdates und Antivirenmaßnahmen sowie Monitoring Server-Aktivitäten verwendet. Diese Vorgehensweisen sind nicht nur für Ihre Skype for Business Server-Infrastruktur, sondern auch für Ihr gesamtes Netzwerk vorteilhaft. Wenn Sie diese Methoden nicht implementiert haben, empfiehlt es sich, dies vor der Bereitstellung von Skype for Business Server zu tun.
ms.openlocfilehash: 62200fc1ac45e1d647761af24d176a00d18693e4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815683"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a><span data-ttu-id="a7df4-105">Bewährte Methoden für Ihre Kerninfrastruktur in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a7df4-105">Best practices for your core infrastructure in Skype for Business Server</span></span>
 
<span data-ttu-id="a7df4-106">Sie haben wahrscheinlich bereits Schritte unternommen, um Fehlertoleranz in Ihrem System zu entwerfen, und Verfahren wie das Sicherstellen von Hardwareredundanz, Schutzmaßnahmen gegen Stromausfälle, Routineinstallation von Sicherheitsupdates und Antivirenmaßnahmen sowie Monitoring Server-Aktivitäten verwendet.</span><span class="sxs-lookup"><span data-stu-id="a7df4-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="a7df4-107">Diese Vorgehensweisen sind nicht nur für Ihre Skype for Business Server-Infrastruktur, sondern auch für Ihr gesamtes Netzwerk vorteilhaft.</span><span class="sxs-lookup"><span data-stu-id="a7df4-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="a7df4-108">Wenn Sie diese Methoden nicht implementiert haben, empfiehlt es sich, dies vor der Bereitstellung von Skype for Business Server zu tun.</span><span class="sxs-lookup"><span data-stu-id="a7df4-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="a7df4-109">Gehen Sie wie folgt vor, um die Server in Ihrer Skype for Business Server-Bereitstellung vor versehentlichen oder zielgerichteten Verletzungen zu schützen, die zu Ausfallzeiten führen können:</span><span class="sxs-lookup"><span data-stu-id="a7df4-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="a7df4-110">Halten Sie Ihre Server mit Sicherheitsupdates auf dem neuesten Stand.</span><span class="sxs-lookup"><span data-stu-id="a7df4-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="a7df4-111">Mit einem Abonnement für den Microsoft Security Notification Service können Sie sicherstellen, dass Sie bei Veröffentlichungen von Sicherheitsbulletins für alle Microsoft-Produkte sofort benachrichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="a7df4-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="a7df4-112">Wenn Sie sich anmelden möchten, wechseln Sie zur [Website Microsoft Technical Security Notifications](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span><span class="sxs-lookup"><span data-stu-id="a7df4-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="a7df4-113">Achten Sie darauf, dass Zugriffsrechte ordnungsgemäß eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="a7df4-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="a7df4-p104">Stellen Sie Ihre Server in einer physischen Umgebung auf, die einen nicht autorisierten Zugriff verhindert. Stellen Sie sicher, dass angemessene Antivirensoftware auf allen Servern installiert ist. Halten Sie die Software mit den neuesten Virussignaturdateien auf dem neuesten Stand. Verwenden Sie die Funktion für automatische Updates Ihrer Antivirenanwendung, um die Virussignaturen aktuell zu halten.</span><span class="sxs-lookup"><span data-stu-id="a7df4-p104">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="a7df4-118">Wir empfehlen, dass Sie die Windows Server-Betriebssystemdienste deaktivieren, die auf den Computern, auf denen Sie Skype for Business Server installieren, nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a7df4-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="a7df4-119">Verschlüsseln Sie Betriebssysteme und Festplattenlaufwerke, auf denen Daten gespeichert sind, mit einem Verschlüsselungssystem für das gesamte Volume, es sei denn, Sie können eine beständige und vollständige Kontrolle der Server, vollkommene physische Isolation und das ordnungsgemäße und sichere Außerbetriebsetzen von ausgetauschten oder ausgefallenen Festplattenlaufwerken sicherstellen.</span><span class="sxs-lookup"><span data-stu-id="a7df4-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="a7df4-120">Deaktivieren Sie alle externen Ports für den direkten Speicherzugriff des Servers, es sei denn, Sie können eine sehr enge Kontrolle des physischen Zugriffs auf die Server sicherstellen.</span><span class="sxs-lookup"><span data-stu-id="a7df4-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="a7df4-121">Angriffe auf der Basis von direktem Speicher, die realtiv einfach initiiert werden können, könnten sehr vertrauliche Informationen wie private Verschlüsselungsschlüssel offenlegen.</span><span class="sxs-lookup"><span data-stu-id="a7df4-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

