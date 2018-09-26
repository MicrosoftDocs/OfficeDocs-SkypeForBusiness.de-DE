---
title: Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Prozess zum Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion.
ms.openlocfilehash: 717726acd3654abb2296d622afc5a4d45009430e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028691"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion

 **In diesem Artikel**
  
[Stellen Sie sicher, dass Skype für Business Server 2019-Dienste gestartet wurden](#sectionSection0)
  
[Öffnen Sie die Skype für Business Server 2019-Systemsteuerung](#sectionSection1)
  
[Versuchen Sie nicht, öffnen Sie die Topologie in der Vorversion Topologie-Generator](#sectionSection2)
  
Nachdem Sie den pilotpool bereitgestellt haben, müssen Sie die Koexistenz der beiden Pools zu überprüfen, indem Sie mithilfe der Verwaltungstools die Poolinformationen anzeigen. Für die Skype für Business Server 2019 Pools und legacypools müssen Sie die Skype für Business Server 2019-Systemsteuerung und Topologie-Generator-Tools verwenden. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Stellen Sie sicher, dass Skype für Business Server 2019-Dienste gestartet wurden
<a name="sectionSection0"> </a>

1. Navigieren Sie aus der Skype für Business Server 2019 Front-End-Server zum Applet verwaltungstools\dienste.
    
2. Stellen Sie sicher, dass die folgenden Dienste auf dem Front-End-Server ausgeführt werden:

    - Zentralisierte Protokollierungs-Dienst-Agenten
    - Anwendungsfreigabe
    - Dienst zum Testen der Audioqualität
    - A/v-Konferenzen
    - Parken von Anrufen
    - Konferenzankündigung
    - Konferenzzentrale
    - Front-End-
    - Instant Messaging-Konferenzen
    - Vermittlungs-
    - Replikat Replikations-Agent
    - Reaktionsgruppe
    - Webkonferenzen
    - Übersetzen von XMPP-Gateway

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Öffnen Sie die Skype für Business Server 2019-Systemsteuerung
<a name="sectionSection1"> </a>

Öffnen Sie von den Front-End-Server in Ihrer Skype für Business Server 2019 Bereitstellung der Skype Business Server 2019-Systemsteuerung zu, und wählen Sie Pool den Vorgängerversion. Wiederholen Sie das Schritte aus, um die Skype für Business Server 2019 Pool zu öffnen.
  
> [!IMPORTANT]
> In Skype für Business Server 2019 müssen Sie Silverlight auf Silverlight, Version 5, bevor Sie die Skype Business Server-Systemsteuerung verwenden upgraden. 
  
Diese Topologie enthält nun Legacy und Skype für Business Server 2019 Serverrollen. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>Versuchen Sie nicht, öffnen Sie die Topologie in der Vorversion Topologie-Generator
<a name="sectionSection2"> </a>

Wenn Sie versuchen, die Topologie mithilfe des legacy-Topologie-Generators öffnen, treten Sie die unten angegebene Fehlermeldung. Die Topologie kann nur mithilfe der Skype für Business Server 2019 Topologie-Generator angezeigt werden. Zum Erstellen von Pools für Skype für Business Server 2019 und der Vorversion installieren, muss der Skype für Business Server 2019 Topologie-Generator verwendet werden.

  

