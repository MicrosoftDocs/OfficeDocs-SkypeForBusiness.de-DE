---
title: Filetransfers-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: Jeder Datensatz stellt eine Dateiübertragungssitzung dar.
ms.openlocfilehash: 8b287d2fc2c40fe7e20cb3abc4ed6e403da701b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815213"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Filetransfers-Tabelle in Skype for Business Server 2015
 
Jeder Datensatz stellt eine Dateiübertragungssitzung dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionID** <br/> |datetime  <br/> |Primär, fremd  <br/> |Uhrzeit der Sitzungsanforderung. Wird in Verbindung mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, fremd  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit **SessionID** -Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**Dateiname** <br/> |nvarchar(256)  <br/> ||Der Name der Datei.  <br/> |
|**Fileidentity** <br/> |uniqueidentifier  <br/> ||Eindeutiger Bezeichner zur Unterscheidung Zwischendatei Übertragungen mit demselben Dateinamen.  <br/> |
|**Cookie** <br/> |nvarchar (128)  <br/> |Primary  <br/> |Wird verwendet, um jede nach Verfolgungs Nachricht als zugeordnet zu kennzeichnen.  <br/> |
|**Annehmen** <br/> |bit  <br/> ||Kann "wahr" oder "Null" sein. Ist "true", ist "ablehnen" und "Abbrechen" NULL.  <br/> |
|**Ablehnen** <br/> |bit  <br/> ||Kann "wahr" oder "Null" sein. Ist "true", ist "akzeptieren" und "Abbrechen" NULL.  <br/> |
|**Abbrechen** <br/> |bit  <br/> ||Kann "wahr" oder "Null" sein. Ist "true", ist "annehmen und ablehnen" NULL.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

