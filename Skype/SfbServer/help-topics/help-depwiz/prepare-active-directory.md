---
title: Vorbereiten von Active Directory
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: Um die Installation von Skype für Business Server 2015 beginnen, müssen Sie Vorbereiten der Active Directory-Domänendienste-Schema,-Gesamtstruktur und Domänen, die Server und Benutzer hostet. Die Skype für Business Server Installations-Assistent führt Sie durch die erforderlichen Schritte zum Vorbereiten von Active Directory, beginnend mit dem Schema, und klicken Sie dann in der Vorbereitung der Gesamtstruktur. Nach der Bestätigung, dass Active Directory-Replikation erfolgreich ist, können Sie dann jede Domäne, die Benutzer oder Server hostet vorbereiten.
ms.openlocfilehash: ba7cbe0b0cf571cc06637cba4e3047016e68f781
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885055"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="b3642-105">Vorbereiten von Active Directory</span><span class="sxs-lookup"><span data-stu-id="b3642-105">Prepare Active Directory</span></span>

<span data-ttu-id="b3642-106">Um die Installation von Skype für Business Server 2015 beginnen, müssen Sie Vorbereiten der Active Directory-Domänendienste-Schema,-Gesamtstruktur und Domänen, die Server und Benutzer hostet.</span><span class="sxs-lookup"><span data-stu-id="b3642-106">To begin the installation of Skype for Business Server 2015, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="b3642-107">Die Skype für Business Server Installations-Assistent führt Sie durch die erforderlichen Schritte zum Vorbereiten von Active Directory, beginnend mit dem Schema, und klicken Sie dann in der Vorbereitung der Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="b3642-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="b3642-108">Nach der Bestätigung, dass Active Directory-Replikation erfolgreich ist, können Sie dann jede Domäne, die Benutzer oder Server hostet vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="b3642-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3642-p103">Um das Schema erfolgreich vorbereiten zu können, müssen Sie als Mitglied der Gruppen „Organisations-Admins“ und „Schema-Admins“ angemeldet sein. Zum Vorbereiten der Gesamtstruktur müssen Sie als Mitglied der Gruppe „Organisations-Admins“ oder als Administrator im Gesamtstrukturstamm angemeldet sein. Zur Vorbereitung der Domäne müssen Sie als Mitglied der Gruppe „Domänen-Admins“ angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="b3642-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="b3642-p104">Ausführliche Informationen zu unterstützten Active Directory-Topologien finden Sie unter [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in der Unterstützungsdokumentation. Ausführliche Informationen zur Active Directory-Vorbereitung finden Sie unter [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b3642-p104">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation. For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


