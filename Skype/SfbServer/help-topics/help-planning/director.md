---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Ein Director ist ein Server mit Skype für Business Server 2015 Communications-Software, die Benutzeranfragen authentifizieren kann, jedoch ist kein Homeserver für alle Benutzerkonten.
ms.openlocfilehash: b6cdecd01183f8e249aaf97e6b4e7bbbbfcbe7cd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895972"
---
# <a name="director-planning-tool"></a>Director (Planning Tool)
 
Ein Director ist ein Server mit Skype für Business Server 2015 Communications-Software, die Benutzeranfragen authentifizieren kann, jedoch ist kein Homeserver für alle Benutzerkonten. 
  
Diese Rolle ist optional, würde der Bereitstellung eines Directors in den folgenden zwei Szenarien werden sollen:
  
- Wenn Sie Zugriff durch externe Benutzer durch die Bereitstellung von Edge-Server aktivieren, sollten Sie auch einen Director bereitstellen. In diesem Szenario der Director externe Benutzer authentifiziert und anschließend übergibt den Datenverkehr an interne Server. Wenn ein Director zur Authentifizierung externer Benutzer verwendet wird, entlastet es Front-End-Poolserver der Aufwand für das Ausführen der Authentifizierung von romotebenutzern einhergeht. Darüber hinaus werden interne Front-End-Pools bösartigem Datenverkehr wie Denial-of-Service-Angriffen zu isolieren. Wenn das Netzwerk mit ungültigen externen Datenverkehr in einem solchen Angriff bereits ist, endet dieser Datenverkehr den Director.
    
- Wenn Sie mehrere Front-End-Pools an einem zentralen Standort bereitstellen, durch Hinzufügen eines Directors in dieser Website können Authentifizierungsanfragen optimieren und die Leistung verbessert. In diesem Szenario werden alle Anforderungen ersten den Übermittler, die sie dann auf dem richtigen Front-End-Pool weitergeleitet.
    

