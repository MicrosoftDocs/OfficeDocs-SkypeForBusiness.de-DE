---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference enthält die Clienteinstellungen des Benutzers. Diese wird in der Regel von Clients vor lync 2013 verwendet.
ms.openlocfilehash: 426a9f6aebe6cc6e510e2a75093b9210d3a0ba46
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814553"
---
# <a name="tblpreference"></a>tblPreference

tblPreference enthält die Clienteinstellungen des Benutzers. Diese wird in der Regel von Clients vor lync 2013 verwendet.

**Spalten**


| **Spalte**            | **Typ**                        | **Beschreibung**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255); nicht NULL  <br/> | Beschriftung mit einem Format wie: \<SIP-URI des Benutzers\>                   |
| prefSeqID  <br/>      | int, nicht NULL  <br/>            | Eine sequenzielle Zahl (pro Etikett) für die Versionsverwaltung  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | Codierter Inhalt.  <br/>                                         |
| lastModifiedBy  <br/> | int, nicht NULL  <br/>            | Die ID des Prinzipals, der die Einstellung aktualisiert hat.  <br/>         |

**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Primärschlüssel  <br/> |


