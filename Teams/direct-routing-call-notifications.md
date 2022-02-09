---
title: Verwalten von Anrufbenachrichtigungen für Direct Routing
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Benachrichtigung über direkten Routinganruf
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 4af5d65a3d92fbe104b7c998cd8045b6fb52c653
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457185"
---
# <a name="manage-call-notifications"></a>Verwalten von Anrufbenachrichtigungen

In diesem Artikel wird beschrieben, wie Sie Anrufbenachrichtigungen für Ihre Direct Routing-Benutzer verwalten. Sie können Anrufendpunkte sowohl für Teams als auch für einen Drittanbieter konfigurieren: Private Branch Exchange (PBX) oder Session Border Controller (SBC). Diese Einrichtung ist z. B. hilfreich, wenn Sie gleichzeitig einen Anruf an die Mobiltelefone und Tischtelefone eines Benutzers senden möchten.   

Im folgenden Diagramm verfügt Irena über zwei Endpunkte:

- Ein Teams-Endpunkt
- Ein SIP-Telefon, das mit einem Drittanbieter-SBC verbunden ist

Wenn ein Anruf eintrifft, leitet der SBC den Aufruf zwischen Direct Routing und dem Drittanbieter-SBC ab.


![Diagram showing forked Teams endpoints.](media/direct-routing-call-notification-1.png)

Wenn der Anruf am Fork 2 (vom Drittanbieter SBC) angenommen wird Teams wird eine Benachrichtigung "Verpasster Anruf" generiert.  

Sie können die Benachrichtigung "Verpasster Anruf" verhindern, indem Sie den SBC so konfigurieren, dass auf "Fork 1" der Vorgang "Abbrechen" gesendet wird:

GRUND: SIP; cause=200;text"Call completed elsewhere" 

Der Aufruf wird nicht in den Anrufdetaildatensätzen der Teams Telefonsystem als erfolgreicher Aufruf registriert. Der Anruf wird als "Versuch" mit dem endgültigen SIP-Code "487", dem endgültigen Microsoft-Untercode "540200" und dem abschließenden SIP-Codebegriff "Anruf an anderer Stelle abgeschlossen" registriert.  (Wechseln Sie zum Anzeigen der Anrufdetaildatensätze zum Teams Admin Center – > **Analytics and** **ReportsUsage** ->  Reports, und wählen Sie **PSTN-Nutzung aus**.)


Das folgende Diagramm zeigt die SIP-Leiter für "Fork 1", erläutert den Anruffluss und den erwarteten GRUND in der Meldung "Abbrechen". 

![Diagramm zeigt ver forkierte Teams Endpunkte.](media/direct-routing-call-notification-2.png)
