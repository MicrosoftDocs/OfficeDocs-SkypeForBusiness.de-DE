---
title: Verwalten von Besprechungseinstellungen
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
description: Hier erfahren Sie, wie Sie die Einstellungen für die von Benutzern in Ihrer Organisation geplanten Teams-Besprechungen verwalten.
ms.openlocfilehash: b231fb1ae564466985195325fb748af5730623a6
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908484"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Verwalten von Besprechungseinstellungen in Microsoft Teams

Als Administrator verwenden Sie Teams-Besprechungseinstellungen, um zu steuern, ob anonyme Benutzer an Teams-Besprechungen teilnehmen können und um Besprechungsanfragen anzupassen. Wenn Sie Quality of Service (QoS) aktivieren möchten, können Sie Portbereiche für den Echtzeitdatenverkehr festlegen. Diese Einstellungen gelten für alle Teams-Besprechungen, die Benutzer in Ihrer Organisation planen. Sie verwalten diese Einstellungen über **Besprechungen** > **Besprechungseinstellungen** im Microsoft Teams Admin Center.

## <a name="allow-anonymous-users-to-join-meetings"></a>Anonyme Benutzer dürfen an Besprechungen teilnehmen

Bei der anonymen Teilnahme kann jeder der Besprechung als anonymer Benutzer beitreten, indem er auf den Link in der Besprechungseinladung klickt. Weitere Informationen hierzu finden Sie unter [Teilnehmen an einer Besprechung ohne ein Teams-Konto](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508).

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

Sie müssen ein Team Dienstadministrator sein, um diese Änderungen vornehmen zu können. Informationen zum Abrufen von Administratorrollen und-Berechtigungen finden Sie unter [Verwenden von Teams-Administratorrollen zum Verwalten von Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) .

1. Wechseln Sie zum Admin Center.

2. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Besprechungseinstellungen**.

3. Aktivieren Sie unter **Teilnehmer** die Option **Anonyme Benutzer können an einer Besprechung teilnehmen**.

    ![Screenshot der Teilnehmereinstellungen für Besprechungen im Admin Center](media/meeting-settings-participants.png "Screenshot der Teilnehmereinstellungen für Teams-Besprechungen im Microsoft Teams Admin Center")

> [!CAUTION]
> Wenn Sie nicht möchten, dass anonyme Benutzer an von Benutzern in Ihrer Organisation geplanten Besprechungen teilnehmen, deaktivieren Sie diese Einstellung.

## <a name="customize-meeting-invitations"></a>Anpassen von Besprechungseinladungen

Sie können Teams-Besprechungseinladungen an die Bedürfnisse Ihrer Organisation anpassen. Sie können das Logo Ihrer Organisation hinzufügen und hilfreiche Informationen wie Links zu Ihrer Supportwebsite und dem rechtlichen Haftungsausschluss sowie eine reine Text-Fußzeile einfügen.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Tipps zum Erstellen eines Logos für Besprechungseinladungen  

1. Erstellen Sie ein Bild, das nicht mehr als 188 Pixel breit und 30 Pixel hoch ist (das ist recht klein).
2. Speichern Sie das Bild im JPG- oder PNG-Format.
3. Speichern Sie das Bild an einem Ort, auf den jeder, der die Einladung erhält, zugreifen kann, z. B. auf einer öffentlichen Website.

    Jetzt können Sie es zu ihren Besprechungseinladungen hinzufügen. Fahren Sie mit den nächsten Schritten fort.

### <a name="customize-your-meeting-invitations"></a>Anpassen Ihrer Besprechungseinladungen

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie zum Admin Center.
2. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Besprechungseinstellungen**.
3. Gehen Sie unter **E-Mail-Einladung** wie folgt vor:

    ![Screenshot der Einstellungen für die Besprechungseinladung, die Sie anpassen können](media/meeting-settings-invitation.png "Screenshot der Einstellungen für die Besprechungseinladung, die Sie für Teams-Besprechungen anpassen können")

    - **Logo-URL** Geben Sie die URL ein, unter der das Logo gespeichert ist.
    - **URL für rechtliche Hinweise** Wenn Ihre Organisation über eine Website mit rechtlichen Hinweisen verfügt, zu der Personen bei rechtliche Bedenken navigieren sollen, geben Sie die URL hier ein.
    - **Hilfe-URL** Wenn Ihre Organisation über eine Supportwebsite verfügt, zu der Personen bei Problemen navigieren sollen, geben Sie die URL hier ein.
    - **Fußzeile** Geben Sie Text ein, der als Fußzeile angezeigt werden soll.
4. Klicken Sie auf **Vorschau für Einladung** , um eine Vorschau Ihrer Besprechungseinladung anzuzeigen.
5. Klicken Sie abschließend auf **Speichern**.
6. Warten Sie eine Stunde, bis die Änderungen weitergegeben wurden. Planen Sie dann eine Teams-Besprechung, um zu sehen, wie die Besprechungseinladung aussieht.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Festlegen, wie der Echtzeit-Mediendatenverkehr für Teams-Besprechungen gehandhabt werden soll

<a name="bknetwork"> </a>

Wenn Sie Quality of Service (QoS) zur Priorisierung des Netzwerkverkehrs verwenden, können Sie QoS-Marker aktivieren und Portbereiche für jeden Mediendaten Verkehr festlegen. Das Festlegen von Portbereichen für verschiedene Datenverkehrstypen ist nur ein Schritt bei der Handhabung von Echtzeitmedien. Weitere Details finden Sie unter [Quality of Service (QoS) in Teams](qos-in-teams.md).

> [!IMPORTANT]
> Wenn Sie QoS aktivieren oder Einstellungen im Microsoft Teams Admin Center für den Teams-Dienst ändern, müssen Sie auch [übereinstimmende Einstellungen auf alle Benutzer Geräte](QoS-in-Teams-clients.md) und alle internen Netzwerkgeräte anwenden, um die Änderungen an QoS in Teams vollständig zu implementieren.

 ![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**
1. Wechseln Sie zum Admin Center.
2. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Besprechungseinstellungen**.
3. Gehen Sie unter **Netzwerk** wie folgt vor:

    ![Screenshot der Netzwerkeinstellungen für Besprechungen im Admin Center](media/meeting-settings-network.png "Screenshot der Netzwerkeinstellungen für Teams-Besprechungen im Microsoft Teams Admin Center")

    - Um die Verwendung von DSCP-Markierungen für QoS zu ermöglichen, aktivieren Sie **Markierungen für Quality of Service (QoS) für Mediendatenverkehr in Echtzeit einfügen**. Sie haben nur die Möglichkeit, Markierungen zu verwenden oder nicht; Sie können nicht für jeden Datenverkehrstyp eigene Markierungen festlegen. Weitere Informationen zu DSCP-Markierungen finden Sie unter [Auswählen einer QoS-Implementierungsmethode](QoS-in-Teams.md#select-a-qos-implementation-method).
        > [!NOTE]
        > DSCP-Tagging erfolgt in der Regel über Quell-Ports, und UDP-Datenverkehr wird standardmäßig an das Transport-Relay mit dem Ziel-Port von 3478 weitergeleitet. Wenn Ihr Unternehmen Tagging für Zielports erfordert, wenden Sie sich bitte an den Support, um die Kommunikation mit dem Transport-Relay mit UDP-Ports 3479 (Audio), 3480 (Video) und 3481 (Freigabe) zu ermöglichen.
    - Um Portbereiche festzulegen, wählen Sie neben **Portbereich für jeden Typ von Mediendatenverkehr in Echtzeit auswählen** die Option **Portbereiche festlegen** aus, und geben Sie dann die Start- und Endports für Audio, Video und Bildschirmfreigabe ein. Die Auswahl dieser Option ist erforderlich, um QoS zu implementieren. 
        > [!Note]
        > Wenn **Quality of Service (QoS)-Marker für echt Zeit Mediendaten Verkehr** aktiviert ist, müssen Sie Ihre Porteinstellungen verwalten. Sie werden nicht automatisch verwaltet.
        
        > [!IMPORTANT]
        > Wenn Sie **Automatisch beliebige verfügbare Ports verwenden** auswählen, werden verfügbare Ports zwischen 1024 und 65535 verwendet. Verwenden Sie diese Option nur, wenn Sie QoS nicht implementieren.
        >
        > Die Auswahl eines zu engen Portbereichs führt zu Anrufabbrüchen und schlechter Anrufqualität. Die nachstehenden Empfehlungen sollten das absolute Minimum darstellen.

Wenn Sie sich nicht sicher sind, welche Portbereiche Sie in Ihrer Umgebung verwenden sollen, sind die folgenden Einstellungen ein guter Ausgangspunkt. Weitere Informationen finden Sie unter [Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md). Dies sind die erforderlichen DSCP-Markierungen und die vorgeschlagenen entsprechenden Medienportbereiche, die sowohl von den Teams als auch von ExpressRoute verwendet werden.

### <a name="port-ranges-and-dscp-markings"></a>Portbereiche und DSCP-Markierungen

Typ des Mediendatenverkehrs| Client-Quellportbereich \* |Protokoll|DSCP-Wert|DSCP-Klasse|
|:---             |:---                         |:---    |:---      |:---      |
|Audio            | 50.000–50.019               |TCP/UDP |46        |Expedited Forwarding (EF)|
|Video            | 50.020–50.039               |TCP/UDP |34        |Assured Forwarding (AF41)|
|Anwendung/Bildschirmfreigabe| 50.040–50.059      |TCP/UDP |18        |Assured Forwarding (AF21)|
| | | | |

\* Die zugewiesenen Portbereiche können sich nicht überlappen und sollten benachbart sein.

Nachdem QoS eine Weile im Einsatz war, erhalten Sie Nutzungsinformationen über den Bedarf für jede dieser drei Arbeitsauslastungen, und Sie können auswählen, welche Änderungen Sie auf der Grundlage Ihrer spezifischen Anforderungen vornehmen möchten. Das [Anrufqualitäts-Dashboard](turning-on-and-using-call-quality-dashboard.md) wird dabei hilfreich sein.
