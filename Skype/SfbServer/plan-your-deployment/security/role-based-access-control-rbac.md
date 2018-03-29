---
title: Rollenbasierte Zugriffssteuerung (RBAC) für Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype für Business Server 2015 enthält Role-Based Access Control (RBAC), um Sie Verwaltungsaufgaben delegieren, während gleichzeitig eine hohe Sicherheit gewährleistet bleibt zu aktivieren. Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt. Ausführliche Informationen zur Vorbereitung der Gesamtstruktur finden Sie unter Active Directory-Domänendienste für Skype Business Server 2015. Ausführliche Informationen zu bestimmten Gruppen von der Gesamtstruktur erstellt finden Sie unter Änderungen durch Vorbereitung der Gesamtstruktur in Skype für Business Server in der Bereitstellungsdokumentation.
ms.openlocfilehash: f637ef752bb122cb73220d66fd8aa19c16fb358e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server-2015"></a>Rollenbasierte Zugriffssteuerung (RBAC) für Skype for Business Server 2015
 
Skype für Business Server 2015 enthält Role-Based Access Control (RBAC), um Sie Verwaltungsaufgaben delegieren, während gleichzeitig eine hohe Sicherheit gewährleistet bleibt zu aktivieren. Diese Gruppen werden während der Gesamtstrukturvorbereitung erstellt. Ausführliche Informationen zur Vorbereitung der Gesamtstruktur finden Sie unter [Active Directory-Domänendienste für Skype für Business Server 2015](active-directory-domain-services.md). Ausführliche Informationen zu bestimmten Gruppen von der Gesamtstruktur erstellt finden Sie unter [Änderungen vorgenommen, die von der gesamtstrukturvorbereitung in Skype für Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation.
  
Mit RBAC wird das administrative Recht gewährt, indem Nutzer vordefinierten administrativen Rollen zugewiesen werden, einschließlich der elf vordefinierten Rollen, die viele häufig verwendete administrative Aufgaben abdecken. Jede Rolle ist zugeordnet, mit einer bestimmten Liste von Lync Server-Verwaltungsshell-Cmdlets, mit denen Benutzer mit dieser Rolle ausgeführt werden dürfen. Mit der rollenbasierten Zugriffssteuerung können Sie dem Prinzip der geringsten Rechte folgen, bei dem Nutzer nur die administrativen Funktionen erhalten, die sie für ihre Arbeit benötigen. 
  

