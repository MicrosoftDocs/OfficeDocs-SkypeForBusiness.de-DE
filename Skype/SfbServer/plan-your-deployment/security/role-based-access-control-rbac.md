---
title: Rollenbasierte Zugriffssteuerung (RBAC) für Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype für Business Server enthält Role-Based Access Control (RBAC), um Sie Verwaltungsaufgaben delegieren, während gleichzeitig eine hohe Sicherheit gewährleistet bleibt zu aktivieren. Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt. Ausführliche Informationen zur gesamtstrukturvorbereitung finden Sie unter Active Directory-Domänendienste für Skype für Business Server. Ausführliche Informationen zu bestimmten Gruppen von der Gesamtstruktur erstellt finden Sie unter Änderungen durch Vorbereitung der Gesamtstruktur in Skype für Business Server in der Bereitstellungsdokumentation.
ms.openlocfilehash: 461fa82809b16ccf6db1ac02e7c8d0e6698e2b61
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894273"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="9cd9d-106">Rollenbasierte Zugriffssteuerung (RBAC) für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="9cd9d-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="9cd9d-107">Skype für Business Server enthält Role-Based Access Control (RBAC), um Sie Verwaltungsaufgaben delegieren, während gleichzeitig eine hohe Sicherheit gewährleistet bleibt zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9cd9d-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="9cd9d-108">Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt.</span><span class="sxs-lookup"><span data-stu-id="9cd9d-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="9cd9d-109">Ausführliche Informationen zur Vorbereitung der Gesamtstruktur finden Sie unter [Active Directory-Domänendienste für Skype für Business Server](active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="9cd9d-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="9cd9d-110">Ausführliche Informationen zu bestimmten Gruppen von der Gesamtstruktur erstellt finden Sie unter [Änderungen vorgenommen, die von der gesamtstrukturvorbereitung in Skype für Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9cd9d-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="9cd9d-111">Mit RBAC wird das administrative Recht gewährt, indem Nutzer vordefinierten administrativen Rollen zugewiesen werden, einschließlich der elf vordefinierten Rollen, die viele häufig verwendete administrative Aufgaben abdecken.</span><span class="sxs-lookup"><span data-stu-id="9cd9d-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="9cd9d-112">Jede Rolle ist zugeordnet, mit einer bestimmten Liste von Lync Server-Verwaltungsshell-Cmdlets, mit denen Benutzer mit dieser Rolle ausgeführt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="9cd9d-112">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="9cd9d-113">Mit der rollenbasierten Zugriffssteuerung können Sie dem Prinzip der geringsten Rechte folgen, bei dem Nutzer nur die administrativen Funktionen erhalten, die sie für ihre Arbeit benötigen.</span><span class="sxs-lookup"><span data-stu-id="9cd9d-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="9cd9d-114">Weitere Informationen zu RBAC-Rollen finden Sie unter:https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx</span><span class="sxs-lookup"><span data-stu-id="9cd9d-114">More details on RBAC roles can be found at: https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx</span></span>
