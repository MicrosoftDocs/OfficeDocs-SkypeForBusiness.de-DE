---
title: Verwalten Sie die Besprechungseinstellungen
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.meetingsettings.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Informationen Sie zum Verwalten von Einstellungen für Teams Besprechungen, die Benutzer in Ihrer Organisation planen.
ms.openlocfilehash: 4ded26dae69b5afef1d9fafb4819a73475c44898
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "31959537"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Verwalten von Besprechungseinstellungen in Microsoft Teams

Verwenden Sie als Administrator Teams Besprechungen Einstellungen Kontrolle, ob anonyme Benutzer teilnehmen an Besprechungen Teams, besprechungseinladungen anpassen, und wenn Sie Quality of Service (QoS) aktivieren möchten, legen Sie Portbereiche für den Datenverkehr in Echtzeit können. Diese Einstellungen gelten für alle Besprechungen von Teams, Zeitplan für Benutzer in Ihrer Organisation. Verwalten Sie diese Einstellungen von **Besprechungen** > **besprechungseinstellungen** in der Verwaltungskonsole von Microsoft-Teams.

## <a name="allow-anonymous-users-to-join-meetings"></a>Zulassen, dass anonyme Benutzer an Besprechungen teilnehmen

Mit anonyme Teilnahme kann jeder die Besprechung als anonymer Benutzer teilnehmen, indem Sie auf den Link in der Einladung.

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**

1. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **besprechungseinstellungen**.
2. Aktivieren Sie unter **Teilnehmer** **anonyme Benutzer können an einer Besprechung teilnehmen**.

    ![Meeting-Einstellungen-participants.png] (media/meeting-settings-participants.png "Screenshot der Teilnehmer Einstellungen für Teams Besprechungen in der Verwaltungskonsole von Microsoft-Teams")

Wenn Sie nicht, dass anonyme Benutzern die Teilnahme von Benutzern in Ihrer Organisation geplant möchten, deaktivieren Sie diese Einstellung.

## <a name="customize-meeting-invitations"></a>Anpassen von Besprechungseinladungen

Sie können Teams Besprechungsanfragen erfüllen der Anforderungen Ihrer Organisation anpassen. Sie können Ihrer Organisation Logo und enthalten hilfreiche Informationen, wie Links zu Support-Website und Haftungsausschluss und eine nur-Text-Fußzeile.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Tipps zum Erstellen eines Logos für Besprechungsanfragen  

1. Erstellen Sie ein Bild, das nicht mehr als 188 Pixel breit und 30 Pixel hoch ist (es ist sehr klein).
2. Speichern Sie das Bild wird im JPG-Format.
3. Speichern Sie das Bild in einen zentralen Speicherort, den alle Benutzer in Ihrer Organisation, wie etwa einer Netzwerkfreigabe zugreifen können.

### <a name="customize-your-meeting-invitations"></a>Anpassen der besprechungseinladungen

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**

1. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **besprechungseinstellungen**.
2. Führen Sie unter **E-Mail-Einladung**folgende Schritte aus:

    ![Meeting-Einstellungen-invitation.png] (media/meeting-settings-invitation.png "Screenshot der Besprechung Einladung Einstellungen, die Sie für Teams Besprechungen anpassen können")

    - **Logo-URL** Geben Sie die URL ein, in dem Ihr Logo gespeichert ist.
    - **Rechtliche URL** Wenn Ihre Organisation rechtliche-Website, die Benutzern verfügt So wechseln zur für alle Probleme werden sollen, geben Sie die URL hier.
    - **Hilfe-URL** Wenn Ihre Organisation eine Support-Website, die Benutzern verfügt zu wechseln, wenn sie Probleme ausgeführt werden soll, geben Sie die URL hier.
    - **Fußzeile** Geben Sie Text ein, den Sie als Footer einschließen möchten.
3. Warten Sie eine Stunde oder, damit die Änderungen weitergegeben. Klicken Sie dann Planen einer Besprechung Teams finden in die Einladung zur Besprechung aussieht.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Legen Sie wie Real-Time Media-Datenverkehr für Teams Besprechungen behandelt werden sollen

<a name="bknetwork"> </a>

Wenn Sie den Netzwerkverkehr zu priorisieren Quality of Service [(QoS)](qos-in-teams.md) verwenden, können Sie QoS-Markierung aktivieren, und Sie können Portbereiche für jede Art von Mediendatenverkehr festlegen.

 ![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**

1. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **besprechungseinstellungen**.
2. Führen Sie unter **Netzwerk**folgende Schritte aus:

    ![Meeting-Einstellungen-network.png] (media/meeting-settings-network.png "Screenshot der Netzwerkeinstellungen für Teams Besprechungen in der Verwaltungskonsole von Microsoft-Teams")

    - Damit DSCP Auswahlmöglichkeiten für QoS verwendet werden können, aktivieren Sie **Einfügen Quality of Service (QoS)-Marker für Mediendatenverkehr in Echtzeit**. Sie müssen nur die Option Markierungen oder nicht verwenden; Benutzerdefinierte Markierungen kann nicht für jeden Datenverkehrstyp festgelegt werden. Weitere auf DSCP-Marker finden Sie unter [Wählen Sie eine QoS-Implementierung-Methode](QoS-in-Teams.md#select-a-qos-implementation-method) .
    - Um anzugeben Portbereiche neben, **Wählen Sie einen Portbereich für jede Art von Mediendatenverkehr in Echtzeit**, wählen Sie **Portbereiche angeben**und geben Sie die Start- und Enddatum Ports für Audio, Video und Bildschirmfreigabe. Diese Option ist erforderlich, um QoS zu implementieren.
    > [!IMPORTANT]
    > Wenn Sie wählen Sie **automatisch alle verfügbaren Ports verwenden**, verfügbaren Ports zwischen 1024 und 65535 verwendet werden. Verwenden Sie diese Option nur, wenn keine QoS zu implementieren.
    >
    > Auswählen einer Portbereich an, der nicht breit genug ist, führt zu Verworfene Anrufe und schlechter Anrufqualität. Die folgenden Empfehlungen sollte mindestens bare sein.

 Wenn Sie nicht sicher sind, welche Port für die Verwendung in Ihrer Umgebung liegt, sind die folgenden Einstellungen einen guten Ausgangspunkt. Lesen Sie weitere Informationen finden Sie [Implementieren Quality of Service (QoS) in Microsoft-Teams](QoS-in-Teams.md). Dies sind die erforderlichen DSCP Auswahlmöglichkeiten und die vorgeschlagenen entsprechenden Medien port Bereiche von Teams und ExpressRoute verwendet werden.

_Portbereiche und DSCP Kennzeichnungen_

Media-Datenverkehrstyp| Client-Quellportbereich\* |Protokoll|DSCP-Wert|DSCP-Klasse|
|:---             |:---                         |:---    |:---      |:---      |
|Audio            | 50.000 – 50,019               |TCP/UDP |46        |Expedited Forwarding (EF)|
|Video            | 50,020 – 50,039               |TCP/UDP |34        |Assured Forwarding (AF41)|
|Anwendung/Bildschirmfreigabe| 50,040 – 50,059      |TCP/UDP |18        |Assured Forwarding (AF21)|
| | | | |

\*Die Portbereiche, die Sie zuweisen können nicht überlappen und nebeneinander sein.

Festlegen von Portbereichen für unterschiedliche Datenverkehrstypen ist nur ein Schritt bei der Behandlung von Real Time Media. Weitere Details finden Sie unter [Quality of Service (QoS) in Teams](qos-in-teams.md) . Wenn Sie aktivieren oder ändern, in der Verwaltungskonsole von Microsoft-Teams, müssen Sie die Änderungen an QoS vollständig in Teams implementieren zum [entsprechende Einstellungen für alle Benutzer Geräte anwenden](QoS-in-Teams-clients.md) und internen Netzwerkgeräte.

Nachdem QoS verwendet wurde für eine Weile haben Sie Informationen zur Verwendung auf die Anforderung für jede der folgenden drei Arbeitslasten, und Sie können auswählen, welche Änderungen an Stellen auf Ihre Bedürfnisse Grundlage. [Rufen Sie Qualitätsdashboard](turning-on-and-using-call-quality-dashboard.md) wird mit dem hilfreich sein.
