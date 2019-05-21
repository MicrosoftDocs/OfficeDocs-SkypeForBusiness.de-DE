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
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference enthält die Clienteinstellungen des Benutzers. Diese wird in der Regel von Clients vor lync 2013 verwendet.
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295342"
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


