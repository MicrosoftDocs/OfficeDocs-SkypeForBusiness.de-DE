---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: "\"tblprincipalmeta\" enthält die Prinzipale, die aus Active Directory Domain Services aktualisiert werden müssen."
ms.openlocfilehash: 049a273f7134ecb945e62da39469bcaf0defbffb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889607"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
"tblprincipalmeta" enthält die Prinzipale, die aus Active Directory Domain Services aktualisiert werden müssen.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |Int, nicht null  <br/> |Prinzipal-ID.  <br/> |
|prinAffiliationsDirty  <br/> |Bit, nicht null  <br/> |True, wenn prinzipalzuordnungen aktualisiert werden müssen.  <br/> |
|prinAttributesDirty  <br/> |Bit, nicht null  <br/> |True, wenn prinzipalattribute aktualisiert werden müssen.  <br/> |
|prinDeleted  <br/> |Bit, nicht null  <br/> |True, wenn der Prinzipal gelöscht wurde.  <br/> |
|tryCount  <br/> |int  <br/> |Anzahl der Versuche zum Erstellen den Prinzipal aus AD DS zu aktualisieren, die bisher ausgeführt wurden.  <br/> |
|lastTry  <br/> |datetime  <br/> |Zeitstempel vom aktuellen Versuch, den Prinzipal zu aktualisieren. Kann null sein, wenn noch keine Aktualisierung versucht wurde.  <br/> |
|nextTry  <br/> |datetime  <br/> |Zeitstempel für die nächste geplante Aktualisierung. Kann null sein, wenn keine weiteren Refresh geplant wurde.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|prinID  <br/> |Primärschlüssel.  <br/> |
|prinID  <br/> |Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.  <br/> |
   

