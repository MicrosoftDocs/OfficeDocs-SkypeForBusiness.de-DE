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
ms.localizationpriority: medium
description: Prozess zum Überprüfen der Koexistenz des Pilotpools mit dem Legacypool.
ms.openlocfilehash: 5d2e6adad0f3297260137df0abcd082b750f0345
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606814"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Überprüfen der Koexistenz des Pilotpools mit dem Legacypool

 **Inhalt dieses Artikels**
  
[Überprüfen, ob Skype for Business Server 2019-Dienste gestartet wurden](#sectionSection0)
  
[Öffnen der Skype for Business Server 2019-Systemsteuerung](#sectionSection1)
  
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
> Auf Skype for Business Server 2019 müssen Sie Silverlight auf Silverlight Version 5 aktualisieren, bevor Sie die Skype for Business Server Systemsteuerung verwenden. 
  
Diese Topologie umfasst jetzt Legacy- und Skype for Business Server 2019-Serverrollen. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>Versuchen Sie nicht, die Topologie im älteren Topologie-Generator zu öffnen.
<a name="sectionSection2"> </a>

Die Topologie kann nur mit Skype for Business Server 2019-Topologie-Generator angezeigt werden. Der Skype for Business Server 2019-Topologie-Generator muss verwendet werden, um Pools für Skype for Business Server 2019 und die Legacyinstallation zu erstellen.

  

