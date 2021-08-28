---
title: Skype for Business Server Director-Planungstool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
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
description: Ein Director ist ein Server mit Skype for Business Server 2015-Kommunikationssoftware, der Benutzeranforderungen authentifizieren kann, aber keine Benutzerkonten verwaltet.
ms.openlocfilehash: 3e28c88621d200517ec64e109ea94bc09a442218
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602670"
---
# <a name="skype-for-business-server-director-planning-tool"></a>Skype for Business Server Director-Planungstool
 
Ein Director ist ein Server mit Skype for Business Server 2015-Kommunikationssoftware, der Benutzeranforderungen authentifizieren kann, aber keine Benutzerkonten verwaltet. 
  
Diese Rolle ist optional. In den folgenden beiden Szenarien würden Sie einen Director bereitstellen:
  
- Wenn Sie den Zugriff durch Gastbenutzer durch die Bereitstellung von Edgeservern aktivieren, sollten Sie auch einen Director bereitstellen. In diesem Szenario authentifiziert der Director die Gäste und übergibt dann den Datenverkehr an interne Server. Wenn ein Director zum Authentifizieren von Gästen verwendet wird, wird der Aufwand für die Authentifizierung dieser Benutzer auf Front-End-Poolserver reduziert. Außerdem können interne Front-End-Pools vor bösartigem Datenverkehr wie Denial-of-Service-Angriffen isoliert werden. Wenn das Netzwerk während eines solchen Angriffs mit ungültigem externen Datenverkehr überflutet wird, endet dieser Datenverkehr beim Director.
    
- Wenn Sie mehrere Front-End-Pools an einem zentralen Standort bereitstellen, können Sie durch Hinzufügen eines Director zu diesem Standort Authentifizierungsanforderungen optimieren und die Leistung verbessern. In diesem Szenario gehen alle Anforderungen zuerst an den Director, der sie dann an den richtigen Front-End-Pool weitergibt.
    

