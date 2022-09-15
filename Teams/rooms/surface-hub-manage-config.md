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
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Verwalten von Microsoft Teams-Einstellungen auf Surface Hub mit Microsoft Intune und Windows-Konfigurations-Designer
ms.openlocfilehash: 7296ed84cf34b47c562cb3ab5f5582fe1eec58ac
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705974"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Verwalten von Microsoft Teams-Einstellungen auf Surface Hub

Sie können Microsoft Teams-Einstellungen auf einem Surface Hub mit dem Windows-Konfigurations-Designer oder Microsoft Intune in Microsoft Endpoint Manager verwalten. Kenntnisse des Windows-Konfigurations-Designers oder Microsoft Intune sind erforderlich, um Änderungen an den Teams-Einstellungen vorzunehmen. Weitere Informationen zu diesen Optionen finden Sie in den folgenden Artikeln:

- [Erstellen eines Bereitstellungspakets für Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [Was ist Microsoft Intune Geräteverwaltung?](/mem/intune/remote-actions/device-management)

Windows-Konfigurations-Designer ist eine gute Option, wenn Sie nur über wenige Surface Hub-Geräte verfügen und einfach darauf zugreifen können. Wenn Sie über viele Surface Hubs verfügen oder sich an Remotestandorten befinden, verwenden Sie Microsoft Intune in Microsoft Endpoint Manager, wenn sie in Ihrer Organisation bereitgestellt werden. Unabhängig von der gewählten Methode müssen Sie eine XML-Konfigurationsdatei erstellen, um Änderungen an den Teams-Einstellungen auf Surface Hub vorzunehmen.

## <a name="teams-configuration-file-syntax"></a>Syntax der Teams-Konfigurationsdatei

Die Teams-Konfiguration auf einem Surface Hub wird mithilfe einer XML-Datei definiert. Die XML-Datei enthält alle Einstellungen, die verwendet werden können, um die Funktionsweise von Teams zu steuern. Sowohl Der Windows-Konfigurations-Designer als auch Microsoft Intune verwenden dieselbe XML-Syntax. Hier ist ein Beispiel für die XML-Konfigurationsdatei von Teams:

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

In der folgenden Tabelle werden alle konfigurationseinstellungen beschrieben, die in der Konfigurationsdatei verfügbar sind:

| Elternteil                  | Element                                   | Attribut | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Keine                    | `<SurfaceHubSettings>`                    |           | Enthält alle Konfigurationselemente für die Teams-Konfiguration auf einem Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Bestimmt, ob Surface Hub angibt, dass es für Bluetooth-Verbindungen verfügbar ist.<br>Akzeptierte Werte: `true`, `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Bestimmt, ob Teams automatisch näherungsbasierte Besprechungen akzeptiert.<br>Akzeptierte Werte: `true`, `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Enthält alle Konfigurationselemente für koordinierte Besprechungen.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Bestimmt, ob Teams für die Teilnahme an koordinierten Besprechungen mit anderen Geräten konfiguriert ist.<br>Akzeptierte Werte: `true`, `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Dies ist eine durch Trennzeichen getrennte Liste von UPNs für jedes Teams-Räume Gerät oder Surface Hub, von dem das Gerät Besprechungsteilnahmeanfragen annehmen soll oder an die Besprechungsteilnahmeanfragen gesendet werden sollen.<br>Akzeptierte Werte: string                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Enthält Konfigurations-Audio- und Videokonfigurationselemente für koordinierte Besprechungen                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Steuert die Audiokonfiguration für Teams auf einem Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Bestimmt, auf welchem Gerät das Mikrofon aktiv ist, wenn eine Besprechung beginnt. Nur ein Gerät (in der Regel ein Teams-Räume Gerät) kann dieses Feld festlegen`true`, während für die restlichen Geräte dieses Feld festgelegt sein muss, um Audio-Echo und -Feedback zu `false` vermeiden.<br>Akzeptierte Werte: `true`, `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Bestimmt, ob teilnehmer an einer Besprechung das Mikrofon ein- oder ausschalten können. Auf Geräten, auf denen der **Audiostandard** festgelegt `false` ist, sollte diese Einstellung so festgelegt `false` sein, dass Teilnehmer nicht versehentlich ein Mikrofon einschalten und Audio-Echo oder Feedback auslösen können.<p>Wenn der **Audiostandard** festgelegt `true`ist, wird diese Einstellung ignoriert, und die Teilnehmer können das Mikrofon stummschalten oder die Stummschaltung aufheben.<br>Akzeptierte Werte: `true`, `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Steuert die Videokonfiguration für Teams auf einem Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Bestimmt, auf welchem Gerät die Kamera aktiv ist, wenn eine Besprechung beginnt. Für eine optimale Benutzererfahrung wird empfohlen, dass nur die Teams-Räume Geräts festgelegt `true` wird, während alle anderen Geräte auf `false`festgelegt sind.<br>Akzeptierte Werte: `true`, `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Bestimmt, ob Teilnehmer an einer Besprechung die Kamera ein- oder ausschalten können. Sie können dies `true` auf allen anderen Geräten des Ereignisses festlegen, auf dem Teilnehmer unterschiedliche Videoperspektiven teilen möchten (z. B. wenn ein Teilnehmer das Surface Hub-Whiteboard verwendet). Wenn Sie nicht möchten, dass Teilnehmer eine Kamera auf einem Gerät ein- oder ausschalten, legen Sie dies auf `false`" fest.<p> Wenn **der Videostandard** festgelegt `true`ist, wird diese Einstellung ignoriert, und teilnehmer können die Kamera ein- oder ausschalten.<br>Akzeptierte Werte: `true`, `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Anwenden von Teams-Einstellungen auf Surface Hub

Wenden Sie Teams-Konfigurationseinstellungen auf Surface Hub entweder mit dem Windows-Konfigurations-Designer oder mit Microsoft Intune in Microsoft Endpoint Manager an, oder aktualisieren Sie sie.

### <a name="use-windows-configuration-designer"></a>Verwenden des Windows-Konfigurations-Designers

Sie können den Windows-Konfigurations-Designer verwenden, um ein Bereitstellungspaket zu erstellen, mit dem Sie Teams-Einstellungen auf Ihre Surface Hubs anwenden können. Sie fügen die oben erstellte XML-Datei in den Windows-Konfigurations-Designer ein, um das Bereitstellungspaket zu erstellen.

> [!IMPORTANT]
> Wenn Sie die Teams-Konfiguration bereits mithilfe eines Bereitstellungspakets auf Surface Hub angewendet haben und diese ändern möchten, müssen Sie zuerst das vorhandene Bereitstellungspaket entfernen. Weitere Informationen finden Sie unter [Entfernen eines Bereitstellungspakets, das von Windows Configuration Designer erstellt wurde](#remove-a-provisioning-package-created-by-windows-configuration-designer).

Gehen Sie wie folgt vor, um das Bereitstellungspaket im Windows-Konfigurations-Designer zu erstellen:

1. Installieren Sie Den Windows-Konfigurations-Designer aus dem Windows Store auf Ihrem lokalen Computer, und öffnen Sie ihn
2. Wählen Sie **"Surface Hub-Geräte bereitstellen** " und dann **zum erweiterten Editor wechseln**
3. Erweitern Sie auf dem nächsten Bildschirm **WindowsTeamSettings** > **Teams**, und wählen Sie **"Konfigurationen**" aus.
4. Fügen Sie im Feld neben **"Konfigurationen** " im mittleren Bereich die einzelne XML-Zeile ein, die Sie oben erstellt haben.
5. Wählen Sie "**Bereitstellungspaket exportieren" aus****.** > 
6. Geben Sie einen Namen für das Bereitstellungspaket unter **"Name**" ein, und wählen Sie **"Weiter** > **"** aus.
7. Geben Sie einen Speicherort zum Speichern des Bereitstellungspakets an, und wählen Sie **"Weiter**" aus.
8. Wählen Sie **"Erstellen**" aus, um das Bereitstellungspaket zu erstellen, und **beenden Sie** dann

Nachdem Sie das Bereitstellungspaket erstellt haben, führen Sie die folgenden Schritte aus, um das Bereitstellungspaket auf Surface Hub anzuwenden:

1. Speichern des oben erstellten Bereitstellungspakets auf einem USB-Laufwerk
2. Schließen Sie das USB-Laufwerk an Den Surface Hub an.
3. Öffnen Sie auf Ihrem Surface Hub das Startmenü, wählen Sie **"Alle Apps**" und dann **"Einstellungen"** aus.
4. Geben Sie Ihren Administratorbenutzernamen und Ihr Kennwort ein, und wählen Sie dann **"Ja**" aus.
5. Wechseln Sie zu **Surface Hub**, **Geräteverwaltung**, **Hinzufügen oder Entfernen eines Bereitstellungspakets**, und **fügen Sie dann ein Paket hinzu**
6. Wählen **Sie unter "Paket auswählen**" die Option **"Hinzufügen"** neben dem Bereitstellungspaket aus, und starten Sie den Surface Hub neu.

### <a name="use-microsoft-intune"></a>Verwenden von Microsoft Intune

Wenn Ihre Surface Hubs mithilfe von Microsoft Intune in Microsoft Endpoint Management verwaltet werden, können Sie damit Teams-Einstellungen auf Ihre Surface Hubs anwenden. Sie erstellen ein neues Konfigurationsprofil und fügen dann die oben erstellte XML-Datei in das Profil ein.

> [!IMPORTANT]
> Ihre Surface Hubs müssen sich in einer Gerätegruppe befinden, damit die Microsoft Intune erkennen können, auf welche Geräte das Konfigurationsprofil angewendet werden soll. Informationen zum Erstellen einer Gerätegruppe finden [Sie unter "Hinzufügen von Gruppen zum Organisieren von Benutzern und Geräten](/mem/intune/fundamentals/groups-add)".

Gehen Sie wie folgt vor, um ein Konfigurationsprofil zu erstellen, um Teams-Einstellungen auf Ihre Surface Hubs anzuwenden:

1. Melden Sie sich bei Microsoft Endpoint Manager an, indem Siehttps://endpoint.microsoft.com/
2. Navigieren Sie zu **Gerätekonfigurationsprofilen** > , und wählen Sie **"Profil erstellen" aus**.
3. Wählen Sie unter **"Plattform****" Windows 10 und höher** aus.
4. Wählen Sie unter **"Profil**" die Option **"Benutzerdefiniert**" aus, und klicken Sie dann auf **"Erstellen"**.
5. Geben Sie auf der Registerkarte "**Grundlagen**" unter **"Name**" einen beschreibenden Namen für Ihr Konfigurationsprofil an, und wählen Sie **"Weiter**" aus.
6. Wählen Sie auf der Registerkarte **"Konfigurationseinstellungen**" die Option **"Hinzufügen"** aus.
7. **Führen Sie im Bereich "Zeile hinzufügen**" die folgenden Schritte aus:
    1. Geben Sie einen beschreibenden Namen und optional eine Beschreibung der Teams-Einstellung an, die Sie hinzufügen möchten.
    2. Geben Sie **in OMA-URI**`./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. Wählen Sie **im Datentyp** **"Zeichenfolge" (XML-Datei)** aus.
    4. Öffnen Sie den Dateibrowser, wählen Sie die oben erstellte XML-Datei aus, und **öffnen** Sie
8. Wählen Sie **"Hinzufügen"** und dann "Weiter" aus **.**
9. Stellen Sie auf der Registerkarte **"Aufgaben**" sicher, dass "**Zuweisen zu**" auf **"Ausgewählte Gruppen**" festgelegt ist.
10. Wählen Sie unter **"Ausgewählte Gruppen**" die Option "**Gruppen auswählen" aus, um sie einzuschließen**, wählen Sie die Gruppe aus, die Ihre Surface Hubs enthält, und wählen **Sie dann "Auswählen"** aus.
11. Wählen Sie **"Weiter**", **"Weiter" aus**.
12. Wählen Sie unter **"Überprüfen + Erstellen**" die Option **"Erstellen"** aus.

## <a name="remove-teams-settings-from-a-surface-hub"></a>Entfernen von Teams-Einstellungen aus einem Surface Hub

Entfernen Sie Teams-Konfigurationseinstellungen auf Surface Hub entweder mit dem Windows-Konfigurations-Designer oder Microsoft Intune in Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Entfernen eines von Windows Configuration Designer erstellten Bereitstellungspakets

Wenn Sie Teams-Einstellungen mithilfe eines von Windows Configuration Designer erstellten Bereitstellungspakets auf einen Surface Hub angewendet haben, führen Sie die folgenden Schritte aus, um das Paket und seine Einstellungen zu entfernen:

1. Öffnen Sie auf Ihrem Surface Hub das Startmenü, wählen Sie **"Alle Apps**" und dann **"Einstellungen"** aus.
2. Geben Sie Ihren Administratorbenutzernamen und Ihr Kennwort ein, und wählen Sie dann **"Ja**" aus.
3. Wechseln Sie zu **Surface Hub**, **Geräteverwaltung** , und **fügen Sie dann ein Bereitstellungspaket hinzu oder entfernen Sie es.**
4. Wählen Sie neben dem Bereitstellungspaket, das Sie entfernen möchten, die Option **"Entfernen"** aus.
5. Wechseln Sie zu **Surface Hub** und dann **zu Apps & Features**
6. Suchen Sie **Microsoft Teams für Surface Hub**, und wählen Sie dann **"Erweiterte Optionen"** aus.
7. Wählen Sie **"Zurücksetzen"** und dann erneut **"Zurücksetzen"** aus.
8. Starten Sie Surface Hub neu.

### <a name="remove-settings-applied-by-microsoft-intune"></a>Von Microsoft Intune angewendete Einstellungen entfernen

Wenn Sie Teams-Einstellungen mithilfe von Microsoft Intune in Microsoft Endpoint Management auf einen Surface Hub angewendet haben, führen Sie die folgenden Schritte aus, um das Konfigurationsprofil und seine Einstellungen zu entfernen:

1. Melden Sie sich bei Microsoft Endpoint Manager an, indem Siehttps://endpoint.microsoft.com/
2. Navigieren zu **Gerätekonfigurationsprofilen**  > 
3. Wählen Sie das Konfigurationsprofil aus, das die Einstellungen für koordinierte Besprechungen enthält, die Sie entfernen möchten.
4. Wählen Sie auf der Seite "Konfigurationsprofildetails" die Option **"Löschen"** und dann **"OK**" aus.

Nachdem Sie das Konfigurationsprofil entfernt haben, das die Einstellungen für die koordinierte Besprechung für Surface Hub enthielt, führen Sie die folgenden Schritte aus, um die Teams-App auf surface Hub zurückzusetzen:

1. Öffnen Sie auf Ihrem Surface Hub das Startmenü, wählen Sie **"Alle Apps**" und dann **"Einstellungen"** aus.
2. Geben Sie Ihren Administratorbenutzernamen und Ihr Kennwort ein, und wählen Sie dann **"Ja**" aus.
3. Wechseln Sie zu **Surface Hub** und dann **zu Apps & Features**
4. Suchen Sie **Microsoft Teams für Surface Hub**, und wählen Sie dann **"Erweiterte Optionen"** aus.
5. Wählen Sie **"Zurücksetzen"** und dann erneut **"Zurücksetzen"** aus.
6. Starten Sie Surface Hub neu.
