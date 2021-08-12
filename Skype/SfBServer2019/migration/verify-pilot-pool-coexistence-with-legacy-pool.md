---
title: Überprüfen der Koexistenz des Pilotpools mit dem Legacypool
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Prozess zum Überprüfen der Koexistenz des Pilotpools mit dem Legacypool.
ms.openlocfilehash: f9a3fa8a9716d880b8fa2381fd5cafe88509504c2c142ebd5da5c5ab43667cf1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341121"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Überprüfen der Koexistenz des Pilotpools mit dem Legacypool

 **Inhalt dieses Artikels**
  
[Überprüfen, ob Skype for Business Server 2019-Dienste gestartet wurden](#sectionSection0)
  
[Öffnen der systemsteuerung Skype for Business Server 2019](#sectionSection1)
  
[Versuchen Sie nicht, die Topologie im älteren Topologie-Generator zu öffnen.](#sectionSection2)
  
Nach der Bereitstellung des Pilotpools müssen Sie die Koexistenz der beiden Pools mithilfe der Verwaltungstools überprüfen, um die Poolinformationen anzuzeigen. Für die Skype for Business Server 2019-Pools und Legacypools müssen Sie die Tools Skype for Business Server 2019-Systemsteuerung und Topologie-Generator verwenden. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Überprüfen, ob Skype for Business Server 2019-Dienste gestartet wurden
<a name="sectionSection0"> </a>

1. Navigieren Sie vom Skype for Business Server 2019 Front-End-Server zum Applet "Verwaltungstools\Dienste".
    
2. Überprüfen Sie, ob die folgenden Dienste auf dem Front-End-Server ausgeführt werden:

    - Zentraler Protokollierungsdienst-Agent
    - Anwendungsfreigabe
    - Audiotestdienst
    - Audio-/Videokonferenzen
    - Parken von Anrufen
    - Konferenzankündigung
    - Konferenzzentrale
    - Front-End
    - Chatkonferenzen
    - Mediation
    - Replikatreplikationsdienst-Agent
    - Reaktionsgruppe
    - Webkonferenz
    - XMPP-Übersetzungsgateway

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Öffnen der Skype for Business Server 2019-Systemsteuerung
<a name="sectionSection1"> </a>

Öffnen Sie auf dem Front-End-Server in Ihrer Skype for Business Server 2019-Bereitstellung die Systemsteuerung Skype for Business Server 2019, und wählen Sie den Legacypool aus. Wiederholen Sie die Prozedur, um den Skype for Business Server 2019-Pool zu öffnen.
  
> [!IMPORTANT]
> On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 to using the Skype for Business Server Control Panel. 
  
Diese Topologie umfasst jetzt Legacy- und Skype for Business Server 2019-Serverrollen. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>Versuchen Sie nicht, die Topologie im älteren Topologie-Generator zu öffnen.
<a name="sectionSection2"> </a>

Die Topologie kann nur mit Skype for Business Server Topologie-Generator 2019 angezeigt werden. Der Skype for Business Server 2019-Topologie-Generator muss verwendet werden, um Pools für Skype for Business Server 2019 und die Legacyinstallation zu erstellen.

  

