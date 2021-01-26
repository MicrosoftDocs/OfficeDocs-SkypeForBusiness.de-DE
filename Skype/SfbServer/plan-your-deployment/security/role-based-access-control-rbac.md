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
description: Skype for Business Server enthält Role-Based Access Control (RBAC)-Gruppen, mit denen Sie Verwaltungsaufgaben delegieren und gleichzeitig hohe Sicherheitsstandards beibehalten können. Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt. Weitere Informationen zur Gesamtstrukturvorbereitung finden Sie unter Active Directory Domain Services for Skype for Business Server. Ausführliche Informationen zu den von der Gesamtstrukturvorbereitung erstellten Gruppen finden Sie unter "Änderungen, die bei der Gesamtstrukturvorbereitung in Skype for Business Server vorgenommen wurden" in der Bereitstellungsdokumentation.
ms.openlocfilehash: 9d3c453d4e7c3057c03f99cf2ff31b5fe17ae0bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832105"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Rollenbasierte Zugriffssteuerung (RBAC) für Skype for Business Server
 
Skype for Business Server enthält Role-Based Access Control (RBAC)-Gruppen, mit denen Sie Verwaltungsaufgaben delegieren und gleichzeitig hohe Sicherheitsstandards beibehalten können. Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt. Weitere Informationen zur Gesamtstrukturvorbereitung finden Sie unter [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md). Ausführliche Informationen zu den von der Gesamtstrukturvorbereitung erstellten Gruppen finden Sie unter "Änderungen, die bei der Gesamtstrukturvorbereitung [in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) vorgenommen wurden" in der Bereitstellungsdokumentation.
  
Mit rbAC werden Administratorrechte gewährt, indem Benutzer vordefinierten Administratorrollen zugewiesen werden, einschließlich der 11 vordefinierten Rollen, die viele allgemeine Verwaltungsaufgaben abdecken. Jede Rolle ist einer bestimmten Liste von Skype for Business Server Management Shell-Cmdlets zugeordnet, die Benutzer in dieser Rolle ausführen dürfen. Sie können rbAC verwenden, um dem Prinzip der geringsten Rechte zu folgen, bei dem Benutzern nur die administrativen Fähigkeiten zur Verfügung stehen, die für ihre Aufträge erforderlich sind. 
  
Weitere Informationen zu rollenbasierten Zugriffssteuerungsrollen finden Sie unter ["Planen der rollenbasierten Zugriffssteuerung".](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)
