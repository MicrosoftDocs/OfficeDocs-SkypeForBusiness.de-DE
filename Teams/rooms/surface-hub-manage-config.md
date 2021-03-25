---
title: Verwalten der Microsoft Teams-Konfiguration auf Surface Hub
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Verwalten von Microsoft Teams-Einstellungen auf Surface Hub mit Microsoft Intune und Windows Configuration Designer
ms.openlocfilehash: 9c16fa4875febd3c9e0a8457626db5e09bf90545
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117383"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Verwalten von Microsoft Teams-Einstellungen auf Surface Hub

Sie können Microsoft Teams-Einstellungen auf einem Surface Hub mithilfe von Windows Configuration Designer oder Microsoft Intune in Microsoft Endpoint Manager verwalten. Die Kenntnisse von Windows Configuration Designer oder Microsoft Intune sind erforderlich, um Änderungen an den Teams-Einstellungen vorzunehmen. Weitere Informationen zu diesen Optionen finden Sie in den folgenden Artikeln:

- [Erstellen eines Bereitstellungspakets für Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [Was ist Die Geräteverwaltung von Microsoft Intune?](/mem/intune/remote-actions/device-management)

Windows-Konfigurations-Designer ist eine gute Option, wenn Sie nur über ein paar Surface Hub-Geräte verfügen und problemlos darauf zugreifen können. Wenn Sie über viele Surface Hubs verfügen oder sich an Remotestandorten befinden, verwenden Sie Microsoft Intune in Microsoft Endpoint Manager, wenn es in Ihrer Organisation bereitgestellt wird. Unabhängig von der von Ihnen verwendeten Methode müssen Sie eine XML-Konfigurationsdatei erstellen, um Änderungen an den Teams-Einstellungen auf Surface Hub vorzunehmen.

## <a name="teams-configuration-file-syntax"></a>Syntax der #A0

Die Konfiguration von Teams auf einem Surface Hub wird mithilfe einer XML-Datei definiert. Die XML-Datei enthält alle Einstellungen, die zum Steuern der Funktionsweise von Teams verwendet werden können. Sowohl windows configuration designer als auch Microsoft Intune verwenden dieselbe XML-Syntax. Hier sehen Sie ein Beispiel für die XML-Datei der Teams-Konfiguration:

```xml
<SurfaceHubSettings>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
    <CoordinatedMeetings enabled="true"> 
        <TrustedAccounts>room@contoso.com</TrustedAccounts>
        <Settings> 
            <Audio default="false" enabled="false" />
            <Video default="false" enabled="true" /> 
        </Settings> 
    </CoordinatedMeetings>
</SurfaceHubSettings>
```

In der folgenden Tabelle sind alle Konfigurationseinstellungen beschrieben, die in der Konfigurationsdatei verfügbar sind:

| Übergeordnetes Element                  | Element                                   | Attribut | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Keine                    | `<SurfaceHubSettings>`                    |           | Enthält alle Konfigurationselemente für die Teams-Konfiguration auf einem Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Bestimmt, ob Surface Hub anklagt, dass es für Bluetooth verfügbar ist.<br>Akzeptierte Werte: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Bestimmt, ob Teams näherungsbasierte Besprechungen automatisch akzeptiert.<br>Akzeptierte Werte: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Enthält alle Konfigurationselemente für koordinierte Besprechungen.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Bestimmt, ob Teams für die Teilnahme an koordinierten Besprechungen mit anderen Geräten konfiguriert ist.<br>Akzeptierte Werte: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Dies ist eine durch Kommas getrennte Liste von UPNs für jedes Teams Room-Gerät oder Surface Hub, von dem das Gerät Besprechungsbesprechungsanfragen annehmen oder an die Besprechungsbesprechungsanfragen gesendet werden sollen.<br>Akzeptierte Werte: Zeichenfolge                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Enthält Konfigurations-Audio- und Videokonfigurationselemente für koordinierte Besprechungen                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Steuert die Audiokonfiguration für Teams auf einem Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Bestimmt, auf welchem Gerät das Mikrofon aktiv ist, wenn eine Besprechung beginnt. Nur auf einem Gerät (in der Regel ein Team Rooms-Gerät) kann dieses Feld auf festgelegt sein, während für die restlichen Geräte dieses Feld auf festgelegt sein muss, um Audio echo und Feedback `true` `false` zu vermeiden.<br>Akzeptierte Werte: `true` , `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Bestimmt, ob Teilnehmer an einer Besprechung das Mikrofon ein- oder ausschalten können. Auf Geräten, auf denen **audio default** festgelegt ist, sollte diese Einstellung auf festgelegt sein, damit die Teilnehmer nicht versehentlich ein Mikrofon aktivieren und audio echo oder Feedback `false` verursachen `false` können.<p>Wenn **audio default** auf festgelegt ist, wird diese Einstellung ignoriert, und die Teilnehmer können das Mikrofon stummschalten oder die `true` Stummschaltung aufhören.<br>Akzeptierte Werte: `true` , `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Steuert die Videokonfiguration für Teams auf einem Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Bestimmt, auf welchem Gerät die Kamera aktiv ist, wenn eine Besprechung beginnt. Zur bestmöglichen Benutzererfahrung empfiehlt es sich, nur auf das Gerät Teams Rooms zu setzen, während `true` alle anderen Geräte auf festgelegt `false` sind.<br>Akzeptierte Werte: `true` , `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Bestimmt, ob Teilnehmer an einer Besprechung die Kamera ein- oder ausschalten können. Sie können dies auf allen anderen Geräten der Ereignisteilnehmer festlegen, die unterschiedliche Videoperspektiven teilen möchten (z. B. wenn ein Teilnehmer das `true` Surface Hub-Whiteboard verwendet). Wenn Sie nicht möchten, dass Teilnehmer eine Kamera auf einem Gerät ein- oder ausschalten, legen Sie dies auf `false` fest.<p> Wenn **video default** auf festgelegt ist, wird diese Einstellung ignoriert, und die Teilnehmer können die Kamera `true` ein- oder ausschalten.<br>Akzeptierte Werte: `true` , `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Anwenden von Teams-Einstellungen auf Surface Hub

Anwenden oder Aktualisieren von Teams-Konfigurationseinstellungen auf Surface Hub mithilfe von Windows Configuration Designer oder Microsoft Intune in Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>Verwenden von Windows Configuration Designer

Sie können windows configuration designer verwenden, um ein Bereitstellungspaket zu erstellen, mit dem Sie Teams-Einstellungen auf Ihre Surface Hubs anwenden können. Sie fügen die oben erstellte XML-Datei in den Windows-Konfigurations-Designer ein, um das Bereitstellungspaket zu erstellen.

> [!IMPORTANT]
> Wenn Sie die Teams-Konfiguration bereits mithilfe eines Bereitstellungspakets auf Ihren Surface Hub angewendet haben und es ändern möchten, müssen Sie zuerst das vorhandene Bereitstellungspaket entfernen. Weitere Informationen finden Sie unter Entfernen eines von Windows Configuration Designer erstellten [Bereitstellungspakets.](#remove-a-provisioning-package-created-by-windows-configuration-designer)

Gehen Sie wie folgt vor, um das Bereitstellungspaket in Windows Configuration Designer zu erstellen:

1. Installieren von Windows Configuration Designer aus dem Windows Store auf Ihrem lokalen Computer und Öffnen
2. Wählen **Sie Surface Hub-Geräte bereitstellen** und dann zum **erweiterten Editor wechseln aus.**
3. Erweitern Sie im nächsten Bildschirm **WindowsTeamSettings**  >  **Teams,** und wählen Sie **Konfigurationen aus.**
4. Fügen Sie im Feld neben **Konfigurationen** im mittleren Bereich die einzelne XML-Zeile ein, die Sie oben erstellt haben.
5. Wählen **Sie**  >  **Bereitstellungspaket exportieren aus.**
6. Geben Sie unter Name einen Namen für das Bereitstellungspaket **an,** und wählen Sie **Weiter**  >  **weiter aus.**
7. Geben Sie einen Speicherort zum Speichern des Bereitstellungspakets an, und wählen Sie Weiter **aus.**
8. Wählen **Sie Build** aus, um das Bereitstellungspaket zu erstellen, und dann Fertig **stellen**

Nachdem Sie das Bereitstellungspaket erstellt haben, gehen Sie zum Anwenden des Bereitstellungspakets auf Ihren Surface Hub wie folgt vor:

1. Speichern des oben erstellten Bereitstellungspakets auf einem USB-Laufwerk
2. Einfügen des USB-Laufwerks in Ihren Surface Hub
3. Öffnen Sie auf Ihrem Surface Hub das Startmenü, wählen Sie **Alle Apps** und dann Einstellungen **aus.**
4. Geben Sie Ihren Administratornamen und ihr Kennwort ein, und wählen Sie dann **Ja aus.**
5. Wechseln Sie **zu Surface Hub,** **Geräteverwaltung,** Hinzufügen oder Entfernen eines **Bereitstellungspakets,** und fügen Sie **dann ein Paket hinzu.**
6. Wählen **Sie unter Paket auswählen** die Option **Neben** Dem Bereitstellungspaket hinzufügen aus, und starten Sie dann Ihren Surface Hub neu.

### <a name="use-microsoft-intune"></a>Verwenden von Microsoft Intune

Wenn Ihre Surface Hubs mit Microsoft Intune in Microsoft Endpoint Management verwaltet werden, können Sie damit Teams-Einstellungen auf Ihre Surface Hubs anwenden. Sie erstellen ein neues Konfigurationsprofil und fügen dann die oben erstellte XML-Datei in das Profil ein.

> [!IMPORTANT]
> Ihre Surface Hubs müssen in einer Gerätegruppe gespeichert sein, damit Microsoft Intune ermitteln kann, auf welche Geräte das Konfigurationsprofil angewendet werden soll. Informationen zum Erstellen einer Gerätegruppe finden Sie unter Hinzufügen von Gruppen zum [Organisieren von Benutzern und Geräten.](/mem/intune/fundamentals/groups-add)

Gehen Sie wie folgt vor, um ein Konfigurationsprofil zu erstellen, um Teams-Einstellungen auf Ihre Surface Hubs anzuwenden:

1. Melden Sie sich bei Microsoft Endpoint Manager an, indem Sie https://endpoint.microsoft.com/
2. Navigieren Sie zu  >  **Gerätekonfigurationsprofile,** und wählen **Sie Profil erstellen aus.**
3. Wählen **Sie unter Plattform** die Option Windows **10 und höher aus.**
4. Wählen **Sie unter Profil** die Option **Benutzerdefiniert** aus, und klicken Sie dann auf **Erstellen.**
5. Geben Sie **auf der** Registerkarte Grundlagen unter **Name** einen beschreibenden Namen für Ihr Konfigurationsprofil ein, und wählen Sie **Weiter aus.**
6. Wählen Sie **auf der** Registerkarte Konfigurationseinstellungen die Option **Hinzufügen aus.**
7. Gehen Sie **im Bereich** Zeile hinzufügen wie folgt vor:
    1. Geben Sie einen beschreibenden Namen und optional eine Beschreibung der Von Ihnen hinzugefügten Teams-Einstellung an.
    2. Geben **Sie in OMA-URI** die `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. Wählen **Sie unter Datentyp** die Option Zeichenfolge **(XML-Datei) aus.**
    4. Öffnen Sie den Dateibrowser, wählen Sie die oben erstellte XML-Datei aus, und **öffnen Sie**
8. Wählen Sie **Hinzufügen** und dann **Weiter aus.**
9. Stellen Sie **auf der** Registerkarte Aufgaben sicher, dass **Zuweisen zu** auf Ausgewählte Gruppen **festgelegt ist.**
10. Wählen **Sie unter** Ausgewählte Gruppen die Option Gruppen auswählen aus, die sie enthalten soll, und wählen Sie dann die Gruppe aus, die Ihre Surface Hubs enthält, und wählen Sie dann Auswählen **aus.** 
11. Wählen **Sie Weiter**, Weiter **aus.**
12. Wählen Sie **auf der Seite Überprüfen + erstellen** die Option Erstellen **aus.**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Entfernen von Teams-Einstellungen von einem Surface Hub

Entfernen Sie die Microsoft Teams-Konfigurationseinstellungen auf Surface Hub mithilfe von Windows Configuration Designer oder Microsoft Intune in Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Entfernen eines vom Windows Configuration Designer erstellten Bereitstellungspakets

Wenn Sie teams-Einstellungen mithilfe eines vom Windows Configuration Designer erstellten Bereitstellungspakets auf einen Surface Hub angewendet haben, verwenden Sie die folgenden Schritte, um das Paket und seine Einstellungen zu entfernen:

1. Öffnen Sie auf Ihrem Surface Hub das Startmenü, wählen Sie **Alle Apps** und dann Einstellungen **aus.**
2. Geben Sie Ihren Administratornamen und ihr Kennwort ein, und wählen Sie dann **Ja aus.**
3. Wechseln Sie **zu Surface Hub**, **Geräteverwaltung** und **dann zu Hinzufügen oder Entfernen eines Bereitstellungspakets**
4. Wählen Sie neben dem Bereitstellungspaket, das Sie entfernen möchten, **Entfernen aus.**
5. Wechseln Sie **zu Surface Hub** und dann apps & **Features**
6. Suchen **Sie Microsoft Teams für Surface Hub,** und wählen Sie erweiterte Optionen **aus.**
7. Wählen **Sie Zurücksetzen** und dann erneut **zurücksetzen** aus.
8. Starten Sie Ihren Surface Hub neu.

### <a name="remove-settings-applied-by-microsoft-intune"></a>Von Microsoft Intune angewendete Einstellungen entfernen

Wenn Sie Teams-Einstellungen mit Microsoft Intune in Microsoft Endpoint Management auf einen Surface Hub angewendet haben, verwenden Sie die folgenden Schritte, um das Konfigurationsprofil und seine Einstellungen zu entfernen:

1. Melden Sie sich bei Microsoft Endpoint Manager an, indem Sie https://endpoint.microsoft.com/
2. Navigieren zu   >  **Gerätekonfigurationsprofilen**
3. Wählen Sie das Konfigurationsprofil aus, das die Einstellungen für die koordinierte Besprechung enthält, die Sie entfernen möchten.
4. Wählen Sie auf der Seite Konfigurationsprofildetails die Option **Löschen** und dann **OK aus.**

Nachdem Sie das Konfigurationsprofil entfernt haben, das die Einstellungen für die koordinierte Besprechung für Ihren Surface Hub enthält, verwenden Sie die folgenden Schritte, um die Teams-App auf dem Surface Hub zurückzusetzen:

1. Öffnen Sie auf Ihrem Surface Hub das Startmenü, wählen Sie **Alle Apps** und dann Einstellungen **aus.**
2. Geben Sie Ihren Administratornamen und ihr Kennwort ein, und wählen Sie dann **Ja aus.**
3. Wechseln Sie **zu Surface Hub** und dann apps & **Features**
4. Suchen **Sie Microsoft Teams für Surface Hub,** und wählen Sie erweiterte Optionen **aus.**
5. Wählen **Sie Zurücksetzen** und dann erneut **zurücksetzen** aus.
6. Starten Sie Ihren Surface Hub neu.