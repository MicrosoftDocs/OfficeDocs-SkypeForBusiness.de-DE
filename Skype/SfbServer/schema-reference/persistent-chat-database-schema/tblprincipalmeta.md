---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta enthält die Prinzipale, die aus Active Directory Domain Services aktualisiert werden müssen.
ms.openlocfilehash: e10b56a8a3a1c25f73cd1a07f4fdcde18c6f1215
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831545"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta enthält die Prinzipale, die aus Active Directory Domain Services aktualisiert werden müssen.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID  <br/> |
|prinAffiliationsDirty  <br/> |bit, nicht NULL  <br/> |TRUE, wenn Prinzipalzuordnungen aktualisiert werden müssen.  <br/> |
|prinAttributesDirty  <br/> |bit, nicht NULL  <br/> |TRUE, wenn Prinzipalattribute aktualisiert werden müssen.  <br/> |
|prinDeleted  <br/> |bit, nicht NULL  <br/> |TRUE, wenn der Prinzipal gelöscht wurde.  <br/> |
|tryCount  <br/> |int  <br/> |Anzahl der Versuche, den Prinzipal über AD DS zu aktualisieren, die bisher ausgeführt wurden.  <br/> |
|lastTry  <br/> |Datum/Uhrzeit  <br/> |Zeitstempel des letzten Versuchs, den Prinzipal zu aktualisieren. Kann NULL sein, wenn bisher kein Aktualisierungsversuch unternommen wurde.  <br/> |
|nextTry  <br/> |Datum/Uhrzeit  <br/> |Zeitstempel für die nächste geplante Aktualisierung. Kann NULL sein, wenn keine weitere Aktualisierung geplant ist.  <br/> |
   
**Keys**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|prinID  <br/> |Primärschlüssel  <br/> |
|prinID  <br/> |Fremdschlüssel mit Abfrage der "tblPrincipal.prinID"-Tabelle.  <br/> |
   

