---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference enthält die Clienteinstellungen der Benutzer. Dies wird in der Regel von Clients vor Lync 2013 verwendet.
ms.openlocfilehash: 24de89ff74da66023aeac696c7f3ae91fb9b98b1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768449"
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


