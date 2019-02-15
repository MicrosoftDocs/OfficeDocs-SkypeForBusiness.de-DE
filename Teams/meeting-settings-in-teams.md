---
title: Verwalten von Einstellungen für die Besprechung
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
MS.collection: Teams_ITAdmin_Help
description: Informationen Sie zum Verwalten von Einstellungen für Teams Besprechungen, die Benutzer in Ihrer Organisation planen.
ms.openlocfilehash: 4f192c0f391e99ffea28d296893f3d5087233519
ms.sourcegitcommit: 4e6b39e7421ea6eb03c524bb6b8e597c1966bad1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2019
ms.locfileid: "30056603"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Verwalten von Besprechungseinstellungen in Microsoft Teams

Verwenden Sie als Administrator Teams Besprechungen Einstellungen Kontrolle, ob anonyme Benutzer teilnehmen an Besprechungen Teams, besprechungseinladungen anpassen, und wenn Sie Quality of Service (QoS) aktivieren möchten Festlegen von Ports für den Datenverkehr in Echtzeit können. Diese Einstellungen gelten für alle Besprechungen von Teams, Zeitplan für Benutzer in Ihrer Organisation. Verwalten Sie diese Einstellungen von **Besprechungen** > **besprechungseinstellungen** in der Verwaltungskonsole von Microsoft-Teams. 

## <a name="allow-anonymous-users-to-join-meetings"></a>Zulassen, dass anonyme Benutzer an Besprechungen teilnehmen

Mit anonyme Teilnahme kann jeder die Besprechung als anonymer Benutzer teilnehmen, indem Sie auf den Link in der Einladung. 

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**
1. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **besprechungseinstellungen**. 
2. Aktivieren Sie unter **Teilnehmer** **anonyme Benutzer können an einer Besprechung teilnehmen**. 

    ![Meeting-Einstellungen-participants.png] (media/meeting-settings-participants.png "Screenshot der Teilnehmer Einstellungen für Teams Besprechungen in der Verwaltungskonsole von Microsoft-Teams")

Wenn Sie nicht, dass anonyme Benutzern die Teilnahme von Benutzern in Ihrer Organisation geplant möchten, deaktivieren Sie diese Einstellung. 

## <a name="customize-meeting-invitations"></a>Anpassen von Besprechungseinladungen

Sie können Teams Besprechungsanfragen erfüllen der Anforderungen Ihrer Organisation anpassen. Sie können Ihrer Organisation Logo und enthalten hilfreiche Informationen, wie Links zu Support-Website und Haftungsausschluss und eine nur-Text-Fußzeile. 

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Tipps zum Erstellen eines Logos für Besprechungseinladungen  

1. Erstellen Sie ein Bild, das nicht mehr als 188 Pixel breit und 30 Pixel hoch ist (es ist sehr klein). 
2. Speichern Sie das Bild im JPG-Format. 
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
Wenn Sie den Netzwerkverkehr zu priorisieren Quality of Service (QoS) verwenden, können Sie QoS-Markierung aktivieren, und Sie können Portbereiche für jede Art von Mediendatenverkehr festlegen. 

 ![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**

1. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **besprechungseinstellungen**. 
2. Führen Sie unter **Netzwerk**folgende Schritte aus:

    ![Meeting-Einstellungen-network.png] (media/meeting-settings-network.png "Screenshot der Netzwerkeinstellungen für Teams Besprechungen in der Verwaltungskonsole von Microsoft-Teams")

    - Um QoS-Markierung aktivieren, aktivieren Sie **Einfügen Quality of Service (QoS)-Marker für Mediendatenverkehr in Echtzeit**.
    - Um anzugeben Portbereiche neben, **Wählen Sie einen Portbereich für jede Art von Mediendatenverkehr in Echtzeit**, wählen Sie **Portbereiche angeben**und geben Sie die Start- und Enddatum Ports für Audio, Video und Bildschirmfreigabe. 
    
        Wenn Sie wählen Sie **automatisch alle verfügbaren Ports verwenden**, verfügbaren Ports zwischen 1024 und 65535 verwendet werden. 

 ### <a name="related-topics"></a>Verwandte Themen
- [Quality of Service (QoS) in Teams](qos-in-teams.md)

