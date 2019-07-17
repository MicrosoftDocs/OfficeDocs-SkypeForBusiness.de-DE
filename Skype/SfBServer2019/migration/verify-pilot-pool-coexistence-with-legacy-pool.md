---
title: Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Prozess zur Überprüfung der Koexistenz von pilotpools mit Legacy Pool
ms.openlocfilehash: b41a1f24786fdf807f9c9c1d5854e397654fdadb
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2019
ms.locfileid: "35758904"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion

 **In diesem Artikel**
  
[Überprüfen, ob Skype for Business Server 2019-Dienste gestartet wurden](#sectionSection0)
  
[Öffnen der Systemsteuerung von Skype for Business Server 2019](#sectionSection1)
  
[Versuchen Sie nicht, die Topologie im Legacy Topology Builder zu öffnen.](#sectionSection2)
  
Nachdem Sie den Pilot Pool bereitgestellt haben, müssen Sie die Koexistenz der beiden Pools überprüfen, indem Sie die Verwaltungstools verwenden, um die Poolinformationen anzuzeigen. Für die Skype for Business Server 2019-Pools und Legacy-Pools müssen Sie die Skype for Business Server 2019 Control Panel-und Topology Builder-Tools verwenden. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Überprüfen, ob Skype for Business Server 2019-Dienste gestartet wurden
<a name="sectionSection0"> </a>

1. Navigieren Sie im Skype for Business Server 2019-Front-End-Server zum Administrator Tools\Services-Applet.
    
2. Überprüfen Sie, ob die folgenden Dienste auf dem Front-End-Server ausgeführt werden:

    - Zentralisierter Protokollierungsdienst-Agent
    - Anwendungsfreigabe
    - Audiotestdienst
    - Audio/Video Konferenzen
    - Parken von Anrufen
    - Konferenzankündigung
    - Konferenzzentrale
    - Front-End
    - Chat Konferenzen
    - Vermittlungs-
    - Replica Replicator-Agent
    - Reaktionsgruppe
    - Webkonferenzen
    - XMPP-Übersetzungs Gateway

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Öffnen der Systemsteuerung von Skype for Business Server 2019
<a name="sectionSection1"> </a>

Öffnen Sie auf dem Front-End-Server in Ihrer Skype for Business Server 2019-Bereitstellung die Systemsteuerung von Skype for Business Server 2019, und wählen Sie den Legacy Pool aus. Wiederholen Sie den Vorgang zum Öffnen des Skype for Business Server 2019-Pools.
  
> [!IMPORTANT]
> Bei Skype for Business Server 2019 müssen Sie Silverlight auf Silverlight Version 5 aktualisieren, bevor Sie die Skype for Business Server-Systemsteuerung verwenden. 
  
Diese Topologie umfasst jetzt Legacy-und Skype for Business Server 2019-Serverrollen. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>Versuchen Sie nicht, die Topologie im Legacy Topology Builder zu öffnen.
<a name="sectionSection2"> </a>

Die Topologie kann nur mit dem Skype for Business Server 2019-Topologie-Generator angezeigt werden. Der Skype for Business Server 2019-Topologie-Generator muss verwendet werden, um Pools für Skype for Business Server 2019 und die Legacy Installation zu erstellen.

  

