---
title: Einrichten oder Entfernen von Komponenten von Skype for Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainBootstrap
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
description: 'Zum Installieren und aktivieren oder deaktivieren oder deinstallieren Skype für Business Server 2015 Komponenten, verwenden Sie Schritt2: Einrichten oder Entfernen von Skype-Serverkomponenten. Sie müssen angemeldet sein in als lokaler Administrator auf dem Computer sind installieren oder ändern und muss in der Lage, Active Directory-Domänendienste-Benutzer und Gruppen in der aktuellen Domäne zu lesen. Klicken Sie auf Ausführen, um zu beginnen. Beim Ausführen dieses Schritts wird die auf dem zentralen Verwaltungsspeicher basierende Topologiedefinition gelesen. Die erforderlichen Softwarekomponenten werden gemäß der im zentralen Verwaltungsspeicher definierten Rolle installiert und konfiguriert. Zeigen Sie nach Abschluss der Installation die Zusammenfassung an und klicken Sie auf Fertig stellen.'
ms.openlocfilehash: c8845f34b09513c47b3332a751ae17e93cc655ee
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201209"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a><span data-ttu-id="e363f-108">Einrichten oder Entfernen von Komponenten von Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e363f-108">Setup or Remove Skype for Business Server Components</span></span>
 
<span data-ttu-id="e363f-109">Verwenden Sie zum Installieren und aktivieren oder deaktivieren oder deinstallieren Skype für Business Server 2015 Komponenten, **Schritt2: Einrichten oder Entfernen von Skype-Serverkomponenten**.</span><span class="sxs-lookup"><span data-stu-id="e363f-109">To install and activate, or deactivate or uninstall Skype for Business Server 2015 components, you use **Step 2: Setup or Remove Skype Server Components**.</span></span> <span data-ttu-id="e363f-110">Sie müssen angemeldet sein in als lokaler Administrator auf dem Computer sind installieren oder ändern und muss in der Lage, Active Directory-Domänendienste-Benutzer und Gruppen in der aktuellen Domäne zu lesen.</span><span class="sxs-lookup"><span data-stu-id="e363f-110">You must be logged in as a local administrator on the computer that you are installing or modifying and must be able to read Active Directory Domain Services users and groups in the current domain.</span></span> <span data-ttu-id="e363f-111">Klicken Sie auf **Ausführen**, um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="e363f-111">To begin, click **Run**.</span></span> <span data-ttu-id="e363f-112">Beim Ausführen dieses Schritts wird die auf dem zentralen Verwaltungsspeicher basierende Topologiedefinition gelesen.</span><span class="sxs-lookup"><span data-stu-id="e363f-112">When you do this, the Central Management store-based topology definition is read.</span></span> <span data-ttu-id="e363f-113">Die erforderlichen Softwarekomponenten werden gemäß der im zentralen Verwaltungsspeicher definierten Rolle installiert und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e363f-113">Necessary software components are installed and configured, according to the role as defined in the Central Management store.</span></span> <span data-ttu-id="e363f-114">Zeigen Sie nach Abschluss der Installation die Zusammenfassung an und klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="e363f-114">When the installation is complete, review the Summary, and click **Finish**.</span></span>
  
> [!TIP]
> <span data-ttu-id="e363f-115">Wenn Sie die Protokolldateien überprüfen, die durch den Bereitstellungs-Assistenten erstellt werden müssen, können sie auf dem Computer finden Sie dem Bereitstellungs-Assistenten ausgeführt wurde, im Verzeichnis Benutzer der Active Directory-Benutzer, die im Schritt ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="e363f-115">If you need to review the log files that are created by the Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="e363f-116">Angenommen, wenn der Benutzer als Domänenadministrator in der Domäne Contoso.net angemeldet, die Protokolldateien befinden sich im: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="e363f-116">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e363f-117">Wenn Sie zuvor Skype für Business Server 2015 Komponenten auf dem Computer installiert haben, im Bereitstellungs-Assistenten wird dies erkannt, und die Schaltfläche in Schritt 2 angezeigt wird, **Erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e363f-117">If you have previously installed Skype for Business Server 2015 components on this computer, the Deployment Wizard will recognize this, and the button in step 2 will be displayed as **Run Again**.</span></span> <span data-ttu-id="e363f-118">So können Sie den Schritt bei Bedarf mehrfach ausführen, um den Server ordnungsgemäß zu konfigurieren oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e363f-118">This enables you to run the step as many times as needed to correctly configure or modify the server.</span></span> 
  

