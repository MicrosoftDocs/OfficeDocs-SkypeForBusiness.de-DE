---
title: Verwalten Sie die Besprechungseinstellungen
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.meetingsettings.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Hier erfahren Sie, wie Sie Einstellungen für Teambesprechungen verwalten, die Benutzer in Ihrer Organisation planen.
ms.openlocfilehash: 10edd2b0b1b665a126fa7528f4b1e24bf88f4fe5
ms.sourcegitcommit: 3197f3ffca2b2315be9fd0c702ccc8c87383c893
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2019
ms.locfileid: "35062387"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Verwalten von Besprechungseinstellungen in Microsoft Teams

Als Administrator verwenden Sie die Einstellungen für Teams-Besprechungen, um zu steuern, ob anonyme Benutzer an Teams-Besprechungen teilnehmen können, Besprechungseinladungen anpassen und wenn Sie Quality of Service (QoS) aktivieren möchten, indem Sie Portbereiche für den Echtzeitverkehr festlegen. Diese Einstellungen gelten für alle Teams-Besprechungen, die Benutzer in Ihrer Organisation planen. Sie verwalten diese Einstellungen aus **** > den**Besprechungseinstellungen** im Microsoft Teams Admin Center.

## <a name="allow-anonymous-users-to-join-meetings"></a>Zulassen, dass anonyme Benutzer an Besprechungen teilnehmen

Mit Anonymous Join kann jeder Teilnehmer an der Besprechung als anonymer Benutzer teilnehmen, indem er auf den Link in der Besprechungseinladung klickt.

![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center** zeigt

1. Wechseln Sie in der linken Navigationsleiste **** > zu**Besprechungseinstellungen**für Besprechungen.
2. Aktivieren Sie unter **Teilnehmer** **die Option Anonyme Benutzer können an einer Besprechung teilnehmen**.

    Screenshot ![der Teilnehmereinstellungen für Besprechungen im Admin Center] Screenshot (media/meeting-settings-participants.png "der Teilnehmereinstellungen für Teams-Besprechungen im Microsoft Teams Admin Center")

Wenn Sie nicht möchten, dass anonyme Benutzer an Besprechungen teilnehmen, die von Benutzern in Ihrer Organisation geplant wurden, deaktivieren Sie diese Einstellung.

## <a name="customize-meeting-invitations"></a>Anpassen von Besprechungseinladungen

Sie können Besprechungseinladungen für Teams anpassen, um die Anforderungen Ihrer Organisation zu erfüllen. Sie können das Logo Ihrer Organisation hinzufügen und hilfreiche Informationen einfügen, beispielsweise Links zu Ihrer Support Website sowie rechtliche Hinweise und eine nur-Text-Fußzeile.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Tipps zum Erstellen eines Logos für Besprechungseinladungen  

1. Erstellen Sie ein Bild, das nicht mehr als 188 Pixel breit und 30 Pixel hoch ist (es ist ziemlich klein).
2. Speichern Sie das Bild im JPG-oder PNG-Format.
3. Speichern Sie das Bild an einem zentralen Speicherort, auf den jeder in Ihrer Organisation zugreifen kann, beispielsweise eine Netzwerkfreigabe.

    Sie können Sie nun zu ihren Besprechungseinladungen hinzufügen. Lesen Sie die nächsten Schritte.

### <a name="customize-your-meeting-invitations"></a>Anpassen der Besprechungseinladungen

![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center** zeigt

1. Wechseln Sie in der linken Navigationsleiste **** > zu**Besprechungseinstellungen**für Besprechungen.
2. Gehen Sie unter **e-Mail-Einladung**wie folgt vor:

    Screenshot ![der Einstellungen für die Besprechungseinladung, die Sie anpassen können] Screenshot (media/meeting-settings-invitation.png "der Einstellungen für Besprechungseinladungen, die Sie für Teambesprechungen anpassen können")

    - **Logo-URL** Geben Sie die URL ein, in der Ihr Logo gespeichert ist.
    - **Rechtliche URL** Wenn Ihre Organisation über eine rechtliche Website verfügt, zu der Sie Personen für rechtliche Belange wechseln möchten, geben Sie die URL hier ein.
    - **Hilfe-URL** Wenn Ihre Organisation über eine Support Website verfügt, auf die Sie von Personen zugreifen können, wenn Sie Probleme haben, geben Sie die URL hier ein.
    - **Fußzeile** Geben Sie Text ein, den Sie als Fußzeile einfügen möchten.
3. Warten Sie eine Stunde, damit die Änderungen weitergegeben werden. Planen Sie dann eine Teams-Besprechung, um zu sehen, wie die Besprechungseinladung aussieht.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Bestimmen Sie, wie Sie den Echt Zeit Mediendatenverkehr für Teams-Besprechungen behandeln möchten.

<a name="bknetwork"> </a>

Wenn Sie Quality of Service [(QoS)](qos-in-teams.md) zur Priorisierung des Netzwerkverkehrs verwenden, können Sie QoS-Marker aktivieren, und Sie können Portbereiche für jede Art von Mediendatenverkehr festlegen.

 ![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center** zeigt

1. Wechseln Sie in der linken Navigationsleiste **** > zu**Besprechungseinstellungen**für Besprechungen.
2. Führen Sie unter **Netzwerk**die folgenden Aktionen aus:

    Screenshot ![der Netzwerkeinstellungen für Besprechungen im Admin Center] Screenshot (media/meeting-settings-network.png "der Netzwerkeinstellungen für Teams-Besprechungen im Microsoft Teams Admin Center")

    - Damit DSCP-Markierungen für QoS verwendet werden können, aktivieren Sie **Quality of Service (QoS)-Marker für echt Zeit Mediendatenverkehr einfügen**. Sie haben nur die Möglichkeit, Marker zu verwenden oder nicht; Sie können keine benutzerdefinierten Marker für jeden Datenverkehrstyp einrichten. Weitere Informationen zu DSCP-Marken finden Sie unter [Auswählen einer QoS-Implementierungsmethode](QoS-in-Teams.md#select-a-qos-implementation-method) .
    - Wenn Sie Portbereiche angeben möchten, wählen Sie neben **Auswählen eines Portbereichs für jeden Typ von Echt Zeit Mediendatenverkehr**die Option **Portbereiche angeben**aus, und geben Sie dann die Start-und endanschlüsse für Audio-, Video-und Bildschirm Freigaben ein. Die Auswahl dieser Option ist erforderlich, um QoS zu implementieren.
    > [!IMPORTANT]
    > Wenn Sie **alle verfügbaren Anschlüsse automatisch verwenden**auswählen, werden die verfügbaren Anschlüsse zwischen 1024 und 65535 verwendet. Verwenden Sie diese Option nur, wenn Sie QoS nicht implementieren.
    >
    > Wenn Sie einen zu engen Portbereich auswählen, werden Anrufe und schlechte Anrufqualität verloren gehen. Die folgenden Empfehlungen sollten ein absolutes Minimum sein.

 Wenn Sie unsicher sind, welche Portbereiche in Ihrer Umgebung zu verwenden sind, sind die folgenden Einstellungen ein guter Ausgangspunkt. Weitere Informationen finden Sie unter [Implementieren der QoS (Quality of Service) in Microsoft Teams](QoS-in-Teams.md). Hierbei handelt es sich um die erforderlichen DSCP-Markierungen und die vorgeschlagenen entsprechenden Medien Portbereiche, die von Teams und Express Route verwendet werden.

_Port Bereiche und DSCP-Markierungen_

Media Traffic-Typ| Client Quellportbereich\* |Protokoll|DSCP-Wert|DSCP-Klasse|
|:---             |:---                         |:---    |:---      |:---      |
|Audio            | 50000 – 50019               |TCP/UDP |46        |Expedited Forwarding (EF)|
|Video            | 50020 – 50039               |TCP/UDP |34        |Assured Forwarding (AF41)|
|Anwendung/Bildschirmübertragung| 50040 – 50059      |TCP/UDP |18        |Sichere Weiterleitung (AF21)|
| | | | |

\*Die zugewiesenen Portbereiche können sich nicht überlappen und müssen benachbart sein.

Das Festlegen von Portbereichen für verschiedene Datenverkehrstypen ist nur ein Schritt bei der Behandlung von Echt Zeit Medien. Ausführlichere Informationen finden Sie unter [Quality of Service (QoS) in Teams](qos-in-teams.md) . Wenn Sie Einstellungen im Microsoft Teams Admin Center aktivieren oder ändern, müssen Sie [übereinstimmende Einstellungen auf alle Benutzer Geräte](QoS-in-Teams-clients.md) und internen Netzwerkgeräte anwenden, um die Änderungen an QoS in Teams vollständig zu implementieren.

Nachdem QoS eine Zeitlang verwendet wurde, verfügen Sie über Nutzungsinformationen zur Nachfrage für jede dieser drei Arbeitsauslastungen, und Sie können auswählen, welche Änderungen je nach Ihren spezifischen Anforderungen vorgenommen werden sollen. Das Dashboard für die [Anrufqualität](turning-on-and-using-call-quality-dashboard.md) ist dabei hilfreich.
