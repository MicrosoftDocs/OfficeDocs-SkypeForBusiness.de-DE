---
title: Anfordern, Installieren oder Zuweisen von Zertifikaten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
description: 'In Schritt 3: Anfordern, Installieren und Zuweisen von Zertifikaten wird beim Klicken auf Ausführen der Zertifikat-Assistent gestartet. Die über den Assistenten konfigurierten Zertifikate basieren auf der Definition der Skype for Business Server 2015-Topologie, die vom Topologie-Generator im zentralen Verwaltungsspeicher konfiguriert und veröffentlicht wurde. Damit der Zertifikat-Assistent für eine Onlinezertifizierungsstelle in Ihrer Organisation erfolgreich ausgeführt werden kann, müssen Sie am Computer als Mitglied der lokalen Gruppe „Administratoren“ angemeldet sein. Ferner müssen Sie ein authentifizierter Domänenbenutzer in der Domäne des Computers und der Zertifizierungsstelle sein. Der Zertifikat-Assistent bietet die Möglichkeit, Alternative Anmeldeinformationen für den Zugriff auf die Zertifizierungsstelle Ihrer Organisation anzugeben.'
ms.openlocfilehash: b5d3c224142d4e457f584faa440b4fd4000497b3
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687288"
---
# <a name="request-install-or-assign-certificates"></a><span data-ttu-id="8dc2f-107">Anfordern, Installieren oder Zuweisen von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="8dc2f-107">Request, Install, or Assign Certificates</span></span>
 
 <span data-ttu-id="8dc2f-108">In **Schritt 3: Anfordern, Installieren und Zuweisen von Zertifikaten** wird beim Klicken auf **Ausführen** der Zertifikat-Assistent gestartet.</span><span class="sxs-lookup"><span data-stu-id="8dc2f-108">**Step 3: Request, Install or Assign Certificates** starts the Certificate Wizard when you click **Run**.</span></span> <span data-ttu-id="8dc2f-109">Die über den Assistenten konfigurierten Zertifikate basieren auf der Definition der Skype for Business Server 2015-Topologie, die vom Topologie-Generator im zentralen Verwaltungsspeicher konfiguriert und veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="8dc2f-109">The certificates that are configured through the wizard are based on the definition of the Skype for Business Server 2015 topology that is configured and published by Topology Builder to the Central Management store.</span></span> <span data-ttu-id="8dc2f-110">Damit der Zertifikat-Assistent für eine Onlinezertifizierungsstelle in Ihrer Organisation erfolgreich ausgeführt werden kann, müssen Sie am Computer als Mitglied der lokalen Gruppe „Administratoren“ angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="8dc2f-110">To successfully run the Certificate Wizard for an online certification authority (CA) in your organization, you must be logged on to the computer as a user who is a member of the computer local administrators group.</span></span> <span data-ttu-id="8dc2f-111">Ferner müssen Sie ein authentifizierter Domänenbenutzer in der Domäne des Computers und der Zertifizierungsstelle sein.</span><span class="sxs-lookup"><span data-stu-id="8dc2f-111">You must also be an authenticated Domain User in the domain where the computer and the CA exist.</span></span> <span data-ttu-id="8dc2f-112">Der Zertifikat-Assistent bietet die Möglichkeit, Alternative Anmeldeinformationen für den Zugriff auf die Zertifizierungsstelle Ihrer Organisation anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8dc2f-112">The certificate wizard does provide the ability to specify alternate credentials for access your organization's CA.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8dc2f-p103">Sie können mithilfe des Zertifikat-Assistenten auch Offlinezertifikatsanforderungen erstellen und verarbeiten, die an eine öffentliche Zertifizierungsstelle oder eine andere Offline-PKI (Public Key-Infrastruktur) gesendet werden. Zum Erstellen einer Offlineanforderung sind nur die üblichen Berechtigungen für die Anmeldung am Computer erforderlich. Zum Verarbeiten der Antwort der öffentlichen Zertifizierungsstelle und zum Zuweisen des Zertifikats zum jeweiligen Computer bzw. zur jeweiligen Rolle müssen Sie als Mitglied der lokalen Gruppe „Administratoren“ (oder einer ähnlichen Gruppe) angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="8dc2f-p103">You can also use the Certificate Wizard to request and process offline certificate requests that are sent to a public CA or other offline public key infrastructure (PKI). There are no specific group memberships, other than those needed to log on to the computer, to generate an offline request. To process the public CA response and to assign the certificate to the computer and role, you must be logged on as a member of the local Administrators group or equivalent.</span></span> 
  

