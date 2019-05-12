---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: TblPreference enthält die Clientvoreinstellungen der der Benutzer. Dies wird im Allgemeinen von Clients vor Lync 2013 verwendet.
ms.openlocfilehash: 1c8b098d308802428dcb314d2163b9e32863b547
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929918"
---
# <a name="tblpreference"></a>tblPreference

TblPreference enthält die Clientvoreinstellungen der der Benutzer. Dies wird im Allgemeinen von Clients vor Lync 2013 verwendet.

**Spalten**


| **Spalte**            | **Typ**                        | **Beschreibung**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | Nvarchar (255), nicht null  <br/> | Bezeichnen mit einem Format, z. B.: \<Sip-Uri des Benutzers\>                   |
| prefSeqID  <br/>      | Int, nicht null  <br/>            | Fortlaufende Zahl (pro Bezeichnung) für die versionsverwaltung.  <br/> |
| prefContent  <br/>    | Nvarchar (Max.)  <br/>           | Verschlüsselter Inhalt.  <br/>                                         |
| lastModifiedBy  <br/> | Int, nicht null  <br/>            | ID des Prinzipals, der die Voreinstellung aktualisiert hat.  <br/>         |

**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<PrefLabel prefSeqID\>  <br/> |Primärschlüssel.  <br/> |


