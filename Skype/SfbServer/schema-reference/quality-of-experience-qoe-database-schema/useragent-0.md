---
title: UserAgent-Ansicht
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: Die UserAgent-Ansicht speichert Informationen über die Benutzeragenten, die an Sitzungen teilgenommen haben und die über Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 605ba868845bbfdd6f425997e59b5fc46dc5924b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834823"
---
# <a name="useragent-view"></a>UserAgent-Ansicht
 
Die UserAgent-Ansicht speichert Informationen über die Benutzeragenten, die an Sitzungen teilgenommen haben und die über Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Eindeutige Zahl, die diesen Benutzer-Agent identifiziert.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Zeichenfolge des Benutzer-Agents.  <br/> |
|UAType  <br/> |Smallint  <br/> |Benutzeragententyp. Weitere Informationen finden Sie in der [UserAgent-Tabelle.](useragent.md) <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |Die Kategorie, der der Benutzer-Agent angehört. Beispielsweise weist der Benutzer-Agent Conferencing_Attendant_1.0 eine UACategory von CAA auf.  <br/> |
   

