---
title: Direktes Routing für Telefonsysteme
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
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Benachrichtigung über direkten Routinganruf
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341807"
---
# <a name="manage-call-notifications"></a>Verwalten von Anrufbenachrichtigungen

In diesem Artikel wird beschrieben, wie Sie Anrufbenachrichtigungen für Ihre Benutzer verwalten. Sie können Anrufendpunkte sowohl für Teams als auch für einen Drittanbieter konfigurieren: Private Branch Exchange (PBX) oder Session Border Controller (SBC).  Dies ist beispielsweise hilfreich, wenn Sie gleichzeitig einen Anruf an die Mobiltelefone und Tischtelefone eines Benutzers senden möchten.   

Im folgenden Diagramm verfügt Irena über zwei Endpunkte:

- Ein Teams-Endpunkt
- Ein SIP-Telefon, das mit einem Drittanbieter-SBC verbunden ist

Wenn ein Anruf eintrifft, leitet der SBC den Aufruf Telefonsystem Direct-Routing und dem Drittanbieter-SBC ab.


![Diagram showing forked Teams endpoints](media/direct-routing-call-notification-1.png)

Wenn der Anruf am Fork 2 (vom Drittanbieter SBC) angenommen wird, wird Teams Benachrichtigung "Verpasster Anruf" generiert.  

Sie können die Benachrichtigung "Verpasster Anruf" verhindern, indem Sie den SBC so konfigurieren, dass der Abbruch an "Fork 1" wie folgt gesendet wird:

GRUND: SIP; cause=200;text"Call completed elsewhere" 

Beachten Sie, dass der Aufruf nicht in den Anrufdetaildatensätzen von Microsoft-Telefon System als erfolgreicher Aufruf registriert wird. Der Anruf wird als "Versuch" mit dem endgültigen SIP-Code "487", dem endgültigen Microsoft-Untercode "540200" und dem abschließenden SIP-Codebegriff "Anruf an anderer Stelle abgeschlossen" registriert.  (Zum Anzeigen der Anrufdetailseakte wechseln Sie zum Teams-Verwaltungsportal, zu Analysen und Berichten, Nutzungsberichte, und wählen Sie PSTN-Nutzung aus.)


Das folgende Diagramm zeigt die SIP-Leiter für "Fork 1", erläutert den Anruffluss und in der Meldung "Abbrechen" den erwarteten GRUND. 

![Diagram showing forked Teams endpoints](media/direct-routing-call-notification-2.png)
