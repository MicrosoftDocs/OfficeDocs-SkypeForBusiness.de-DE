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
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Benachrichtigung über Direct Routing-Anrufe
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 4aa8e6a6f75141f7858e2342b65fb59d09326c33
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268430"
---
# <a name="manage-call-notifications"></a>Verwalten von Anrufbenachrichtigungen

In diesem Artikel wird beschrieben, wie Sie Anrufbenachrichtigungen für Ihre Direct Routing-Benutzer verwalten. Sie können Anrufendpunkte sowohl für Teams als auch für einen Private Branch Exchange (PBX) oder Session Border Controller (SBC) eines Drittanbieters konfigurieren. Diese Einrichtung ist z. B. hilfreich, wenn Sie gleichzeitig einen Anruf an die Mobiltelefone und Telefone eines Benutzers senden möchten.   

Im folgenden Diagramm verfügt Der Benutzer Irena über zwei Endpunkte:

- Ein Teams-Endpunkt
- Ein SIP-Telefon, das mit einem SBC eines Drittanbieters verbunden ist

Wenn ein Anruf eingeht, gibt der SBC den Anruf zwischen Direct Routing und dem SBC eines Drittanbieters ab.


![Diagramm mit verzweigten Teams-Endpunkten.](media/direct-routing-call-notification-1.png)

Wenn der Anruf am Fork 2 (vom Drittanbieter-SBC) angenommen wird, generiert Teams eine Benachrichtigung "Verpasster Anruf".  

Sie können die Benachrichtigung "Verpasster Anruf" verhindern, indem Sie den SBC so konfigurieren, dass ein Cancel on Fork 1 wie folgt gesendet wird:

GRUND: SIP; cause=200;text"Anruf an anderer Stelle abgeschlossen" 

Der Anruf wird nicht als erfolgreicher Anruf in den Anrufdetaildatensätzen des Teams-Telefonsystems registriert. Der Anruf wird als "Attempt" mit dem endgültigen SIP-Code "487", der endgültigen Microsoft-Untercodierung "540200" und dem abschließenden SIP-Codeausdruck "Call completed elsewhere" registriert.  (Um die Anrufdetaildatensätze anzuzeigen, wechseln Sie zum Teams Admin Center > **Analyse- und****Berichtsnutzungsberichte** -> , und wählen Sie **PSTN-Nutzung** aus.)


Das folgende Diagramm veranschaulicht die SIP-Leiter für Verzweigung 1, erläutert den Anruffluss und den erwarteten GRUND in der Nachricht "Abbrechen". 

![Diagramm zeigt verzweigte Teams-Endpunkte.](media/direct-routing-call-notification-2.png)
