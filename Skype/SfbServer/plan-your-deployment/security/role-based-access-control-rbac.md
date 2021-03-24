---
title: Rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) für Skype for Business Server
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
description: Skype for Business Server umfasst Role-Based Zugriffssteuerungsgruppen (Access Control, RBAC), mit denen Sie Verwaltungsaufgaben delegieren und gleichzeitig hohe Sicherheitsstandards beibehalten können. Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt. Weitere Informationen zur Gesamtstrukturvorbereitung finden Sie unter Active Directory Domain Services for Skype for Business Server. Ausführliche Informationen zu den durch die Gesamtstrukturvorbereitung erstellten gruppen finden Sie unter Änderungen, die von der Gesamtstrukturvorbereitung in Skype for Business Server vorgenommen wurden, in der Bereitstellungsdokumentation.
ms.openlocfilehash: e02123721433e2af0ca3576ac71dd5a49a0ad9a1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104211"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) für Skype for Business Server
 
Skype for Business Server umfasst Role-Based Zugriffssteuerungsgruppen (Access Control, RBAC), mit denen Sie Verwaltungsaufgaben delegieren und gleichzeitig hohe Sicherheitsstandards beibehalten können. Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt. Weitere Informationen zur Gesamtstrukturvorbereitung finden Sie unter [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md). Ausführliche Informationen zu den durch die Gesamtstrukturvorbereitung erstellten gruppen finden Sie unter [Änderungen,](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) die von der Gesamtstrukturvorbereitung in Skype for Business Server vorgenommen wurden, in der Bereitstellungsdokumentation.
  
Mit rbAC werden Administratorrechte gewährt, indem Benutzern vordefinierte Administrative Rollen zugewiesen werden, einschließlich der 11 vordefinierten Rollen, die viele allgemeine Verwaltungsaufgaben abdecken. Jede Rolle ist einer bestimmten Liste von Skype for Business Server Management Shell-Cmdlets zugeordnet, die Benutzer in dieser Rolle ausführen dürfen. Sie können rbAC verwenden, um das Prinzip der "geringsten Rechte" zu befolgen, bei dem Benutzern nur die administrativen Fähigkeiten zur Verfügung stehen, die ihre Aufträge erfordern. 
  
Weitere Informationen zu rollenbasierten Zugriffssteuerungsrollen finden Sie unter [Planning for role-based access control](/lyncserver/lync-server-2013-planning-for-role-based-access-control).