---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: Ein Director ist ein Server, auf dem Skype for Business Server Kommunikationssoftware ausgeführt wird, der Benutzeranforderungen authentifizieren kann, aber keine Benutzerkonten verwaltet.
ms.openlocfilehash: 1d7d65502e6c306a1ed709dbd3c1f6a66370f14a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833661"
---
# <a name="director-planning-tool"></a>Director (Planning Tool)
 
Ein Director ist ein Server, auf dem Skype for Business Server Kommunikationssoftware ausgeführt wird, der Benutzeranforderungen authentifizieren kann, aber keine Benutzerkonten verwaltet. 
  
Diese Rolle ist optional. In den folgenden beiden Szenarien würden Sie einen Director bereitstellen:
  
- Wenn Sie den Zugriff durch externe Benutzer durch die Bereitstellung von Edgeservern aktivieren, sollten Sie auch einen Director bereitstellen. In diesem Szenario authentifiziert der Director die externen Benutzer und übergibt dann den Datenverkehr an interne Server. Wenn ein Director verwendet wird, um externe Benutzer zu authentifizieren, werden Front-End-Poolserver vom Mehraufwand für die Authentifizierung dieser Benutzer gehindert. Außerdem können interne Front-End-Pools vor bösartigem Datenverkehr wie Denial-of-Service-Angriffen isoliert werden. Wenn das Netzwerk während eines solchen Angriffs mit ungültigem externen Datenverkehr überflutet wird, endet dieser Datenverkehr beim Director.
    
- Wenn Sie mehrere Front-End-Pools an einem zentralen Standort bereitstellen, können Sie durch Hinzufügen eines Director zu diesem Standort Authentifizierungsanforderungen optimieren und die Leistung verbessern. In diesem Szenario gehen alle Anforderungen zuerst an den Director, der sie dann an den richtigen Front-End-Pool weitergibt.
    

