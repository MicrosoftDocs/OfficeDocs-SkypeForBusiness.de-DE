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
ms.localizationpriority: medium
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta enthält die Prinzipale, die von Active Directory Domain Services aktualisiert werden müssen.
ms.openlocfilehash: fd67a9ff2ff68f919ebbff54a0eea2ba59aa7949
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620841"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta enthält die Prinzipale, die von Active Directory Domain Services aktualisiert werden müssen.
  
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
   

