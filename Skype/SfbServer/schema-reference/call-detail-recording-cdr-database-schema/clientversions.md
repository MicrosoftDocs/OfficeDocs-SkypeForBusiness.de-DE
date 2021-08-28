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
ms.localizationpriority: medium
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: Bei der ClientVersions-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der eine Liste der verschiedenen Clienttypen und -versionen gespeichert wird, die an in der Datenbank aufgezeichneten Sitzungen beteiligt sind. Jeder Datensatz in der Tabelle steht für eine Clientversion.
ms.openlocfilehash: 2c03ef74e4cfe6f7989bc299c82e21500986b6f1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582589"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>ClientVersions-Tabelle in Skype for Business Server 2015
 
Bei der ClientVersions-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der eine Liste der verschiedenen Clienttypen und -versionen gespeichert wird, die an in der Datenbank aufgezeichneten Sitzungen beteiligt sind. Jeder Datensatz in der Tabelle steht für eine Clientversion.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |Eindeutige Zahl, die den Clienttyp und die Clientversion identifiziert.  <br/> |
|**Version** <br/> |**nvarchar(256)** <br/> ||Versionsname  <br/> |
|**ClientType** <br/> |int  <br/> ||Gibt den Typ des Clients an, der in der Sitzung verwendet wird. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle.](useragentdef.md) <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

