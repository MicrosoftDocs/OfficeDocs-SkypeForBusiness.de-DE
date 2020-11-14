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
description: Hier erfahren Sie, wie Sie Geräte verwalten, die mit Teams in Ihrer Organisation verwendet werden.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: d6996b0980ae7305a7517a71645ba823a588e2f8
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49033011"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Verwalten Ihrer Geräte in Microsoft Teams

Sie können Geräte, die mit Microsoft Teams in Ihrer Organisation verwendet werden, über das Microsoft Teams Admin Center verwalten. Sie können die Geräte Inventur für Ihre Organisation anzeigen und verwalten sowie Aufgaben wie aktualisieren, Neustarten und Überwachen der Diagnose für Geräte ausführen. Sie können auch einem Gerät oder einer Gruppe von Geräten Konfigurationsprofile erstellen und zuweisen.

Wenn Sie Geräte wie die Gerätekonfiguration ändern, Geräte neu starten, Updates verwalten oder Geräte-und peripheren Status anzeigen möchten, müssen Sie eine der folgenden Microsoft 365-Administratorrollen zuweisen:

- Microsoft 365-globaler Administrator
- Team Dienstadministrator
- Teams-Geräteadministrator

Weitere Informationen zu Administratorrollen in Teams finden Sie unter [Verwenden von Teams-Administratorrollen zum Verwalten von Teams](../using-admin-roles.md).

## <a name="what-devices-can-you-manage"></a>Welche Geräte können verwaltet werden?

Sie können jedes Gerät verwalten, das für Teams zertifiziert und registriert ist. Ein Gerät wird automatisch registriert, wenn sich ein Benutzer zum ersten Mal bei Teams auf dem Gerät anmeldet. Eine Liste der zertifizierten Geräte, die verwaltet werden können, finden Sie unter:

- [Microsoft Teams-Räume](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Konferenztelefone](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Tischtelefone](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams wird angezeigt](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Zusammenarbeits leisten](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)

Zum Verwalten von Geräten wechseln Sie in der linken Navigationsleiste des [Microsoft Teams Admin Center](https://admin.teams.microsoft.com)zu **Geräte** , und wählen Sie dann den Gerätetyp aus. Jeder Gerätetyp verfügt über einen eigenen Abschnitt, in dem Sie diese separat verwalten können.

## <a name="manage-teams-rooms-devices"></a>Verwalten von Teams rooms-Geräten

Sie können das Team Admin Center verwenden, um Ihre Teams rooms-Geräte in Ihrer Organisation anzuzeigen und Remote zu verwalten. Das Team Admin Center macht es einfach, auf einen Blick zu sehen, welche Geräte gesund sind und welche Aufmerksamkeit erfordern, und ermöglicht Ihnen, sich auf bestimmte Geräte zu konzentrieren, um detaillierte Informationen zu Gerätestatus, Besprechungs Leistung, Anrufqualität und Peripheriegeräten anzuzeigen. 

Hier sind einige Möglichkeiten, wie Sie Ihre Teams rooms-Geräte verwalten können. Teams rooms-Geräte finden Sie im [Microsoft Teams Admin Center](https://admin.teams.microsoft.com) unter **Geräte**  >  **Teams-Chatrooms**.

Ausführliche Informationen zum Verwalten von Geräten für teamsräume finden Sie unter [Verwalten von Microsoft Teams-Räumen](../rooms/rooms-manage.md).

| Zu diesem Zweck... | Vorgehensweise|
|---------------|--------|
| Ändern von Einstellungen auf einem oder mehreren Geräten | Wählen Sie ein oder mehrere Geräte > **Bearbeitungseinstellungen** aus. Wenn Sie mehrere Geräte auswählen, werden die Werte auf allen ausgewählten Geräten durch die Werte ersetzt, die Sie ändern. |
| Geräte neu starten | Wählen Sie ein oder mehrere Geräte > **Neustart** aus. Wenn Sie ein Gerät neu starten, können Sie auswählen, ob Sie das Gerät sofort neu starten oder " **Neustart planen** " auswählen, um das Gerät zu einem bestimmten Zeitpunkt neu zu starten. Das von Ihnen ausgewählte Datum und die Uhrzeit sind lokal für das Gerät, das neu gestartet wird.|
| Anzeigen von Besprechungs Aktivitäten | Wählen Sie einen Gerätenamen aus, um Gerätedetails > **Aktivität** zu öffnen. Wenn Sie die Registerkarte **Aktivität** öffnen, werden alle Besprechungen angezeigt, an denen das Gerät teilgenommen hat. In dieser Zusammenfassungsansicht werden die Startzeit der Besprechung, die Anzahl der Teilnehmer, die Dauer und die Gesamtqualität des Anrufs angezeigt.|
| Anzeigen von Besprechungsdetails |  Wählen Sie einen Gerätenamen aus, um Gerätedetails > **Aktivität** zu öffnen > eine Besprechung auszuwählen. Wenn Sie die Details einer Besprechung öffnen, können Sie alle Teilnehmer der Besprechung, die Dauer des Anrufs, die Sitzungstypen der Teams und die individuelle Anrufqualität sehen. Wenn Sie technische Informationen zum Anruf eines Teilnehmers anzeigen möchten, wählen Sie die Startzeit des Teilnehmers aus.|

## <a name="manage-phones-collaboration-bars-and-teams-displays"></a>Verwalten von Telefonen, Zusammenarbeits leisten und Teams wird angezeigt 

Im Team Admin Center können Sie Telefone, Zusammenarbeits leisten und Teams anzeigen, die für Teams in Ihrer Organisation registriert sind. Zu den Informationen, die Sie für jedes Gerät sehen, gehören Gerätename, Hersteller, Modell, Benutzer, Status, Aktion, zuletzt gesehen und Verlauf. Sie können die Ansicht anpassen, um die Informationen anzuzeigen, die Ihren Anforderungen entsprechen.

Telefone, Zusammenarbeits leisten und Teams werden automatisch in Microsoft InTune registriert, wenn Sie sich dafür registriert haben. Nachdem ein Gerät registriert wurde, wird die Gerätekompatibilität bestätigt, und auf das Gerät werden Richtlinien für den bedingten Zugriff angewendet.

Nachfolgend finden Sie einige Beispiele, wie Sie Telefone, Zusammenarbeits leisten und Teams in Ihrer Organisation anzeigen können.  

|Zu diesem Zweck...  |Vorgehensweise |
|---------|---------|
| Ändern von Geräteinformationen               | Wählen Sie ein Gerät > **Bearbeiten** aus. Sie können Details wie Gerätename, Inventar Kategorie und Notizen bearbeiten.     |
| Verwalten von Softwareupdates                 | Wählen Sie ein Gerät > **Update** aus. Sie können die Liste der für das Gerät verfügbaren Software-und Firmware-Updates anzeigen und die zu installierenden Updates auswählen. Weitere Informationen zum Aktualisieren von Geräten finden Sie unter [Aktualisieren von Teams-Geräten per Remotezugriff](remote-update.md) .   |
| Aktualisieren von Teams-Smartphones auf Teams-Displays                | Wählen Sie auf der Seite **IP-Telefone** ein oder mehrere Teams-Telefone > **Upgrade** aus. Diese Option steht nur für Telefone zur Verfügung, die ein Upgrade auf Teams-Displays unterstützen. Weitere Informationen finden Sie unter [Upgrade von Teams-Smartphones auf Teams-Displays](upgrade-phones-to-displays.md).   |
| Zuweisen oder Ändern von Konfigurationsrichtlinien | Wählen Sie ein oder mehrere Geräte aus, > die **Konfiguration zuzuweisen**.                                                                                                                                                                                                                   |
| Hinzufügen oder Entfernen von Gerätekategorien               | Wählen Sie ein oder mehrere Geräte > **Kategorien verwalten** aus. Weitere Informationen zu Geräte Tags finden Sie unter [Verwalten von Teams-Gerätekategorien](manage-device-tags.md).                                                                                                      |
| Geräte neu starten                         | Wählen Sie ein oder mehrere Geräte > **Neustart** aus.                                                                                                                                                                                                                                |
| Filtern von Geräten mithilfe von Gerätekategorien        | Wählen Sie das Filtersymbol aus, wählen Sie das **Tag** -Feld aus, geben Sie ein Device-Tag zum Filtern an, und wählen Sie über **nehmen** aus. Weitere Informationen zum Filtern von Geräten mithilfe von Geräte Tags finden Sie unter [Verwenden von Filtern zum Zurückgeben von Geräten mit einem bestimmten Tag](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag).|
| Geräte Verlauf anzeigen                     | Wählen Sie ein Gerät > **Verlauf** aus. Sie können den Updateverlauf für das Gerät anzeigen.                                                                                                                                                                                |
| Anzeigen von Diagnosen                        | Wählen Sie ein Gerät > **Diagnose** aus.                                                                                                                                                                                                                            |
### <a name="use-configuration-profiles-in-teams"></a>Verwenden von Konfigurationsprofilen in Teams

Verwenden Sie Konfigurationsprofile zum Verwalten von Einstellungen und Features für Teams-Telefone und Zusammenarbeits leisten in Ihrer Organisation. Sie können Konfigurationsprofile erstellen oder hochladen, um Einstellungen und Features einzubeziehen, die Sie aktivieren oder deaktivieren möchten, und dann einem Gerät oder einer Gruppe von Geräten ein Profil zuweisen. 

#### <a name="create-a-configuration-profile"></a>Erstellen eines Konfigurationsprofils

1. Navigieren Sie in der linken Navigationsleiste zu **Devices** -  >  **Konfigurationsprofilen**.
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie einen Namen für das Profil ein, und fügen Sie bei Bedarf eine Beschreibung hinzu.
4. Geben Sie die gewünschten Einstellungen für das Profil ein, und klicken Sie auf **Speichern**.

#### <a name="assign-a-configuration-profile"></a>Zuweisen eines Konfigurationsprofils

1. Navigieren Sie in der linken Navigationsleiste zu **Devices** -  >  **Konfigurationsprofilen**.
2. Wählen Sie das **Konfigurationsprofil** aus, das Sie zuweisen möchten, und klicken Sie dann auf **auf Gerät zuweisen**.  
3. Suchen Sie im Bereich **Geräte zu einem Konfigurationsprofil zuweisen** nach den Geräten, die Sie zuweisen möchten, und wählen Sie Sie aus.
4. Klicken Sie auf **Speichern**.

