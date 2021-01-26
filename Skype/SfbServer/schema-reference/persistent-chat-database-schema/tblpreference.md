---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: "\"tblPreference\" enthält die Clienteinstellungen der Benutzer. Dies wird in der Regel von Clients vor Lync 2013 verwendet."
ms.openlocfilehash: 96cd017dd67a05f3240269f5bdcbd23f30fffd28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815905"
---
# <a name="tblpreference"></a>tblPreference

"tblPreference" enthält die Clienteinstellungen der Benutzer. Dies wird in der Regel von Clients vor Lync 2013 verwendet.

**Columns**


| **Spalte**            | **Typ**                        | **Beschreibung**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), nicht NULL  <br/> | Bezeichnung mit einem Format wie: \<user sip uri\>                   |
| prefSeqID  <br/>      | int, nicht NULL  <br/>            | Eine sequenzielle Zahl (pro Bezeichnung) für Versionszwecke.  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | Codierter Inhalt.  <br/>                                         |
| lastModifiedBy  <br/> | int, nicht NULL  <br/>            | ID des Prinzipal, der die Einstellung aktualisiert hat.  <br/>         |

**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Primärschlüssel  <br/> |


