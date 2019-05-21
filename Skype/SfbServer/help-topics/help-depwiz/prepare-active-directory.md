---
title: Vorbereiten von Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: Um mit der Installation von Skype for Business Server 2015 zu beginnen, müssen Sie das Active Directory-Domänendienste-Schema, die Gesamtstruktur und die Domänen vorbereiten, die Server und Benutzer hosten werden. Der Bereitstellungs-Assistent von Skype for Business Server führt Sie durch die Schritte, die erforderlich sind, um Active Directory vorzubereiten, beginnend mit dem Schema und dann in die Gesamtstrukturvorbereitung. Nachdem Sie bestätigt haben, dass die Active Directory-Replikation erfolgreich ist, bereiten Sie dann jede Domäne vor, die Benutzer oder Server hostet.
ms.openlocfilehash: a7b908bb1c6194e1b6d9b12a90d250d09815ea5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283753"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="33627-105">Vorbereiten von Active Directory</span><span class="sxs-lookup"><span data-stu-id="33627-105">Prepare Active Directory</span></span>

<span data-ttu-id="33627-106">Um mit der Installation von Skype for Business Server 2015 zu beginnen, müssen Sie das Active Directory-Domänendienste-Schema, die Gesamtstruktur und die Domänen vorbereiten, die Server und Benutzer hosten werden.</span><span class="sxs-lookup"><span data-stu-id="33627-106">To begin the installation of Skype for Business Server 2015, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="33627-107">Der Bereitstellungs-Assistent von Skype for Business Server führt Sie durch die Schritte, die erforderlich sind, um Active Directory vorzubereiten, beginnend mit dem Schema und dann in die Gesamtstrukturvorbereitung.</span><span class="sxs-lookup"><span data-stu-id="33627-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="33627-108">Nachdem Sie bestätigt haben, dass die Active Directory-Replikation erfolgreich ist, bereiten Sie dann jede Domäne vor, die Benutzer oder Server hostet.</span><span class="sxs-lookup"><span data-stu-id="33627-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33627-p103">Um das Schema erfolgreich vorbereiten zu können, müssen Sie als Mitglied der Gruppen „Organisations-Admins“ und „Schema-Admins“ angemeldet sein. Zum Vorbereiten der Gesamtstruktur müssen Sie als Mitglied der Gruppe „Organisations-Admins“ oder als Administrator im Gesamtstrukturstamm angemeldet sein. Zur Vorbereitung der Domäne müssen Sie als Mitglied der Gruppe „Domänen-Admins“ angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="33627-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="33627-p104">Ausführliche Informationen zu unterstützten Active Directory-Topologien finden Sie unter [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in der Unterstützungsdokumentation. Ausführliche Informationen zur Active Directory-Vorbereitung finden Sie unter [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="33627-p104">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation. For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


