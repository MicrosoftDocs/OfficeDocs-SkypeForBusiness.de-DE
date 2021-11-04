---
title: Benutzeransicht
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 6508bac1b40ca88429cc0504982ed9d2464ee5d2
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777735"
---
# <a name="user-view"></a>Benutzeransicht
 
In der Benutzeransicht werden Informationen über Benutzer gespeichert, die an Anrufen oder Sitzungen teilnehmen, welche über Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |URI des Benutzers  <br/> |
|TenantKey  <br/> |Uniqueidentifier  <br/> |Mandant des Benutzers. Weitere Informationen finden Sie in der [Tabelle "Mandanten".](tenants.md) <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Benutzer-URI-Typ. Weitere Informationen finden Sie in der [UriTypes-Tabelle.](uritypes.md) <br/> |
   

