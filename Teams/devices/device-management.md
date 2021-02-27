---
title: Verwalten Ihrer Geräte in Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Erfahren Sie, wie Sie Geräte verwalten, die mit Teams in Ihrer Organisation verwendet werden.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 41213955c9e57829208ce0ec98448195dc266044
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2021
ms.locfileid: "50350597"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Verwalten Ihrer Geräte in Microsoft Teams

Sie können Geräte, die mit Microsoft Teams in Ihrer Organisation verwendet werden, über das Microsoft Teams Admin Center verwalten. Sie können den Geräteinventar für Ihre Organisation anzeigen und verwalten und Aufgaben wie Aktualisieren, Neustarten und Überwachen der Diagnose für Geräte ausführen. Sie können einem Gerät oder einer Gerätegruppe auch Konfigurationsprofile erstellen und zuweisen.

Zum Verwalten von Geräten, z. B. Gerätekonfiguration ändern, Geräte neu starten, Updates verwalten oder Geräte- und Peripheriegerätezustand anzeigen, müssen Sie eine der folgenden Microsoft 365-Administratorrollen zugewiesen haben:

- Globaler Microsoft 365-Administrator
- Teams Service Admin
- Administrator von Teams-Geräten

Weitere Informationen zu Administratorrollen in Teams finden Sie unter Verwenden von [Teams-Administratorrollen zum Verwalten von Teams.](../using-admin-roles.md)

## <a name="what-devices-can-you-manage"></a>Welche Geräte können Sie verwalten?

Sie können jedes Gerät verwalten, das für Teams zertifiziert und registriert ist. Ein Gerät wird automatisch registriert, wenn sich ein Benutzer zum ersten Mal bei Teams auf dem Gerät registriert. Eine Liste der zertifizierten Geräte, die verwaltet werden können, finden Sie unter:

- [Balken für die Zusammenarbeit](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)
- [Telefonkonferenzen](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Tischtelefone](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Microsoft Teams-Räume](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Anzeigen von Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams-Panels](teams-panels.md)

Um Geräte zu verwalten, wechseln Sie im linken Navigationsbereich des [Microsoft Teams Admin Centers](https://admin.teams.microsoft.com)zu **Geräte,** und wählen Sie dann den Gerätetyp aus. Jeder Gerätetyp verfügt über einen eigenen abschnitt, in dem Sie sie separat verwalten können.

## <a name="manage-teams-rooms-devices"></a>Verwalten von Teams Rooms-Geräten

Sie können das Teams Admin Center verwenden, um Ihre Teams Rooms-Geräte in Ihrer Organisation zu anzeigen und remote zu verwalten. Das Teams Admin Center erleichtert es Ihnen, auf einen Blick zu sehen, welche Geräte fehlerfrei sind und welche Aufmerksamkeit benötigt werden. Außerdem können Sie sich auf bestimmte Geräte konzentrieren, um detaillierte Informationen zu Gerätezustand, Besprechungsleistung, Anrufqualität und Peripheriegeräten zu erhalten. 

Hier sind einige Dinge, die Sie zum Verwalten Ihrer Teams Rooms-Geräte tun können. Teams Rooms-Geräte finden Sie im [Microsoft Teams Admin Center](https://admin.teams.microsoft.com) unter **Geräte**  >  **Teams Rooms**.

Details zum Verwalten Ihrer Teams Rooms-Geräte finden Sie unter [Verwalten von Microsoft Teams Rooms](../rooms/rooms-manage.md).

| Dazu...                          | Gehen Sie dazu vor                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ändern von Einstellungen auf einem oder mehreren Geräten | Wählen Sie ein oder mehrere Geräte > **Einstellungen bearbeiten aus.** Wenn Sie mehrere Geräte auswählen, ersetzen die von Ihnen geänderten Werte die Werte auf allen ausgewählten Geräten.                                                                                                                                                                                                                       |
| Neu starten von Geräten                        | Wählen Sie mindestens ein Gerät aus, > **neu starten.** Wenn Sie ein Gerät neu starten, können Sie  auswählen, ob das Gerät sofort neu gestartet werden soll, oder Einen Neustart planen auswählen, um das Gerät zu einem bestimmten Datum und zu einem bestimmten Zeitpunkt neu zu starten. Datum und Uhrzeit, die Sie auswählen, sind lokal auf dem Gerät, das neu gestartet wird.                                                                                            |
| Anzeigen der Besprechungsaktivität                  | Wählen Sie einen Gerätenamen aus, um Gerätedetails > **Aktivität zu öffnen.** Wenn Sie die Registerkarte **Aktivität** öffnen, werden alle Besprechungen angezeigt, an denen das Gerät teilgenommen hat. In dieser Zusammenfassungsansicht werden die Startzeit der Besprechung, die Anzahl der Teilnehmer, die Dauer und die Anrufqualität insgesamt angezeigt.                                                                                        |
| Anzeigen von Besprechungsdetails                   | Wählen Sie einen Gerätenamen aus, um Gerätedetails > **Aktivitätsdetails >** eine Besprechung auszuwählen. Wenn Sie die Details einer Besprechung öffnen, können Sie alle Teilnehmer an der Besprechung, die Dauer des Anrufs, die Sitzungstypen von Teams und deren individuelle Anrufqualität anzeigen. Wenn Sie technische Informationen zum Anruf eines Teilnehmers sehen möchten, wählen Sie die Startzeit des Teilnehmers aus. |

## <a name="manage-phones-collaboration-bars-teams-displays-and-teams-panels"></a>Verwalten von Telefonen, Zusammenarbeitsleisten, Teams-Displays und Teams-Panels 

Im Teams Admin Center können Sie Telefone, Zusammenarbeitsleisten, Teams-Displays und Teams-Panels anzeigen und verwalten, die in Teams in Ihrer Organisation registriert sind. Zu den Informationen, die Für jedes Gerät angezeigt werden, gehören Gerätename, Hersteller, Modell, Benutzer, Status, Aktion, Zuletzt gesehen und Verlauf. Sie können die Ansicht so anpassen, dass die Informationen angezeigt werden, die Ihren Anforderungen entsprechen.

Smartphones, Zusammenarbeitsleisten, Teams-Displays und Teams-Panels werden automatisch bei Microsoft Intune registriert, wenn Sie sich dafür registriert haben. Nach der Registrierung eines Geräts wird die Gerätekonformität bestätigt und Richtlinien für den bedingten Zugriff auf das Gerät angewendet.

Hier sind einige Beispiele für die Verwaltung von Telefonen, Zusammenarbeitsleisten, Teams-Displays und Teams-Panels in Ihrer Organisation.  

| Dazu...                           | Gehen Sie dazu vor                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ändern von Geräteinformationen               | Wählen Sie ein Gerät > **Bearbeiten aus.** Sie können Details wie Gerätename, Objekttag bearbeiten und Notizen hinzufügen.                                                                                                                                                                                                              |
| Verwalten von Softwareupdates                 | Wählen Sie ein Gerät > **Aktualisieren aus.** Sie können die Liste der für das Gerät verfügbaren Software- und Firmwareupdates anzeigen und die zu installierende Aktualisierung auswählen. Weitere Informationen zum Aktualisieren von Geräten finden Sie unter [Remoteupdate für Teams-Geräte.](remote-update.md)                                                          |
| Upgrade von Teams-Telefonen auf Teams-Displays  | Wählen Sie auf der Seite **IP-Telefone** ein oder mehrere Teams-Telefone aus, > **upgraden möchten.** Diese Option ist nur für Smartphones verfügbar, die ein Upgrade auf Teams-Displays unterstützen. Weitere Informationen finden Sie unter [Aktualisieren von Teams-Telefonen auf Die Anzeigen von Teams.](upgrade-phones-to-displays.md)                                                      |
| Zuweisen oder Ändern von Konfigurationsrichtlinien | Wählen Sie ein oder mehrere Geräte > **Konfiguration zuweisen aus.**                                                                                                                                                                                                                                                       |
| Hinzufügen oder Entfernen von Gerätetags               | Wählen Sie ein oder mehrere Geräte > **Tags verwalten aus.** Weitere Informationen zu Gerätetags finden Sie unter [Verwalten von Teams-Gerätetags.](manage-device-tags.md)                                                                                                                                                                 |
| Neu starten von Geräten                         | Wählen Sie mindestens ein Gerät aus, > **neu starten.**                                                                                                                                                                                                                                                                    |
| Filtern von Geräten mithilfe von Gerätetags        | Wählen Sie das Filtersymbol aus, wählen Sie das **Feld Tag** aus, geben Sie ein Gerätetag an, nach dem gefiltert werden soll, und wählen Sie **Übernehmen aus.** Weitere Informationen zum Filtern von Geräten mithilfe von Gerätetags finden Sie unter Verwenden von Filtern zum Zurückgeben von Geräten [mit einem bestimmten Tag.](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag) |
| Anzeigen des Geräteverlaufs und der Diagnose     | Klicken Sie **unter der** Spalte Verlauf auf **den** Link Ansicht für ein Gerät, um den Aktualisierungsverlauf und diagostische Details anzuzeigen.                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>Verwenden von Konfigurationsprofilen in Teams

Mithilfe von Konfigurationsprofilen können Sie Einstellungen und Features für verschiedene Teams-Geräte in Ihrer Organisation verwalten, einschließlich Zusammenarbeitsleisten, Teams-Displays, Teams-Telefon und Teams-Panels. Sie können Konfigurationsprofile erstellen oder hochladen, um Einstellungen und Features zu enthalten, die Sie aktivieren oder deaktivieren möchten, und dann einem Gerät oder einer Gruppe von Geräten ein Profil zuweisen. 

#### <a name="create-a-configuration-profile"></a>Erstellen eines Konfigurationsprofils

So erstellen Sie ein Konfigurationsprofil für einen Teams-Gerätetyp:

1. Wechseln Sie im linken Navigationsbereich **zu** Geräte, > Sie den Gerätetyp "Teams" > **Konfigurationsprofile aus.** Wählen Sie beispielsweise Geräte Teams **Panels**  >    >  **Konfigurationsprofile aus,** um ein neues Konfigurationsprofil für Teams-Panels zu erstellen.
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie einen Namen für das Profil ein, und fügen Sie optional eine benutzerfreundlichen Beschreibung hinzu.
4. Geben Sie die einstellungen für das Profil an, und klicken Sie dann auf **Speichern.**
   Das neu erstellte Konfigurationsprofil wird in der Liste der Profile angezeigt.

#### <a name="assign-a-configuration-profile"></a>Zuweisen eines Konfigurationsprofils
Nachdem Sie ein Konfigurationsprofil für einen Gerätetyp von Teams erstellt haben, weisen Sie es einem oder mehreren Geräten zu.

1. Wechseln Sie im linken Navigationsbereich **zu** Geräte, > Sie den Gerätetyp "Teams" aus. Wenn Sie z. B. einem Gerät eines Teams-Panels ein Konfigurationsprofil zuweisen möchten, wählen Sie **Geräte**  >  **Teams-Panels aus.**
2. Wählen Sie ein oder mehrere Geräte aus, und klicken Sie dann **auf Konfiguration zuweisen.**  
3. Suchen Sie **im Bereich Konfiguration zuweisen** nach Konfigurationsprofil, das den ausgewählten Geräten zugewiesen werden soll.
4. Klicken Sie auf **Anwenden**.
   Für die Geräte, auf die Sie  die Konfigurationsrichtlinie angewendet  haben, wird in der Spalte Aktion die Spalte **Konfigurationsupdate** und in der Spalte Konfigurationsprofil der Name des Konfigurationsprofils angezeigt.
