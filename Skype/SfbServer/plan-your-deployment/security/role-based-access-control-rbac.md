---
title: Rollenbasierte Zugriffssteuerung (RBAC) für Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype for Business Server umfasst Role-Based RBAC-Gruppen (Access Control), mit denen Sie administrative Aufgaben delegieren und gleichzeitig hohe Sicherheitsstandards beibehalten können. Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt. Ausführliche Informationen zur Gesamtstrukturvorbereitung finden Sie unter Active Directory Domain Services für Skype for Business Server. Ausführliche Informationen zu den spezifischen Gruppen, die durch die Gesamtstrukturvorbereitung erstellt wurden, finden Sie unter Änderungen, die von der Gesamtstrukturvorbereitung in Skype for Business Server in der Bereitstellungsdokumentation vorgenommen wurden.
ms.openlocfilehash: 05f1b4873e6d671ecb53e6778a67b5558d4aa1ee
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60744102"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Rollenbasierte Zugriffssteuerung (RBAC) für Skype for Business Server
 
Skype for Business Server umfasst Role-Based RBAC-Gruppen (Access Control), mit denen Sie administrative Aufgaben delegieren und gleichzeitig hohe Sicherheitsstandards beibehalten können. Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt. Ausführliche Informationen zur Gesamtstrukturvorbereitung finden Sie unter [Active Directory Domain Services für Skype for Business Server.](active-directory-domain-services.md) Ausführliche Informationen zu den spezifischen Gruppen, die durch die Gesamtstrukturvorbereitung erstellt wurden, finden Sie unter Änderungen, die durch die [Gesamtstrukturvorbereitung in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation vorgenommen wurden.
  
Mit RBAC werden Administratorrechte gewährt, indem Benutzern vordefinierte Administrative Rollen zugewiesen werden, einschließlich der 11 vordefinierten Rollen, die viele allgemeine Verwaltungsaufgaben abdecken. Jede Rolle ist einer bestimmten Liste Skype for Business Server Verwaltungsshell-Cmdlets zugeordnet, die Benutzer in dieser Rolle ausführen dürfen. Sie können RBAC verwenden, um dem Prinzip der "geringsten Rechte" zu folgen, bei dem Benutzern nur die administrativen Fähigkeiten zugewiesen werden, die für ihre Aufträge erforderlich sind. 
  
Weitere Informationen zu RBAC-Rollen finden Sie unter [Planning for role-based access control](/lyncserver/lync-server-2013-planning-for-role-based-access-control).