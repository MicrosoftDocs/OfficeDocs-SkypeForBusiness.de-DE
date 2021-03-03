---
title: Benutzeransicht
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: In der Benutzeransicht werden Informationen über Benutzer gespeichert, die an Anrufen oder Sitzungen teilnehmen, welche über Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 03af849f9185d90d1c7888c1946b47ee2ef38db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831695"
---
# <a name="user-view"></a>Benutzeransicht
 
In der Benutzeransicht werden Informationen über Benutzer gespeichert, die an Anrufen oder Sitzungen teilnehmen, welche über Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |URI des Benutzers  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Mandant des Benutzers. Weitere Informationen [finden Sie in der Tabelle "Mandanten".](tenants.md) <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Benutzer-URI-Typ. Weitere Informationen finden Sie in der [Tabelle "UriTypes".](uritypes.md) <br/> |
   

