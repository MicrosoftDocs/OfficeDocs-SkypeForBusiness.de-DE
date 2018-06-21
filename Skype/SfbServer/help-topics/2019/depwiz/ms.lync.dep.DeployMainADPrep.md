---
title: Vorbereiten von Active Directory
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: Um die Installation von Skype für Business Server beginnen, müssen Sie Vorbereiten der Active Directory-Domänendienste-Schema,-Gesamtstruktur und Domänen, die Server und Benutzer hostet. Die Skype für Business Server Installations-Assistent führt Sie durch die erforderlichen Schritte zum Vorbereiten von Active Directory, beginnend mit dem Schema, und klicken Sie dann in der Vorbereitung der Gesamtstruktur. Nach der Bestätigung, dass Active Directory-Replikation erfolgreich ist, können Sie dann jede Domäne, die Benutzer oder Server hostet vorbereiten.
ms.openlocfilehash: 69c101d7aa22e5129253760883ed0d83f1c8f164
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "19991045"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="a26b0-105">Vorbereiten von Active Directory</span><span class="sxs-lookup"><span data-stu-id="a26b0-105">Prepare Active Directory</span></span>
 
<span data-ttu-id="a26b0-106">Um die Installation von Skype für Business Server beginnen, müssen Sie Vorbereiten der Active Directory-Domänendienste-Schema,-Gesamtstruktur und Domänen, die Server und Benutzer hostet.</span><span class="sxs-lookup"><span data-stu-id="a26b0-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="a26b0-107">Die Skype für Business Server Installations-Assistent führt Sie durch die erforderlichen Schritte zum Vorbereiten von Active Directory, beginnend mit dem Schema, und klicken Sie dann in der Vorbereitung der Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="a26b0-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="a26b0-108">Nach der Bestätigung, dass Active Directory-Replikation erfolgreich ist, können Sie dann jede Domäne, die Benutzer oder Server hostet vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="a26b0-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a26b0-p103">Um das Schema erfolgreich vorbereiten zu können, müssen Sie als Mitglied der Gruppen „Organisations-Admins“ und „Schema-Admins“ angemeldet sein. Zum Vorbereiten der Gesamtstruktur müssen Sie als Mitglied der Gruppe „Organisations-Admins“ oder als Administrator im Gesamtstrukturstamm angemeldet sein. Zur Vorbereitung der Domäne müssen Sie als Mitglied der Gruppe „Domänen-Admins“ angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="a26b0-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span> 
  
<span data-ttu-id="a26b0-112">Ausführliche Informationen zu den unterstützten Active Directory-Topologien finden Sie unter [Active Directory-Unterstützung](http://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a26b0-112">For details about supported Active Directory topologies, see [Active Directory Support](http://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="a26b0-113">Ausführliche Informationen zur Vorbereitung von Active Directory finden Sie unter [Übersicht über die der Domäne Services Vorbereitung von Active Directory](http://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a26b0-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](http://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>
  

