---
title: Einrichten oder Entfernen von Komponenten von Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainBootstrap
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
ROBOTS: NOINDEX, NOFOLLOW
description: 'Zum Installieren und aktivieren oder deaktivieren oder Deinstallieren von Skype for Business Server-Komponenten verwenden Sie Schritt 2: Einrichten oder Entfernen von Skype Server-Komponenten. Sie müssen als lokaler Administrator auf dem Computer angemeldet sein, den Sie installieren oder ändern, und Sie müssen in der Lage sein, die Active Directory-Domänendienste-Benutzer und-Gruppen in der aktuellen Domäne zu lesen. Klicken Sie auf Ausführen, um zu beginnen. Beim Ausführen dieses Schritts wird die auf dem zentralen Verwaltungsspeicher basierende Topologiedefinition gelesen. Die erforderlichen Softwarekomponenten werden gemäß der im zentralen Verwaltungsspeicher definierten Rolle installiert und konfiguriert. Zeigen Sie nach Abschluss der Installation die Zusammenfassung an und klicken Sie auf Fertig stellen.'
ms.openlocfilehash: d19d4946af48f96066d01cea33f0a5c04c22f816
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798362"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a><span data-ttu-id="66d77-108">Einrichten oder Entfernen von Komponenten von Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="66d77-108">Setup or Remove Skype for Business Server Components</span></span>
 
<span data-ttu-id="66d77-109">Zum Installieren und aktivieren oder deaktivieren oder Deinstallieren von Skype for Business Server-Komponenten verwenden Sie **Schritt 2: Einrichten oder Entfernen von Skype Server-Komponenten**.</span><span class="sxs-lookup"><span data-stu-id="66d77-109">To install and activate, or deactivate or uninstall Skype for Business Server components, you use **Step 2: Setup or Remove Skype Server Components**.</span></span> <span data-ttu-id="66d77-110">Sie müssen als lokaler Administrator auf dem Computer angemeldet sein, den Sie installieren oder ändern, und Sie müssen in der Lage sein, die Active Directory-Domänendienste-Benutzer und-Gruppen in der aktuellen Domäne zu lesen.</span><span class="sxs-lookup"><span data-stu-id="66d77-110">You must be logged in as a local administrator on the computer that you are installing or modifying and must be able to read Active Directory Domain Services users and groups in the current domain.</span></span> <span data-ttu-id="66d77-111">Klicken Sie auf **Ausführen**, um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="66d77-111">To begin, click **Run**.</span></span> <span data-ttu-id="66d77-112">Beim Ausführen dieses Schritts wird die auf dem zentralen Verwaltungsspeicher basierende Topologiedefinition gelesen.</span><span class="sxs-lookup"><span data-stu-id="66d77-112">When you do this, the Central Management store-based topology definition is read.</span></span> <span data-ttu-id="66d77-113">Die erforderlichen Softwarekomponenten werden gemäß der im zentralen Verwaltungsspeicher definierten Rolle installiert und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="66d77-113">Necessary software components are installed and configured, according to the role as defined in the Central Management store.</span></span> <span data-ttu-id="66d77-114">Zeigen Sie nach Abschluss der Installation die Zusammenfassung an und klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="66d77-114">When the installation is complete, review the Summary, and click **Finish**.</span></span>
  
> [!TIP]
> <span data-ttu-id="66d77-115">Wenn Sie die vom Bereitstellungs-Assistenten erstellten Protokolldateien überprüfen müssen, können Sie diese auf dem Computer finden, auf dem der Bereitstellungs-Assistent ausgeführt wurde, und zwar im Verzeichnis Benutzer des Active Directory-Benutzers, der den Schritt ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="66d77-115">If you need to review the log files that are created by the Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="66d77-116">Wenn sich der Benutzer beispielsweise als Domänenadministrator im Domänen contoso.net angemeldet hat, befinden sich die Protokolldateien in: #a0 C:\users\administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="66d77-116">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  
> [!NOTE]
> <span data-ttu-id="66d77-117">Wenn Sie zuvor Skype for Business Server-Komponenten auf diesem Computer installiert haben, wird dies vom Bereitstellungs-Assistenten erkannt, und die Schaltfläche in Schritt 2 wird als **erneut ausführen**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="66d77-117">If you have previously installed Skype for Business Server components on this computer, the Deployment Wizard will recognize this, and the button in step 2 will be displayed as **Run Again**.</span></span> <span data-ttu-id="66d77-118">So können Sie den Schritt bei Bedarf mehrfach ausführen, um den Server ordnungsgemäß zu konfigurieren oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="66d77-118">This enables you to run the step as many times as needed to correctly configure or modify the server.</span></span> 
  

