---
title: Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion
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
description: Prozess zum Überprüfen der Koexistenz von pilotpools mit dem Legacy Pool.
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751657"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion

 **Inhalt dieses Artikels**
  
[Sicherstellen, dass Skype for Business Server 2019-Dienste gestartet wurden](#sectionSection0)
  
[Öffnen der Systemsteuerung von Skype for Business Server 2019](#sectionSection1)
  
[Versuchen Sie nicht, die Topologie im Legacy Topologie-Generator zu öffnen.](#sectionSection2)
  
Nachdem Sie den Pilot-Pool bereitgestellt haben, müssen Sie die Koexistenz der beiden Pools überprüfen, indem Sie die Verwaltungstools verwenden, um die Poolinformationen anzuzeigen. Für Skype for Business Server 2019-Pools und Legacy Pools müssen Sie die Skype for Business Server 2019-Systemsteuerung und die Topologie-Generator-Tools verwenden. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Sicherstellen, dass Skype for Business Server 2019-Dienste gestartet wurden
<a name="sectionSection0"> </a>

1. Navigieren Sie im Skype for Business Server 2019 Front-End-Server zum Applet für administrative verwaltungstools\dienste..
    
2. Überprüfen Sie, ob die folgenden Dienste auf dem Front-End-Server ausgeführt werden:

    - Zentraler Protokollierungsdienst-Agent
    - Anwendungsfreigabe
    - Audio-Test Dienst
    - Audio/Video Konferenzen
    - Funktion zum Parken von Anrufen
    - Konferenzankündigung
    - Konferenzzentrale
    - Front-End
    - Chat Konferenzen
    - Vermittlungs
    - Replikat Replikationsdienst-Agent
    - Reaktionsgruppe
    - Webkonferenz
    - XMPP-Übersetzungs Gateway

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Öffnen der Systemsteuerung von Skype for Business Server 2019
<a name="sectionSection1"> </a>

Öffnen Sie in der Front-End-Server Skype for Business Server 2019-Bereitstellung die Skype for Business Server 2019-Systemsteuerung, und wählen Sie den Pool Legacy aus. Wiederholen Sie den Vorgang, um den Pool Skype for Business Server 2019 zu öffnen.
  
> [!IMPORTANT]
> Auf Skype for Business Server 2019 müssen Sie Silverlight auf Silverlight, Version 5 aktualisieren, bevor Sie die Skype for Business Server-Systemsteuerung verwenden. 
  
Diese Topologie umfasst nun Legacy-und Skype for Business Server 2019-Server Rollen. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>Versuchen Sie nicht, die Topologie im Legacy Topologie-Generator zu öffnen.
<a name="sectionSection2"> </a>

Die Topologie kann nur mit Skype for Business Server 2019-Topologie-Generator angezeigt werden. Der Skype for Business Server 2019-Topologie-Generator muss verwendet werden, um Pools sowohl für Skype for Business Server 2019 als auch für die Legacy Installation zu erstellen.

  

