---
title: UserAgent-Ansicht
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: Die UserAgent-Ansicht speichert Informationen über die Benutzeragenten, die an Sitzungen teilgenommen haben und die über Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: d6ed446c429c3e055d3b5387f4675eaed7fb1f9e992d7211346309254549b66d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282987"
---
# <a name="useragent-view"></a>UserAgent-Ansicht
 
Die UserAgent-Ansicht speichert Informationen über die Benutzeragenten, die an Sitzungen teilgenommen haben und die über Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |Ganzzahl  <br/> |Eindeutige Zahl, die diesen Benutzer-Agent identifiziert.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Zeichenfolge des Benutzer-Agents.  <br/> |
|UAType  <br/> |Smallint  <br/> |Benutzeragententyp. Weitere Informationen finden Sie in der [UserAgent-Tabelle.](useragent.md) <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |Die Kategorie, der der Benutzer-Agent angehört. Beispielsweise weist der Benutzer-Agent Conferencing_Attendant_1.0 eine UACategory von CAA auf.  <br/> |
   

