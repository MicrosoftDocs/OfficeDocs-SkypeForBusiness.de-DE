---
title: Verwalten Microsoft Teams Konfiguration auf einem Surface Hub
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
ms.localizationpriority: medium
description: Verwalten Microsoft Teams Einstellungen für Surface Hub mithilfe Microsoft Intune und Windows Configuration Designer
ms.openlocfilehash: 70295a22524dc702832a729dc7e631c49b206053
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015265"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Verwalten Microsoft Teams Einstellungen auf Surface Hub

Sie können ihre Microsoft Teams auf einem Surface Hub mithilfe Windows Configuration Designer oder Microsoft Intune in Microsoft Endpoint Manager. Kenntnisse des Windows Konfigurations-Designers oder Microsoft Intune sind erforderlich, um Änderungen an den Einstellungen Teams vornehmen zu können. Weitere Informationen zu diesen Optionen finden Sie in den folgenden Artikeln:

- [Erstellen eines Bereitstellungspakets für Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [Was ist Microsoft Intune Geräteverwaltung?](/mem/intune/remote-actions/device-management)

Windows Configuration Designer ist eine gute Option, wenn Sie nur über ein paar Surface Hub verfügen und problemlos darauf zugreifen können. Wenn Sie viele Surface Hubs haben oder sich an Remotestandorten befinden, verwenden Sie Microsoft Intune in Microsoft Endpoint Manager, wenn es in Ihrer Organisation bereitgestellt ist. Unabhängig von der von Ihnen verwendeten Methode müssen Sie eine XML-Konfigurationsdatei erstellen, um Änderungen an den Teams Einstellungen für Surface Hub.

## <a name="teams-configuration-file-syntax"></a>Teams der Konfigurationsdatei

Teams konfiguration für ein Surface Hub mithilfe einer XML-Datei definiert. Die XML-Datei enthält alle Einstellungen, die verwendet werden können, um die Funktionsweise Teams steuern. Sowohl Windows Configuration Designer als Microsoft Intune verwenden dieselbe XML-Syntax. Hier sehen Sie ein Beispiel für die XML Teams Konfigurationsdatei:

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

In der folgenden Tabelle werden alle in der Konfigurationsdatei verfügbaren Konfigurationseinstellungen beschrieben:

| Übergeordnetes Element                  | Element                                   | Attribut | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Keine                    | `<SurfaceHubSettings>`                    |           | Enthält alle Konfigurationselemente für Teams Konfiguration auf einem Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Bestimmt, Surface Hub diese für Verbindungen verfügbar Bluetooth wird.<br>Akzeptierte Werte: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Bestimmt, Teams Besprechungen automatisch akzeptiert werden.<br>Akzeptierte Werte: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Enthält alle Konfigurationselemente für koordinierte Besprechungen.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Bestimmt, Teams für die Teilnahme an koordinierten Besprechungen mit anderen Geräten konfiguriert ist.<br>Akzeptierte Werte: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Dabei handelt es sich um eine durch Kommas getrennte Liste mit UPNs für jedes Teams Raumgerät oder jedes Surface Hub, von dem das Gerät Besprechungs-Joinanfragen annehmen oder an die Besprechungs-Joinanfragen gesendet werden sollen.<br>Akzeptierte Werte: Zeichenfolge                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Enthält Konfigurations-Audio- und Videokonfigurationselemente für koordinierte Besprechungen                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Steuert die Audiokonfiguration für Teams auf einem Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Bestimmt, auf welchem Gerät das Mikrofon beim Beginn einer Besprechung aktiv ist. Dieses Feld kann nur auf einem Gerät (in der Regel ein Teams-Räume-Gerät) festgelegt werden, während dieses Feld auf den restlichen Geräten auf festgelegt sein muss, um Audio-Echo und -Feedback `true` `false` zu vermeiden.<br>Akzeptierte Werte: `true` , `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Bestimmt, ob Teilnehmer an einer Besprechung das Mikrofon ein- oder ausschalten können. Auf Geräten, **auf denen der** Standardwert für Audio festgelegt ist, sollte diese Einstellung auf festgelegt sein, damit Teilnehmer nicht versehentlich ein Mikrofon aktivieren und Audio-Echo oder Feedback verursachen `false` `false` können.<p>Wenn **audio default** auf festgelegt ist, wird diese Einstellung ignoriert, und die Teilnehmer können das Mikrofon stummschalten bzw. die `true` Stummschaltung wieder einstellen.<br>Akzeptierte Werte: `true` , `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Steuert die Videokonfiguration für Teams auf einem Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Bestimmt, auf welchem Gerät die Kamera aktiv ist, wenn eine Besprechung beginnt. Für eine optimale Benutzererfahrung empfehlen wir, dass nur das Teams-Räume auf festgelegt wird, während alle `true` anderen Geräte auf festgelegt `false` sind.<br>Akzeptierte Werte: `true` , `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Bestimmt, ob Teilnehmer einer Besprechung die Kamera ein- oder ausschalten können. Sie können dies auf allen anderen Geräten der Ereignisteilnehmer festlegen, die unterschiedliche Videoperspektiven teilen möchten (z. B. wenn ein Teilnehmer das `true` Surface Hub verwendet). Wenn Sie nicht möchten, dass Teilnehmer eine Kamera auf einem Gerät ein- oder ausschalten, legen Sie dies auf `false` fest.<p> Wenn **video default** auf festgelegt ist, wird diese Einstellung ignoriert, und die Teilnehmer können die Kamera `true` ein- oder ausschalten.<br>Akzeptierte Werte: `true` , `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Anwenden Teams Einstellungen auf Surface Hub

Sie können Teams Konfigurationseinstellungen auf einem Surface Hub entweder mithilfe Windows Configuration Designer oder Microsoft Intune in Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>Verwenden Windows Configuration Designer

Sie können Windows Configuration Designer verwenden, um ein Bereitstellungspaket zu erstellen, das Sie zum Anwenden Teams Einstellungen auf Ihre Surface Hubs verwenden können. Sie fügen die oben erstellte XML-Datei in den Konfigurations-Designer Windows, um das Bereitstellungspaket zu erstellen.

> [!IMPORTANT]
> Wenn Sie ihre Teams bereits mithilfe eines Bereitstellungspakets Surface Hub angewendet haben und es ändern möchten, müssen Sie zuerst das vorhandene Bereitstellungspaket entfernen. Weitere Informationen finden Sie unter [Entfernen eines Bereitstellungspakets,](#remove-a-provisioning-package-created-by-windows-configuration-designer)das von Windows Configuration Designer erstellt wurde.

Gehen Sie wie folgt vor, um das Bereitstellungspaket in ihrem Windows zu erstellen:

1. Installieren Windows Configuration Designer aus dem Windows Store auf dem lokalen Computer, und öffnen Sie es
2. Wählen **Sie Geräte Surface Hub bereitstellen** und dann Zum **erweiterten Editor wechseln aus.**
3. Erweitern Sie auf dem nächsten Bildschirm **windowsTeamSettings**  >  **Teams** und wählen **Sie Configurations aus.**
4. Fügen Sie im Feld neben **Konfigurationen** im mittleren Bereich die oben erstellte einzelne XML-Zeile ein.
5. Wählen Sie **"Bereitstellungspaket**  >  **exportieren" aus.**
6. Geben Sie einen Namen für das Bereitstellungspaket in **Name ein,** und wählen Sie Weiter   >  **Weiter aus.**
7. Geben Sie einen Speicherort zum Speichern des Bereitstellungspakets an, und wählen Sie Weiter **aus.**
8. Wählen **Sie Erstellen** aus, um das Bereitstellungspaket zu erstellen, und wählen Sie dann Fertig stellen **aus.**

Nachdem Sie das Bereitstellungspaket erstellt haben, gehen Sie zum Schluss wie folgt vor, um das Bereitstellungspaket auf Ihre Surface Hub:

1. Speichern des oben erstellten Bereitstellungspakets auf einem USB-Laufwerk
2. Stecken Sie das USB-Laufwerk in den Surface Hub
3. Öffnen Sie Surface Hub Ihrer App Startmenü, wählen Sie **Alle Apps** aus, und wählen Sie **dann** Einstellungen
4. Geben Sie Ihren Administratorbenutzernamen und das Kennwort ein, und wählen Sie dann Ja **aus.**
5. Wechseln Sie **zu Surface Hub**, **Geräteverwaltung**, Hinzufügen oder Entfernen eines **Bereitstellungspakets** und dann **zu Paket hinzufügen.**
6. Wählen **Sie unter Paket auswählen** die Option **Hinzufügen** neben dem Bereitstellungspaket aus, und starten Sie die Surface Hub

### <a name="use-microsoft-intune"></a>Verwenden Microsoft Intune

Wenn Ihre Surface Hubs mithilfe von Microsoft Intune in Microsoft Endpoint Management verwaltet werden, können Sie es verwenden, um Teams Einstellungen auf Ihre Surface Hubs anzuwenden. Sie erstellen ein neues Konfigurationsprofil und fügen dann die oben erstellte XML-Datei in das Profil ein.

> [!IMPORTANT]
> Ihre Surface Hubs müssen in einer Gerätegruppe sein, damit die Microsoft Intune erkennen kann, auf welche Geräte das Konfigurationsprofil angewendet werden soll. Informationen zum Erstellen einer Gerätegruppe finden Sie unter Hinzufügen von Gruppen zum [Organisieren von Benutzern und Geräten.](/mem/intune/fundamentals/groups-add)

Gehen Sie wie folgt vor, um ein Konfigurationsprofil zu erstellen, um Teams Surface Hubs anzuwenden:

1. Melden Sie sich bei Microsoft Endpoint Manager an, indem Siehttps://endpoint.microsoft.com/
2. Navigieren Sie zu   >  **Gerätekonfigurationsprofile, und** wählen Sie **Profil erstellen aus.**
3. Wählen **Sie unter Plattform** Windows 10 und höher **aus.**
4. Wählen **Sie unter** Profil die Option **Benutzerdefiniert** aus, und klicken Sie dann **auf Erstellen.**
5. Geben Sie **auf der** Registerkarte Grundlagen unter **Name** einen beschreibenden Namen für Ihr Konfigurationsprofil ein, und wählen Sie Weiter **aus.**
6. Wählen Sie **auf der Registerkarte "Konfigurationseinstellungen"** die Option **"Hinzufügen" aus.**
7. Gehen Sie **im Bereich Zeile** hinzufügen wie folgt vor:
    1. Geben Sie einen beschreibenden Namen und optional eine Beschreibung der Teams, die Sie hinzufügen möchten.
    2. Geben **Sie in OMA-URI**`./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. Wählen **Sie unter Datentyp** die Option Zeichenfolge **(XML-Datei) aus.**
    4. Öffnen Sie den Dateibrowser, wählen Sie die oben erstellte XML-Datei und dann **Öffnen aus.**
8. Wählen **Sie Hinzufügen** und dann Weiter **aus.**
9. Vergewissern Sie **sich auf der** Registerkarte Aufgaben, dass Zuweisen **zu** auf Ausgewählte Gruppen **festgelegt ist.**
10. Wählen **Sie unter Ausgewählte Gruppen** die Option Zu **verwendende** Gruppen und dann die Gruppe aus, die Ihre Surface Hubs enthält. Wählen Sie dann **Auswählen**
11. Wählen Sie **Weiter**, **Weiter aus.**
12. Wählen Sie **auf der Seite Überprüfen und erstellen** die Option Erstellen **aus.**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Entfernen Teams Einstellungen aus einem Surface Hub

Entfernen Teams Konfigurationseinstellungen für Surface Hub mithilfe von Windows Configuration Designer oder Microsoft Intune in Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Entfernen eines Bereitstellungspakets, das von Windows Erstellt wurde

Wenn Sie mit Teams Configuration Designer erstellte Bereitstellungspakete Surface Hub Windows einem Teams angewendet haben, entfernen Sie das Paket und dessen Einstellungen mit den folgenden Schritten:

1. Öffnen Sie Surface Hub Ihrer App Startmenü, wählen Sie **Alle Apps** aus, und wählen Sie **dann** Einstellungen
2. Geben Sie Ihren Administratorbenutzernamen und das Kennwort ein, und wählen Sie dann Ja **aus.**
3. Wechseln Sie **Surface Hub**, **Geräteverwaltung** und dann **zu Bereitstellungspaket hinzufügen oder entfernen**
4. Wählen Sie neben dem Bereitstellungspaket, das Sie entfernen möchten, Entfernen **aus.**
5. Wechseln Sie **zu Surface Hub** und dann apps **& Features**
6. Suchen **Microsoft Teams Für Surface Hub** und wählen Sie dann Erweiterte Optionen **aus.**
7. Wählen **Sie Zurücksetzen** und dann erneut **Zurücksetzen** aus.
8. Starten Sie die Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>Entfernen von Einstellungen, die von der Microsoft Intune

Wenn Sie in microsoft Endpoint Management Teams-Einstellungen mithilfe Surface Hub -Microsoft Intune auf ein -Konto angewendet haben, entfernen Sie das Konfigurationsprofil und dessen Einstellungen mit den folgenden Schritten:

1. Melden Sie sich bei Microsoft Endpoint Manager an, indem Siehttps://endpoint.microsoft.com/
2. Navigieren zu   >  **Gerätekonfigurationsprofile**
3. Wählen Sie das Konfigurationsprofil aus, das die Einstellungen für die koordinierte Besprechung enthält, die Sie entfernen möchten.
4. Wählen Sie auf der Seite mit den Konfigurationsprofildetails Löschen **und** dann **OK aus.**

Nachdem Sie das Konfigurationsprofil entfernt haben, das die Einstellungen für die koordinierte Besprechung für Ihren Surface Hub enthielt, setzen Sie die Teams-App auf dem Surface Hub:

1. Öffnen Sie Surface Hub Ihrer App Startmenü, wählen Sie **Alle Apps** aus, und wählen Sie **dann** Einstellungen
2. Geben Sie Ihren Administratorbenutzernamen und das Kennwort ein, und wählen Sie dann Ja **aus.**
3. Wechseln Sie **zu Surface Hub** und dann apps **& Features**
4. Suchen **Microsoft Teams Für Surface Hub** und wählen Sie dann Erweiterte Optionen **aus.**
5. Wählen **Sie Zurücksetzen** und dann erneut **Zurücksetzen** aus.
6. Starten Sie die Surface Hub
