---
title: tblPreference
ms.reviewer: null
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference enthält die Clienteinstellungen der Benutzer. Dies wird in der Regel von Clients vor Lync 2013 verwendet.
---

# <a name="tblpreference"></a>tblPreference

tblPreference enthält die Clienteinstellungen der Benutzer. Dies wird in der Regel von Clients vor Lync 2013 verwendet.

**Columns**


| **Spalte**            | **Typ**                        | **Beschreibung**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), nicht NULL  <br/> | Beschriftung mit einem Format wie z. B.: \<user sip uri\>                   |
| prefSeqID  <br/>      | int, nicht NULL  <br/>            | Eine sequenzielle Zahl (pro Bezeichnung) für Versionsverwaltungszwecke.  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | Codierter Inhalt.  <br/>                                         |
| lastModifiedBy  <br/> | int, nicht NULL  <br/>            | ID des Prinzipals, der die Einstellung aktualisiert hat.  <br/>         |

**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Primärschlüssel  <br/> |


