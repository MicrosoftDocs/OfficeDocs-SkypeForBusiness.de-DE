---
title: Verwalten von Besprechungseinstellungen
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Hier erfahren Sie, wie Sie die Einstellungen für die von Benutzern in Ihrer Organisation geplanten Teams-Besprechungen verwalten.
ms.openlocfilehash: a0c0e40be84a1b947b5924f97c0c64556a92e249
ms.sourcegitcommit: c477aa1a7da0b6b9bea1f5d10f1395eef418bfdb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711762"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Verwalten von Besprechungseinstellungen in Microsoft Teams

Als Administrator verwenden Sie Teams-Besprechungseinstellungen, um zu steuern, ob anonyme Benutzer an Teams-Besprechungen teilnehmen können und um Besprechungsanfragen anzupassen. Wenn Sie Quality of Service (QoS) aktivieren möchten, können Sie Portbereiche für den Echtzeitdatenverkehr festlegen. Diese Einstellungen gelten für alle Teams-Besprechungen, die Benutzer in Ihrer Organisation planen. Sie verwalten diese Einstellungen über **Besprechungen** > **Besprechungseinstellungen** im Microsoft Teams Admin Center.

## <a name="allow-anonymous-users-to-join-meetings"></a>Anonyme Benutzer dürfen an Besprechungen teilnehmen

Bei der anonymen Teilnahme kann jeder der Besprechung als anonymer Benutzer beitreten, indem er auf den Link in der Besprechungseinladung klickt. Weitere Informationen hierzu finden Sie unter [Teilnehmen an einer Besprechung ohne ein Teams-Konto](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508).

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

Sie müssen ein Teams-Dienstadministrator sein, um diese Änderungen machen zu können. Informationen zum Erhalten von Administratorrollen und -Berechtigungen finden Sie unter [Teams-Administratorrollen verwenden, um Teams zu verwalten](https://docs.microsoft.com/microsoftteams/using-admin-roles).

1. Wechseln Sie zum Admin Center.

2. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Besprechungseinstellungen**.

3. Aktivieren Sie unter **Teilnehmer** die Option **Anonyme Benutzer können an einer Besprechung teilnehmen**.

    ![Screenshot der Teilnehmereinstellungen für Besprechungen im Admin Center](media/meeting-settings-participants.png "Screenshot der Teilnehmereinstellungen für Teams-Besprechungen im Microsoft Teams Admin Center")

> [!CAUTION]
> Wenn Sie nicht möchten, dass anonyme Benutzer an von Benutzern in Ihrer Organisation geplanten Besprechungen teilnehmen, deaktivieren Sie diese Einstellung.

## <a name="allow-anonymous-users-to-interact-with-apps-in-meetings"></a>Zulassen, dass anonyme Benutzer in Besprechungen mit Apps interagieren

Anonyme Benutzer erben jetzt die globale Standardberechtigungsrichtlinie auf Benutzerebene. Dieses Steuerelement ermöglicht dann anonymen Benutzern die Interaktion mit Apps in Teams-Besprechungen, sofern die App von der Berechtigungsrichtlinie auf Benutzerebene aktiviert wurde. Beachten Sie, dass anonyme Benutzer nur mit Apps interagieren können, die bereits in einer Besprechung verfügbar sind, und diese Apps nicht erwerben und/oder verwalten können. 

> [!IMPORTANT]
> Standardmäßig ist die Einstellung, anonymen Benutzern die Interaktion mit Apps in Besprechungen zu erlauben, aktiviert.

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

Sie müssen ein Teams-Dienstadministrator sein, um auf diese Einstellung zugreifen zu können. Informationen zum Erhalten von Administratorrollen und -Berechtigungen finden Sie unter [Teams-Administratorrollen verwenden, um Teams zu verwalten](https://docs.microsoft.com/microsoftteams/using-admin-roles).

1. Wechseln Sie zum Admin Center.

2. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Besprechungseinstellungen**.

3. Die Einstellung für **Anonyme Benutzer können mit Apps in Besprechungen interagieren** kann unter **Teilnehmer** geändert werden.

> [!CAUTION]
> Wenn Sie nicht zulassen möchten, dass anonyme Benutzer mit Apps in von Benutzern in Ihrer Organisation geplanten Besprechungen interagieren, deaktivieren Sie diese Einstellung.

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
4. Klicken Sie auf **Vorschau für Einladung**, um eine Vorschau Ihrer Besprechungseinladung anzuzeigen.
5. Klicken Sie abschließend auf **Speichern**.
6. Warten Sie eine Stunde, bis die Änderungen weitergegeben wurden. Planen Sie dann eine Teams-Besprechung, um zu sehen, wie die Besprechungseinladung aussieht.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Festlegen, wie der Echtzeit-Mediendatenverkehr für Teams-Besprechungen gehandhabt werden soll

<a name="bknetwork"> </a>

Wenn Sie Quality of Service (QoS) zur Priorisierung des Netzwerkverkehrs verwenden, können Sie QoS-Markierungen aktivieren und Portbereiche für jede Art von Mediendatenverkehr festlegen. Das Festlegen von Portbereichen für verschiedene Datenverkehrstypen ist nur ein Schritt bei der Handhabung von Echtzeitmedien. Weitere Details finden Sie unter [Quality of Service (QoS) in Teams](qos-in-teams.md).

> [!IMPORTANT]
> Wenn Sie QoS aktivieren oder Einstellungen im Microsoft Teams Admin Center für den Teams-Dienst ändern, müssen Sie außerdem [übereinstimmende Einstellungen auf alle Benutzergeräte anwenden](QoS-in-Teams-clients.md) und auf alle internen Netzwerkgeräte, um die Änderungen an QoS in Teams vollständig zu implementieren.

 ![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**
1. Wechseln Sie zum Admin Center.
2. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Besprechungseinstellungen**.
3. Gehen Sie unter **Netzwerk** wie folgt vor:

    ![Screenshot der Netzwerkeinstellungen für Besprechungen im Admin Center](media/meeting-settings-network.png "Screenshot der Netzwerkeinstellungen für Teams-Besprechungen im Microsoft Teams Admin Center")

    - Um die Verwendung von DSCP-Markierungen für QoS zu ermöglichen, aktivieren Sie **Markierungen für Quality of Service (QoS) für Mediendatenverkehr in Echtzeit einfügen**. Sie haben nur die Möglichkeit, Markierungen zu verwenden oder nicht; Sie können nicht für jeden Datenverkehrstyp eigene Markierungen festlegen. Weitere Informationen zu DSCP-Markierungen finden Sie unter [Auswählen einer QoS-Implementierungsmethode](QoS-in-Teams.md#select-a-qos-implementation-method).
        > [!NOTE]
        > Das DSCP-Markieren erfolgt normalerweise über Quellports, und der UDP-Verkehr wird standardmäßig an das Transportrelais mit dem Zielport 3478 weitergeleitet. Wenn Ihr Unternehmen das Markieren auf Zielports verlangt, kontaktieren Sie bitte den Support, um die Kommunikation zum Transportrelais mit den UDP-Ports 3479 (Audio), 3480 (Video), und 3481 (Teilen) zu aktivieren.
    - Um Portbereiche festzulegen, wählen Sie neben **Portbereich für jeden Typ von Mediendatenverkehr in Echtzeit auswählen** die Option **Portbereiche festlegen** aus, und geben Sie dann die Start- und Endports für Audio, Video und Bildschirmfreigabe ein. Die Auswahl dieser Option ist erforderlich, um QoS zu implementieren. 
        > [!Note]
        > Wenn **QoS-Markierungen (Quality of Service) für den Echtzeit-Medienverkehr** aktiviert sind, müssen Sie Ihre Porteinstellungen verwalten. Diese werden nicht automatisch angepasst.
        
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

\* Die von Ihnen zugewiesenen Portbereiche dürfen sich nicht überlappen und sollten nebeneinander liegen.

Nachdem QoS eine Weile im Einsatz war, erhalten Sie Nutzungsinformationen über den Bedarf für jede dieser drei Arbeitsauslastungen, und Sie können auswählen, welche Änderungen Sie auf der Grundlage Ihrer spezifischen Anforderungen vornehmen möchten. Das [Anrufqualitäts-Dashboard](turning-on-and-using-call-quality-dashboard.md) wird dabei hilfreich sein.
