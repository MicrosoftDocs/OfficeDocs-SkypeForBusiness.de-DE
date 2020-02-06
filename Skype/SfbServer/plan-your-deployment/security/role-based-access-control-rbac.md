---
title: Rollenbasierte Zugriffssteuerung (RBAC) für Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype for Business Server umfasst Rollenbasierte Zugriffssteuerungsgruppen, mit deren Hilfe Sie Verwaltungsaufgaben delegieren und gleichzeitig hohe Sicherheitsstandards gewährleisten können. Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt. Details zur Vorbereitung der Gesamtstruktur finden Sie unter Active Directory-Domänendienste für Skype for Business Server. Details zu den von der Gesamtstrukturvorbereitung erstellten Gruppen finden Sie unter Änderungen, die von der Gesamtstrukturvorbereitung in Skype for Business Server in der Bereitstellungsdokumentation vorgenommen wurden.
ms.openlocfilehash: 41efad45b442d9c7fca82d090afa0d1aa23e7d63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815623"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="4a71c-106">Rollenbasierte Zugriffssteuerung (RBAC) für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4a71c-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="4a71c-107">Skype for Business Server umfasst Rollenbasierte Zugriffssteuerungsgruppen, mit deren Hilfe Sie Verwaltungsaufgaben delegieren und gleichzeitig hohe Sicherheitsstandards gewährleisten können.</span><span class="sxs-lookup"><span data-stu-id="4a71c-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="4a71c-108">Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt.</span><span class="sxs-lookup"><span data-stu-id="4a71c-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="4a71c-109">Details zur Vorbereitung der Gesamtstruktur finden Sie unter [Active Directory-Domänendienste für Skype for Business Server](active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="4a71c-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="4a71c-110">Details zu den von der Gesamtstrukturvorbereitung erstellten Gruppen finden Sie unter Änderungen, die [von der Gesamtstrukturvorbereitung in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="4a71c-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="4a71c-111">Mit RBAC wird das administrative Recht gewährt, indem Nutzer vordefinierten administrativen Rollen zugewiesen werden, einschließlich der elf vordefinierten Rollen, die viele häufig verwendete administrative Aufgaben abdecken.</span><span class="sxs-lookup"><span data-stu-id="4a71c-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="4a71c-112">Jede Rolle ist mit einer bestimmten Liste von Cmdlets für die Skype for Business Server-Verwaltungsshell verknüpft, die Benutzer in dieser Rolle ausführen dürfen.</span><span class="sxs-lookup"><span data-stu-id="4a71c-112">Each role is associated with a specific list of Skype for Business Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="4a71c-113">Mit der rollenbasierten Zugriffssteuerung können Sie dem Prinzip der geringsten Rechte folgen, bei dem Nutzer nur die administrativen Funktionen erhalten, die sie für ihre Arbeit benötigen.</span><span class="sxs-lookup"><span data-stu-id="4a71c-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="4a71c-114">Weitere Informationen zu RBAC-Rollen finden Sie unter [Planen einer rollenbasierten Zugriffssteuerung](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span><span class="sxs-lookup"><span data-stu-id="4a71c-114">More details on RBAC roles can be found at [Planning for role-based access control](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span></span>
