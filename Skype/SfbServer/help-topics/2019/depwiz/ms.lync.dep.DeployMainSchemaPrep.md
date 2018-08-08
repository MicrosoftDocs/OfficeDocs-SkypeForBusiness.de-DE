---
title: Vorbereiten des Schemas
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Führen Sie zur Vorbereitung des Schemas für Active Directory Domain Services im Schema vorbereiten Schritt in der Skype für Business Server-Bereitstellungs-Assistenten auf. Klicken Sie auf Ausführen, um mit der Schemavorbereitung zu beginnen.
ms.openlocfilehash: 829c3062fcbfc1dab41e56de63e7a469f8e6e069
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "22138541"
---
# <a name="prepare-schema"></a><span data-ttu-id="f6547-104">Vorbereiten des Schemas</span><span class="sxs-lookup"><span data-stu-id="f6547-104">Prepare Schema</span></span>
 
<span data-ttu-id="f6547-105">Führen Sie zur Vorbereitung des Schemas für Active Directory Domain Services im Schema vorbereiten Schritt in der Skype für Business Server-Bereitstellungs-Assistenten auf.</span><span class="sxs-lookup"><span data-stu-id="f6547-105">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="f6547-106">Klicken Sie auf **Ausführen**, um mit der Schemavorbereitung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="f6547-106">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="f6547-107">Im Schritt „Schema vorbereiten“ werden die bereitgestellten Schemadefinitionsdateien im Verzeichnis „\Programme\Microsoft Lync Server 2013\Deployment\Setup“ des Systems gelesen, auf dem der Bereitstellungs-Assistent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f6547-107">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Microsoft Lync Server 2013\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="f6547-108">Diese Dateien stehen auch auf den Installationsmedien im Verzeichnis „\Support\Schema“ zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f6547-108">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="f6547-109">Der Schritt „Schema vorbereiten“ dient zum Erweitern des Schemas und zum Melden des Prozessstatus.</span><span class="sxs-lookup"><span data-stu-id="f6547-109">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="f6547-110">Ferner wird in diesem Schritt der Abschluss des Prozesses gemeldet.</span><span class="sxs-lookup"><span data-stu-id="f6547-110">It will also notify you when the process is complete.</span></span> <span data-ttu-id="f6547-111">Auf dem Zusammenfassungsbildschirm können Sie die Protokolle des Prozesses überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f6547-111">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="f6547-112">Vergewissern Sie sich mithilfe der Protokolle, dass die Vorbereitung erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="f6547-112">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f6547-113">Zum Erweitern des Schemas müssen Sie bei der Domäne als Mitglied der Gruppen „Schema-Admins“ und „Organisations-Admins“ angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="f6547-113">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="f6547-114">Zum Erweitern des Schemas Active Directory Domain Services zur Unterstützung von Skype für Business Server Server-Dienst und User-Objekte werden Klassen und Attribute hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f6547-114">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server server, service, and user objects.</span></span> <span data-ttu-id="f6547-115">Vor dem Erweitern des Schemas müssen Sie eine Systemstatussicherung des Domänencontrollers mit der Schemamasterrolle ausführen.</span><span class="sxs-lookup"><span data-stu-id="f6547-115">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="f6547-116">Das Erweitern des Schemas ist nicht umkehrbar.</span><span class="sxs-lookup"><span data-stu-id="f6547-116">Extending the schema is not reversible.</span></span> <span data-ttu-id="f6547-117">Versuchen Sie immer, die potenziellen Auswirkungen einer fehlerhaften Schemaerweiterung einzudämmen und sicherzustellen, dass die Erweiterung des Schemas erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="f6547-117">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="f6547-118">Dies ist besonders bei einem Ausfall der Kommunikation oder einem anderen Ausfall auf dem Server wichtig.</span><span class="sxs-lookup"><span data-stu-id="f6547-118">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="f6547-119">Sie sollten eine Sicherung der Schemamaster-Domänencontroller und eine vollständige Sicherung von Active Directory ausführen.</span><span class="sxs-lookup"><span data-stu-id="f6547-119">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="f6547-120">So führen Sie eine Sicherung der Schemamaster-Domänencontroller und eine vollständige Sicherung der Active Directory aus:</span><span class="sxs-lookup"><span data-stu-id="f6547-120">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="f6547-121">Trennen Sie den Domänencontroller mit der Schemamasterrolle vom Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="f6547-121">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="f6547-122">Führen Sie eine Systemstatussicherung des Domänencontrollers mit dem Schemamaster durch.</span><span class="sxs-lookup"><span data-stu-id="f6547-122">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="f6547-123">Erweitern Sie das Schema.</span><span class="sxs-lookup"><span data-stu-id="f6547-123">Extend the schema.</span></span>
    
4. <span data-ttu-id="f6547-124">Verbinden Sie den Domänencontroller nach erfolgreicher Schemaerweiterung wieder mit dem Netzwerk und stellen Sie sicher, dass die Replikation aktiv und betriebsbereit ist.</span><span class="sxs-lookup"><span data-stu-id="f6547-124">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="f6547-125">Wiederherstellen von in unwahrscheinlichen bei einem den Systemen Zustand des Domänencontrollers und Active Directory anhand der Systemstatus-Sicherung, die Sie zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="f6547-125">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f6547-126">Wenn Sie die Protokolldateien überprüfen, die durch die Skype für Business Server-Bereitstellungs-Assistenten erstellt werden müssen, finden Sie die Dateien auf dem Computer, auf dem Bereitstellungs-Assistenten ausgeführt wurde, im Verzeichnis Benutzer der Active Directory-Benutzer, die im Schritt ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="f6547-126">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="f6547-127">Angenommen, wenn der Benutzer als Domänenadministrator in der Domäne Contoso.net angemeldet, die Protokolldateien befinden sich im: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="f6547-127">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

