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
description: Verwalten von Microsoft Teams-Einstellungen auf Surface Hub mithilfe von Microsoft InTune und Windows-Konfigurations-Designer
ms.openlocfilehash: 3e254d7f7afbd918e8279d2dc7b100ebbfdc3daf
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761440"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Verwalten von Microsoft Teams-Einstellungen auf Surface Hub

Sie können die Microsoft Teams-Einstellungen auf einem Surface Hub mit dem Windows-Konfigurations-Designer oder Microsoft InTune in Microsoft Endpoint Manager verwalten. Kenntnisse über den Windows-Konfigurations-Designer oder Microsoft InTune sind erforderlich, um Änderungen an den Einstellungen für Teams vorzunehmen. Weitere Informationen zu diesen Optionen finden Sie in den folgenden Artikeln:

- [Erstellen eines Bereitstellungspakets für Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package)
- [Was ist die Microsoft InTune-Geräteverwaltung?](https://docs.microsoft.com/mem/intune/remote-actions/device-management)

Der Windows-Konfigurations-Designer ist eine gute Option, wenn Sie nur über einige Surface-Hub-Geräte verfügen und problemlos darauf zugreifen können. Wenn Sie über viele Surface Hubs verfügen oder sich an Remotestandorten befinden, verwenden Sie Microsoft InTune in Microsoft Endpoint Manager, wenn es in Ihrer Organisation bereitgestellt wird. Unabhängig von der gewählten Methode müssen Sie eine XML-Konfigurationsdatei erstellen, um Änderungen an den Einstellungen für Teams auf Surface Hub vorzunehmen.

## <a name="teams-configuration-file-syntax"></a>Syntax der Teams-Konfigurationsdatei

Die Konfiguration von Teams auf einem Surface Hub wird mithilfe einer XML-Datei definiert. Die XML-Datei enthält alle Einstellungen, die verwendet werden können, um zu steuern, wie Teams funktionieren. Sowohl der Windows-Konfigurations-Designer als auch Microsoft InTune verwenden dieselbe XML-Syntax. Im folgenden finden Sie ein Beispiel für die XML-Datei "Teams-Konfiguration":

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

In der folgenden Tabelle werden alle Konfigurationseinstellungen beschrieben, die in der Konfigurationsdatei zur Verfügung stehen:

| Eltern                  | Element                                   | Attribut | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Keine                    | `<SurfaceHubSettings>`                    |           | Enthält alle Konfigurationselemente für die Konfiguration von Teams auf einem Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Bestimmt, ob Surface Hub ankündigt, dass es für Bluetooth-Verbindungen verfügbar ist.<br>Akzeptierte Werte: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Bestimmt, ob Teams Näherungs basierte Besprechungen automatisch akzeptieren.<br>Akzeptierte Werte: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Enthält alle Konfigurationselemente für koordinierte Besprechungen.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Bestimmt, ob Teams für die Teilnahme an koordinierten Besprechungen mit anderen Geräten konfiguriert ist.<br>Akzeptierte Werte: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Hierbei handelt es sich um eine durch trennzeichengetrennte Liste von UPNs für jedes TeamRoom-Gerät oder einen Surface-Hub, von dem das Gerät Besprechungsteilnahme Anforderungen annehmen soll oder an die Besprechungsteilnahme Anforderungen gesendet werden sollen.<br>Akzeptierte Werte: Zeichenfolge                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Enthält Konfigurationselemente für Audio-und Videokonfiguration für koordinierte Besprechungen                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Steuert die Audiokonfiguration für Teams auf einem Surface-Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Bestimmt, auf welchem Gerät das Mikrofon aktiv sein soll, wenn eine Besprechung gestartet wird. Dieses Feld kann nur auf einem Gerät (in der Regel in einem Team Room-Gerät) eingestellt werden, `true` während auf den restlichen Geräten dieses Feld auf " `false` Audio-Echo und-Feedback verhindern" gesetzt sein muss.<br>Akzeptierte Werte: `true` , `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Bestimmt, ob Teilnehmer an einer Besprechung das Mikrofon ein-oder ausschalten können. Bei Geräten, auf denen die Standardeinstellung für **Audio** festgelegt ist, `false` sollte diese Einstellung so festgelegt sein `false` , dass die Teilnehmer nicht versehentlich ein Mikrofon einschalten und audioechos oder Feedback verursachen können.<p>Wenn **Audiostandard** auf festgelegt ist `true` , wird diese Einstellung ignoriert, und die Teilnehmer können das Mikrofon stumm schalten oder die Stummschaltung aufheben.<br>Akzeptierte Werte: `true` , `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Steuert die Videokonfiguration für Teams auf einem Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Bestimmt, auf welchem Gerät die Kamera aktiv ist, wenn eine Besprechung gestartet wird. Für eine optimale Benutzerfreundlichkeit empfehlen wir, dass nur das Gerät "Teams Rooms" auf eingestellt ist, `true` während alle anderen Geräte auf fest eingestellt sind `false` .<br>Akzeptierte Werte: `true` , `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Bestimmt, ob Teilnehmer an einer Besprechung die Kamera ein-oder ausschalten können. Sie können diese Einstellung `true` auf allen anderen Geräten in dem Ereignis festzulegen, in dem die Teilnehmer verschiedene Video Perspektiven freigeben möchten (beispielsweise, wenn ein Teilnehmer das Surface-Hub-Whiteboard verwendet). Wenn Sie nicht möchten, dass Teilnehmer eine Kamera auf einem Gerät ein-oder ausschalten, wählen Sie diese Option aus `false` .<p> Wenn **Video Standard** auf festgelegt ist `true` , wird diese Einstellung ignoriert, und die Teilnehmer können die Kamera ein-oder ausschalten.<br>Akzeptierte Werte: `true` , `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Anwenden von Teams-Einstellungen auf Surface Hub

Übernehmen oder aktualisieren Sie die Konfigurationseinstellungen für Teams auf Surface Hub mit dem Windows-Konfigurations-Designer oder Microsoft InTune in Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>Verwenden des Windows-Konfigurations-Designers

Mit dem Windows-Konfigurations-Designer können Sie ein Bereitstellungspaket erstellen, das Sie verwenden können, um die Einstellungen für Teams auf Ihre Surface Hubs anzuwenden. Sie fügen die oben erstellte XML-Datei in den Windows-Konfigurations-Designer ein, um das Bereitstellungspaket zu erstellen.

> [!IMPORTANT]
> Wenn Sie die Konfiguration von Teams bereits mithilfe eines Bereitstellungspakets auf Ihren Surface Hub angewendet haben und es ändern möchten, müssen Sie zuerst das vorhandene Bereitstellungspaket entfernen. Weitere Informationen finden Sie unter [Entfernen eines vom Windows-Konfigurations-Designer erstellten Bereitstellungspakets](#remove-a-provisioning-package-created-by-windows-configuration-designer).

Gehen Sie wie folgt vor, um das Bereitstellungspaket im Windows-Konfigurations-Designer zu erstellen:

1. Installieren Sie den Windows-Konfigurations-Designer aus dem Windows Store auf dem lokalen Computer, und öffnen Sie ihn.
2. Wählen Sie **Surface Hub Devices bereit** stellen und wechseln Sie dann **zu erweiterter Editor** .
3. Erweitern Sie auf dem nächsten Bildschirm **WindowsTeamSettings**  >  **Teams** , und wählen Sie **Konfigurationen** aus.
4. Fügen Sie in dem Feld neben **Konfigurationen** im mittleren Bereich die oben erstellte einzelne XML-Zeile ein.
5. Auswählen des **Export**  >  **Bereitstellungspakets**
6. Geben Sie einen Namen für das Bereitstellungspaket in **Name** ein, und wählen **Sie weiter**  >  **weiter** aus.
7. Geben Sie einen Speicherort zum Speichern des Bereitstellungspakets an, und wählen Sie **weiter** aus.
8. Wählen Sie **Erstellen** aus, um das Bereitstellungspaket zu erstellen und dann **fertig zu stellen** .

Nachdem Sie das Bereitstellungspaket erstellt haben, führen Sie die folgenden Schritte aus, um das Bereitstellungspaket auf Ihren Surface-Hub anzuwenden:

1. Speichern Sie das oben erstellte Bereitstellungspaket auf einem USB-Laufwerk.
2. Legen Sie das USB-Laufwerk in ihren Surface-Hub ein.
3. Öffnen Sie auf dem Surface Hub das Startmenü, wählen Sie **alle apps**aus, und wählen Sie dann **Einstellungen** aus.
4. Geben Sie Ihren Administrator-Nutzernamen und Ihr Kennwort ein und wählen Sie dann **Ja** aus.
5. Wechseln Sie zu **Surface Hub**, **Device Management**, **Hinzufügen oder Entfernen eines Bereitstellungspakets**, und **fügen Sie dann ein Paket hinzu** .
6. Wählen Sie unter **Paket auswählen**die Option neben Ihrem Bereitstellungspaket **Hinzufügen** aus, und starten Sie dann den Surface Hub neu.

### <a name="use-microsoft-intune"></a>Verwenden von Microsoft InTune

Wenn Ihre Surface Hubs mithilfe von Microsoft InTune in Microsoft Endpoint Management verwaltet werden, können Sie Sie verwenden, um die Einstellungen für Teams auf Ihre Surface Hubs anzuwenden. Erstellen Sie ein neues Konfigurationsprofil, und fügen Sie dann die oben erstellte XML-Datei ein.

> [!IMPORTANT]
> Ihre Surface Hubs müssen sich in einer Gerätegruppe befinden, damit Microsoft InTune erkennen kann, auf welche Geräte das Konfigurationsprofil angewendet werden soll. Informationen zum Erstellen einer Gerätegruppe finden Sie unter [Hinzufügen von Gruppen zum Organisieren von Benutzern und Geräten](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).

Gehen Sie wie folgt vor, um ein Konfigurationsprofil zu erstellen, um die Einstellungen für Teams auf Ihre Surface Hubs anzuwenden:

1. Wenn Sie sich bei Microsoft Endpoint Manager anmelden, besuchen Sie https://endpoint.microsoft.com/
2. Navigieren Sie zu **Devices**  >  -**Konfigurationsprofilen** , und wählen Sie **Profil erstellen** aus
3. Wählen Sie unter **Plattform**die Option **Windows 10 und höher** aus.
4. Wählen Sie unter **Profil**die Option **Benutzerdefiniert**aus, und klicken Sie dann auf **Erstellen** .
5. Geben Sie auf der Registerkarte **Grundlagen** in **Name**einen aussagekräftigen Namen für Ihr Konfigurationsprofil ein, und wählen Sie **weiter** aus.
6. Wählen Sie auf der Registerkarte **Konfigurationseinstellungen** die Option **Hinzufügen** aus.
7. Führen Sie im Bereich **Zeile hinzufügen** die folgenden Aktionen aus:
    1. Geben Sie einen aussagekräftigen Namen und optional eine Beschreibung der hinzuzufügenden Teams-Einstellung an.
    2. Geben Sie in **Oma-URI**`./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. Wählen Sie im **Datentyp**die **Zeichenfolge (XML-Datei)** aus.
    4. Öffnen Sie den Dateibrowser, wählen Sie die oben erstellte XML-Datei aus, und **Öffnen** Sie
8. Wählen Sie **Hinzufügen** und dann **weiter** aus.
9. Stellen Sie sicher, dass auf der Registerkarte **Aufgaben** die Option **zuweisen** an auf **ausgewählte Gruppen** gesetzt ist.
10. Wählen Sie unter **ausgewählte Gruppen**die Option **Gruppen zum einbeziehen** auswählen aus, und wählen Sie die Gruppe aus, die ihre Surface Hubs enthält, und wählen Sie dann **auswählen** aus.
11. Wählen **Next**Sie weiter **aus.**
12. **Wählen Sie** auf der Registerkarte **überprüfen + erstellen**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Entfernen von Team Einstellungen von einem Surface Hub

Entfernen Sie die Konfigurationseinstellungen für Teams auf Surface Hub mit dem Windows-Konfigurations-Designer oder Microsoft InTune in Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Entfernen eines vom Windows-Konfigurations-Designer erstellten Bereitstellungspakets

Wenn Sie die Einstellungen für Teams mithilfe eines vom Windows-Konfigurations-Designer erstellten Bereitstellungspakets auf einen Surface-Hub angewendet haben, entfernen Sie das Paket und dessen Einstellungen mit den folgenden Schritten:

1. Öffnen Sie auf dem Surface Hub das Startmenü, wählen Sie **alle apps**aus, und wählen Sie dann **Einstellungen** aus.
2. Geben Sie Ihren Administrator-Nutzernamen und Ihr Kennwort ein und wählen Sie dann **Ja** aus.
3. Wechseln Sie zu **Surface Hub**, **Device Management** , und **fügen Sie dann ein Bereitstellungspaket hinzu oder entfernen** Sie es.
4. Wählen Sie neben dem Bereitstellungspaket, das Sie entfernen möchten, die Option **Entfernen** aus.
5. Wechseln Sie zu **Surface Hub** und dann **apps & Features**
6. Suchen Sie **Microsoft Teams für Surface Hub** , und wählen Sie dann **Erweiterte Optionen** aus.
7. Wählen Sie **Zurücksetzen**und dann erneut **Zurücksetzen** aus.
8. Neustarten des Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>Entfernen der von Microsoft InTune angewendeten Einstellungen

Wenn Sie die Einstellungen für Teams auf einem Surface Hub mithilfe von Microsoft InTune in Microsoft Endpoint Management angewendet haben, entfernen Sie das Konfigurationsprofil und dessen Einstellungen mit den folgenden Schritten:

1. Wenn Sie sich bei Microsoft Endpoint Manager anmelden, besuchen Sie https://endpoint.microsoft.com/
2. Navigieren zu **Devices**-  >  **Konfigurationsprofilen**
3. Wählen Sie das Konfigurationsprofil aus, das die koordinierten Besprechungseinstellungen enthält, die Sie entfernen möchten.
4. Wählen Sie auf der Seite Konfigurationsprofil Details die Option **Löschen** und dann **OK** aus.

Nachdem Sie das Konfigurationsprofil entfernt haben, das die koordinierten Besprechungseinstellungen für Ihren Surface-Hub enthielt, führen Sie die folgenden Schritte aus, um die Teams-App auf dem Surface-Hub zurückzusetzen:

1. Öffnen Sie auf dem Surface Hub das Startmenü, wählen Sie **alle apps**aus, und wählen Sie dann **Einstellungen** aus.
2. Geben Sie Ihren Administrator-Nutzernamen und Ihr Kennwort ein und wählen Sie dann **Ja** aus.
3. Wechseln Sie zu **Surface Hub** und dann **apps & Features**
4. Suchen Sie **Microsoft Teams für Surface Hub** , und wählen Sie dann **Erweiterte Optionen** aus.
5. Wählen Sie **Zurücksetzen**und dann erneut **Zurücksetzen** aus.
6. Neustarten des Surface Hub