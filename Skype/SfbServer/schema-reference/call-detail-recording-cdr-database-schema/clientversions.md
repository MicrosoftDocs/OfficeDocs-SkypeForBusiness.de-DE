---
title: ClientVersions-Tabelle in Skype for Business Server 2015
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: Bei der ClientVersions-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der eine Liste der verschiedenen Clienttypen und -versionen gespeichert wird, die an in der Datenbank aufgezeichneten Sitzungen beteiligt sind. Jeder Datensatz in der Tabelle steht für eine Clientversion.
ms.openlocfilehash: 1cf2f237fd05937f8eea9a8c7f180ae43418fd586b59c99679770efa2205af88
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341770"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>ClientVersions-Tabelle in Skype for Business Server 2015
 
Bei der ClientVersions-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der eine Liste der verschiedenen Clienttypen und -versionen gespeichert wird, die an in der Datenbank aufgezeichneten Sitzungen beteiligt sind. Jeder Datensatz in der Tabelle steht für eine Clientversion.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |Eindeutige Zahl, die den Clienttyp und die Clientversion identifiziert.  <br/> |
|**Version** <br/> |**nvarchar(256)** <br/> ||Versionsname  <br/> |
|**ClientType** <br/> |Ganzzahl  <br/> ||Gibt den Typ des Clients an, der in der Sitzung verwendet wird. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle.](useragentdef.md) <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

