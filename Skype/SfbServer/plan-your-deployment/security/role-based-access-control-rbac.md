---
title: Rollenbasierte Zugriffssteuerung (RBAC) für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype for Business Server umfasst Role-Based Zugriffssteuerungsgruppen (Access Control, RBAC), mit denen Sie administrative Aufgaben delegieren und gleichzeitig hohe Sicherheitsstandards einhalten können. Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt. Ausführliche Informationen zur Gesamtstrukturvorbereitung finden Sie unter Active Directory Domain Services für Skype for Business Server. Ausführliche Informationen zu den spezifischen Gruppen, die durch die Gesamtstrukturvorbereitung erstellt wurden, finden Sie unter Änderungen, die von der Gesamtstrukturvorbereitung in Skype for Business Server in der Bereitstellungsdokumentation vorgenommen wurden.
ms.openlocfilehash: 8b4dbfc85a92063bff7e5c57ee18ccc9b80bb4e08b0716fd1cac0666f1862fb0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337723"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Rollenbasierte Zugriffssteuerung (RBAC) für Skype for Business Server
 
Skype for Business Server umfasst Role-Based Zugriffssteuerungsgruppen (Access Control, RBAC), mit denen Sie administrative Aufgaben delegieren und gleichzeitig hohe Sicherheitsstandards einhalten können. Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt. Ausführliche Informationen zur Gesamtstrukturvorbereitung finden Sie unter [Active Directory Domain Services für Skype for Business Server.](active-directory-domain-services.md) Ausführliche Informationen zu den spezifischen Gruppen, die durch die Gesamtstrukturvorbereitung erstellt wurden, finden Sie unter Änderungen, die von der [Gesamtstrukturvorbereitung in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation vorgenommen wurden.
  
Mit RBAC werden Administratorrechte gewährt, indem Benutzern vordefinierte Administrative Rollen zugewiesen werden, einschließlich der 11 vordefinierten Rollen, die viele allgemeine Verwaltungsaufgaben abdecken. Jede Rolle ist einer bestimmten Liste Skype for Business Server Verwaltungsshell-Cmdlets zugeordnet, die Benutzer in dieser Rolle ausführen dürfen. Sie können RBAC verwenden, um dem Prinzip der "geringsten Rechte" zu folgen, bei dem Benutzern nur die administrativen Fähigkeiten zugewiesen werden, die für ihre Aufträge erforderlich sind. 
  
Weitere Informationen zu RBAC-Rollen finden Sie unter [Planning for role-based access control](/lyncserver/lync-server-2013-planning-for-role-based-access-control).