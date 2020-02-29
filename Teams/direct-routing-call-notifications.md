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
description: Benachrichtigung über direkten Routing Anruf
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

In diesem Artikel wird beschrieben, wie Sie Anrufbenachrichtigungen für Ihre Benutzer verwalten. Sie können Anruf Endpunkte sowohl für Teams als auch für eine Drittpartei (Private Branch Exchange, PBX) oder einen Session Border Controller (SBC) konfigurieren.  Dies ist beispielsweise hilfreich, wenn Sie einen Anruf an das Mobiltelefon und die Tischtelefone eines Benutzers gleichzeitig senden möchten.   

Im folgenden Diagramm hat der Benutzer Irena zwei Endpunkte:

- Ein Team Endpunkt
- Ein SIP-Telefon, das mit einem Drittanbieter-SBC verbunden ist

Wenn ein Anruf eingeht, verzweigt der SBC den Anruf zwischen dem direkten Routing des Telefonsystems und dem Drittanbieter-SBC.


![Diagramm mit gegabelten Teams-Endpunkten](media/direct-routing-call-notification-1.png)

Wenn der Anruf auf Fork 2 (vom Drittanbieter-SBC) akzeptiert wird, generiert Teams eine Benachrichtigung über verpasste Anrufe.  

Sie können die Benachrichtigung "verpasste Anrufe" verhindern, indem Sie den SBC so konfigurieren, dass ein Cancel auf Gabel 1 wie folgt gesendet wird:

Grund: SIP; Ursache = 200; Text "Anruf an anderer Stelle abgeschlossen" 

Beachten Sie, dass der Anruf nicht in den Anruf Detaildatensätzen von Microsoft Phone System als erfolgreicher Anruf registriert wird. Der Anruf wird als "Versuch" mit dem endgültigen SIP-Code "487", dem endgültigen Microsoft-Subcode "540200" und dem letzten SIP-Codesatz "Anruf an anderer Stelle abgeschlossen" registriert.  (Wenn Sie die Anruf Detaildatensätze anzeigen möchten, wechseln Sie zum Teamadministrator-Portal, Analyse-und Berichtsfunktionen, Verwendungsberichte, und wählen Sie PSTN-Nutzung aus.)


Das folgende Diagramm zeigt die SIP-Leiter für Fork 1, erläutert den Anruffluss und den erwarteten Grund in der Abbruch Nachricht. 

![Diagramm mit gegabelten Teams-Endpunkten](media/direct-routing-call-notification-2.png)
