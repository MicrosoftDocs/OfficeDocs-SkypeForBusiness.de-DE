---
title: Benutzeransicht
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: In der Benutzeransicht werden Informationen über Benutzer gespeichert, die an Anrufen oder Sitzungen teilnehmen, welche über Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 448577f4379bc4db690569333c6d912f777e408e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404507"
---
# <a name="user-view"></a>Benutzeransicht
 
In der Benutzeransicht werden Informationen über Benutzer gespeichert, die an Anrufen oder Sitzungen teilnehmen, welche über Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |URI des Benutzers  <br/> |
|TenantKey  <br/> |Uniqueidentifier  <br/> |Mandant des Benutzers. Weitere Informationen finden Sie in der [Tabelle "Mandanten](tenants.md) ". <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Benutzer-URI-Typ. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
   

