---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: Ein Director ist ein Server mit Skype for Business Server-Kommunikationssoftware, der Benutzeranforderungen authentifizieren kann, aber keine Benutzerkonten erstellt.
ms.openlocfilehash: 0c76fb5290715bb394b4c84ffadad3a2e9dd74db
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801095"
---
# <a name="director-planning-tool"></a>Director (Planning Tool)
 
Ein Director ist ein Server mit Skype for Business Server-Kommunikationssoftware, der Benutzeranforderungen authentifizieren kann, aber keine Benutzerkonten erstellt. 
  
Diese Rolle ist optional. In den folgenden beiden Szenarien würden Sie einen Director bereitstellen:
  
- Wenn Sie den Zugriff durch externe Benutzer durch die Bereitstellung von Edgeservern aktivieren, sollten Sie auch einen Director bereitstellen. In diesem Szenario authentifiziert der Director die externen Benutzer und übergibt dann ihren Datenverkehr an interne Server. Wenn ein Director zur Authentifizierung externer Benutzer verwendet wird, entlasten sie front-End-Poolserver von dem Mehraufwand für die Authentifizierung dieser Benutzer. Es trägt außerdem dazu bei, interne Front-End-Pools vor bösartigem Datenverkehr wie Denial-of-Service-Angriffen zu schützen. Wenn das Netzwerk während eines solchen Angriffs mit ungültigem externen Datenverkehr überflutet wird, endet dieser Datenverkehr beim Director.
    
- Wenn Sie mehrere Front-End-Pools an einem zentralen Standort bereitstellen, können Sie durch Hinzufügen eines Director zu diesem Standort Authentifizierungsanforderungen optimieren und die Leistung verbessern. In diesem Szenario gehen alle Anforderungen zuerst an den Director, der sie dann an den richtigen Front-End-Pool weiter leitet.
    

