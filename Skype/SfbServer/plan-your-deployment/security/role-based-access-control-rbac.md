---
title: Rollenbasierte Zugriffssteuerung (RBAC) für Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype für Business Server enthält Role-Based Access Control (RBAC), um Sie Verwaltungsaufgaben delegieren, während gleichzeitig eine hohe Sicherheit gewährleistet bleibt zu aktivieren. Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt. Ausführliche Informationen zur gesamtstrukturvorbereitung finden Sie unter Active Directory-Domänendienste für Skype für Business Server. Ausführliche Informationen zu bestimmten Gruppen von der Gesamtstruktur erstellt finden Sie unter Änderungen durch Vorbereitung der Gesamtstruktur in Skype für Business Server in der Bereitstellungsdokumentation.
ms.openlocfilehash: 34f5fa455b865e40ba2ad21298e37d0948d2a810
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914205"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Rollenbasierte Zugriffssteuerung (RBAC) für Skype für Business Server
 
Skype für Business Server enthält Role-Based Access Control (RBAC), um Sie Verwaltungsaufgaben delegieren, während gleichzeitig eine hohe Sicherheit gewährleistet bleibt zu aktivieren. Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt. Ausführliche Informationen zur Vorbereitung der Gesamtstruktur finden Sie unter [Active Directory-Domänendienste für Skype für Business Server](active-directory-domain-services.md). Ausführliche Informationen zu bestimmten Gruppen von der Gesamtstruktur erstellt finden Sie unter [Änderungen vorgenommen, die von der gesamtstrukturvorbereitung in Skype für Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation.
  
Mit RBAC wird das administrative Recht gewährt, indem Nutzer vordefinierten administrativen Rollen zugewiesen werden, einschließlich der elf vordefinierten Rollen, die viele häufig verwendete administrative Aufgaben abdecken. Jede Rolle ist zugeordnet, mit einer bestimmten Liste von Lync Server-Verwaltungsshell-Cmdlets, mit denen Benutzer mit dieser Rolle ausgeführt werden dürfen. Mit der rollenbasierten Zugriffssteuerung können Sie dem Prinzip der geringsten Rechte folgen, bei dem Nutzer nur die administrativen Funktionen erhalten, die sie für ihre Arbeit benötigen. 
  
Weitere Informationen zu RBAC-Rollen finden Sie unter:https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx
