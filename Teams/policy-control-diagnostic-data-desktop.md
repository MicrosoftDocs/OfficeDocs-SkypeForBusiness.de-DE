---
title: Erforderliche Desktop-Client-Diagnosedaten für Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Eine Liste von Desktopeigenschaften und -ereignissen für die Richtliniensteuerelemente für Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbac20caa3f1eff0ead7ef0bf7f11d55b7718903
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136054"
---
# <a name="required-desktop-diagnostic-data-for-microsoft-teams"></a>Erforderliche Desktop-Diagnosedaten für Microsoft Teams

Der folgende Artikel enthält eine Liste von Microsoft Teams-Desktopereignissen sowie Listen von Eigenschaften, die vom jeweiligen Ereignis erfasst werden.

## <a name="events"></a>Ereignisse

> [!NOTE]
> Es gibt einige Eigenschaften, die von allen nachstehend aufgeführten Ereignissen übermittelt werden. Informationen hierzu finden Sie unter [Eigenschaften, die mit allen Ereignissen gesendet werden](#properties-sent-with-all-events).

### <a name="logging"></a>Protokollierung

> [!NOTE]
> Informationen zu den Eigenschaften von Protokollereignissen finden Sie unter [Eigenschaften, die mit Ereignisprotokollen gesendet werden](#properties-sent-with-logging-events).

- **adal-anonymous-mac.ts:this.logger.logError**: Zeichnet auf, dass bei der anonymen Anmeldung auf einem Mac-Gerät ein allgemeiner SSO-Fehler aufgetreten ist.
- **adalAnonymousUtil.ts:loggingService.getInstance**: Protokolliert eine Fehlermeldung, die besagt, dass die App die anonyme Benutzerauthentifizierung nicht starten konnte.
- **adal-anonymous-windows.ts:this.logger.logError**: Zeichnet auf, dass bei der anonymen Anmeldung auf einem Windows-Gerät ein allgemeiner SSO-Fehler aufgetreten ist.
- **adalBase.ts:this.loggingService.logError**: Zeichnet Informationen auf, die erforderlich sind, um festzustellen, ob das Benutzerprofil NULL oder leer ist.
- **adal-impl-mac.ts:this.loggingService.logError**: Zeichnet das Auftreten eines Problems beim Parsen von während der Authentifizierung erhaltenen Telemetriedaten oder eines allgemeinen SSO-Fehlers beim Anmelden auf einem Mac-Gerät auf.
- **adal-rigel-windows.ts:this.logger.logError**: Allgemeine Protokollangabe, die besagt, dass bei der Anmeldung auf dem Besprechungsraumgerät ein allgemeiner SSO-Fehler aufgetreten ist.
- **adal-sso-windows.ts:this.loggingService.logError**: Zeichnet das Auftreten eines allgemeinen SSO-Fehlers bei der Anmeldung auf einem Windows-Gerät, von Fehlern beim Initiieren des Chatdiensts oder Informationen zu Fehlern bei der Anmeldung auf.
- **appOnlineService.ts:loggingService.getInstance**: Zeichnet das Auftreten eines Fehlers aufgrund von Einstellungen, die während des Starts nicht analysiert werden konnten, oder beim Herunterladen vorautorisierter Einstellungen für die Benutzervorauthentifizierung auf.
- **appStart.ts:loggingService.logError**: Zeichnet das Auftreten eines Fehlers, wenn die Anwendung nicht gestartet werden konnte, Speicherplatzfehler, Fehler im Hinblick auf gültige Zertifikate oder Fehler beim Auffinden des richtigen Zertifikats und Neustarten der App auf.
- **browserWindowHttp.ts:this.loggingService.logError**: Zeichnet Informationen dazu auf, dass die Anwendung aufgrund von Problemen mit dem Dateisystem nicht aktualisiert werden konnte.
- **contextInstallService.ts:loggingService.getInstance**: Zeichnet das Auftreten eines Fehlers in folgenden Fällen auf:
  - bei dem Versuch, eine Datei zu analysieren oder auszulesen oder eine URL aufzulösen, die für das kontextbezogene Installationsfeature wichtig ist.
  - wenn der URL-Shortener versucht, das kontextbezogene Installationsfeature auszuführen.
- **crashManager.ts:loggingService.logError**: Zeichnet Informationen zur Ermittlung der Ursache eines Fehlers auf, wenn die Anwendung abstürzt.
- **localStorageService.ts:loggingService.getInstance**: Zeichnet das Auftreten eines Fehlers auf, wenn grundlegende Startdaten nicht ordnungsgemäß zum Ausführen der Anwendung geladen werden.
- **logProviders\pageDumpProvider.ts:loggingService.getInstance**: Zeichnet Fehlerinformationen auf, wenn die Anwendung abstürzt.
- **multiWindowManager.ts:this.logError**: Zeichnet das Auftreten eines Fehlers auf, wenn grundlegende Startdaten nicht ordnungsgemäß zum Ausführen der Anwendung geladen werden.
- **nativeElectronNotifications\osNotificationService.ts:this.loggingService.logError**: Zeichnet das Auftreten eines Fehlers bei dem Versuch, eine Benachrichtigung über einen Fehler zu starten, auf.
- **OutlookMeetingAddinHelper.ts:loggingService.getInstance**: Zeichnet das Auftreten eines Fehlers beim Herstellen einer Verbindung mit einer Besprechung mithilfe des Outlook-Besprechungs-Add-Ins auf.
- **recoveryManager.ts:loggingService.getInstance**: Zeichnet das Auftreten eines Fehlers während Update-Rollbacks auf.
- **renderer\startPage\startPage.ts:this.logger.logError**: Zeichnet das Auftreten eines Fehlers mit der Startseite der Anwendung auf.
- **settingsService.ts:loggingService.getInstance**: Zeichnet das Auftreten eines Fehlers im Zusammenhang mit den Anwendungseinstellungen auf.
- **updateInfo.ts:loggingService.getInstance**: Zeichnet das Auftreten eines Fehlers beim Übertragen von Updates auf.
- **updatenotification.js:this._loggingService.logError**: Zeichnet das Auftreten von Problemen mit dem Festplattenspeicher auf.
- **utility.ts:loggingService.logError**: Zeichnet einen Fehler beim Zugreifen auf eine lokale Datei (eine Datei in der Anwendung) auf.
- **utility.ts:loggingService.getInstance**: Zeichnet einen Fehler in Zusammenhang mit dem verfügbaren Festplattenspeicher, Anzeigeprobleme, URL-Probleme, Cookie-Probleme, Protokoll- oder RegKey-Probleme auf dem Computer beim Laden der Anwendung auf.
- **windowmanager.js:this._loggingService.logError**: Zeichnet das Auftreten von Cookie-Problemen, Whitescreen-Problemen, Problemen bei der Kommunikation zwischen Desktop und Shell, URL-Problemen, Fehlern beim Laden von Seitenbenachrichtigungen, Fehlern beim Prozess-Rendering und Problemen mit der Netzwerkkonnektivität auf.
- **windowmanager.js:loggingService.getInstance**: Zeichnet Informationen dazu auf, wann das Wiederherstellungsfenster nicht angezeigt werden konnte.

### <a name="outlook-addin"></a>Outlook-Add-In

> [!NOTE]
> Informationen zu den Eigenschaften von Outlook-Add-In-Ereignissen finden Sie unter [Eigenschaften, die mit Outlook-Add-In-Ereignissen gesendet werden](#properties-sent-with-outlook-addin-events).

- **joinmeetingoperation**: Zeichnet Informationen auf, die erforderlich sind, um einen Benutzer zu einer Besprechung hinzuzufügen.
- **meetingaddinapplifecycle**: Zeichnet Informationen zum App-Status auf, z. B. „Starten“ oder „Beenden“.
- **meetingaddinloadtime**: Zeichnet auf, wie lange das Laden von Besprechungsinformationen aus Outlook dauert.
- **openmeetingoperation**: Zeichnet Informationen auf, die zum Öffnen einer geplanten Besprechung erforderlich sind.
- **savemeetingoperation**: Zeichnet Informationen auf, die zum Speichern der Besprechung während deren Planung erforderlich sind.

### <a name="scenario"></a>Szenario

> [!NOTE]
> Informationen zu den Eigenschaften von Szenario-Ereignissen finden Sie unter [Eigenschaften, die mit Szenario-Ereignissen gesendet werden](#properties-sent-with-scenario-events).

- **desktop_app_load**: Zeichnet Informationen auf, die erforderlich sind, um festzustellen, ob die Desktopanwendung gestartet wurde, ob der Dienst initialisiert werden soll und ob er initialisiert werden kann.
- **desktop_app_not_ready**: Zeichnet Informationen auf, die erforderlich sind, um festzustellen, ob die Desktopanwendung nicht einsatzbereit ist.
- **desktop_install**: Zeichnet Informationen auf, die erforderlich sind, um zu ermitteln, ob die Desktopanwendung erfolgreich installiert wurde, oder ob die Installation fehlgeschlagen ist.
- **desktop_previous_lifecycle_invalid**: Zeichnet Informationen auf, die erforderlich sind, um zu ermitteln, ob die Desktopanwendung neu gestartet wurde, nachdem sie zuvor ausgeführt worden war und dann abstürzte.

### <a name="tracking"></a>Verfolgung

> [!NOTE]
> Informationen zu den Eigenschaften von Verfolgungsereignissen finden Sie unter [Eigenschaften, die mit Verfolgungsereignissen gesendet werden](#properties-sent-with-tracking-events).

- **deeplink_scenario_missing**: Microsoft Teams wurde über einen Deeplink gestartet, aber die Telemetrie-/Diagnosedaten sind nicht vorhanden.
- **desktop_app_initialized**: Zeichnet Informationen auf, die erforderlich sind, um festzustellen, ob die Anwendung erfolgreich gestartet wurde, wenn die Desktopanwendung initialisiert wird.
- **desktop_app_quit_exception**: Die Anwendung ist bei dem Versuch, sie zu schließen, abgestürzt.
- **desktop_blankScreenDetected**: Zeichnet Informationen auf, die zum Ermitteln von Fehlern erforderlich sind, wenn die Desktopanwendung einen leeren Bildschirm rendert.
- **desktop_blankScreenDetectedAfterRepaint**: Nach dem Erkennen eines Renderingversuchs wurde erkannt, dass die Seite leer war.
- **desktop_blankScreenRecoveredAfterRepaint**: Wiederherstellung nach einem vorherigen Renderingproblem, bei dem der Bildschirm nicht gerendert wurde.
- **desktop_configuration_failed_to_save**: Erfasst Informationen, die zum Ermitteln von Konfigurationsfehlern erforderlich sind, wenn die Desktopeinstellungen nicht gespeichert werden konnten.
- **desktop_navigation_error_recovery**: Erfasst Informationen, die zum Ermitteln von Desktop-Navigationsfehlern erforderlich sind, wenn eine Seite nach fünf Versuchen nicht geladen werden konnte.
- **desktop_previous_gpu_crashed**: Zeichnet Informationen auf, die zur Ermittlung von GPU-Fehlern erforderlich sind, wenn der Desktop abstürzt.
- **desktop_previous_plugin_host_crashed**: Erfasst Informationen, die zum Ermitteln von Medienstapelproblemen, die mit dem Absturz von Desktopanwendungen in Zusammenhang stehen, erforderlich sind.
- **desktop_recovery_cleared_user_data**: Zeichnet auf, dass die App mehrfach abstürzte, und dass die App zur Wiederherstellung den lokalen Cache löschen musste.
- **desktop_settings_blank_on_load**: Es liegt ein Fehler vor: keine Anwendungseinstellungen vorhanden.
- **desktop_settings_failed_to_load**: Erfasst Informationen, die zum Ermitteln der Ursachen erforderlich sind, wenn die Desktopeinstellungen nicht geladen werden.
- **desktop_silent_restart**: Das Client-Update erfolgt mehrstufig, und der Client wird ohne Unterbrechungen für den Benutzer aktualisiert.
- **desktop_terminated**: Zeichnet Informationen auf, die erforderlich sind, um festzustellen, ob die Kommunikation zwischen Prozessen unterbrochen wurde, als der Benutzer die Desktopanwendung geschlossen hat.
- **desktop_uncaught_exception**: Funktionsaufruf bei einem nicht definierten Objekt; dies führt zu einem Absturz/Neustart der App.
- **desktop_write_storage_failed**: Zeichnet Informationen auf, die zur Ermittlung von Festplattenfehlern erforderlich sind, wenn die Desktopanwendung nicht in den Speicher schreiben kann.
- **registration_failed**: Zeichnet Informationen auf, die zum Beheben von Fehlern bei der Add-In-Registrierung erforderlich sind.
- **registration_success**: Zeichnet Informationen auf, die erforderlich sind, um festzustellen, ob Add-In-Registrierungen erfolgreich waren.
- **security_unsupported_ipc_channel**: Unzulässige Nachricht zwischen Prozessen war eingehender Art.
- **sfb_running_not_connected**: Es wurde erkannt, dass die Skype for Business-App nicht ausgeführt wird.
- **sfb_not_running**: Zeichnet auf, dass das Zeitlimit für das Warten auf Antwort bei einem Anruf bei Skype for Business überschritten wurde.
- **sfb_never_replied**: Erfasst, ob bei der Kommunikation mit Skype for Business keine API-Antwort erfolgt.
- **server_error_hit**: Erfasst das Auftreten eines Fehlers bei den mit Skype for Business kommunizierenden IPC-Pipes.
- **unexpected_sfb_ipc_disconnection**: Zeichnet Informationen auf, die zur Ermittlung eines Fehlers beim Herstellen einer Verbindung mit dem Dienst erforderlich sind.
- **unregister_failed**: Zeichnet Informationen auf, die zum Ermitteln von Fehlern bei der Abmeldung des Outlook-Besprechungs-Add-Ins erforderlich sind.

## <a name="userbi-panelaction"></a>UserBI Panelaction

> [!NOTE]
> Informationen zu den Eigenschaften von UserBI Panelaction-Ereignissen finden Sie unter [Eigenschaften, die mit UserBI Panelaction-Ereignissen gesendet werden](#properties-sent-with-userbi-panelaction-events).

- **inlinereply**: Zeichnet Informationen dazu auf, ob ein Benutzer über die Benachrichtigung geantwortet hat.
- **toastclick**: Erfasst das Klicken eines Benutzers, um zur Nachrichteneingabe bei Popupbenachrichtigungen zu navigieren, um den SLA-Dienst zu überwachen und die entsprechende Antwort auf Popupbenachrichtigungen zu laden.
- **toastdismiss**: Zeichnet Informationen auf, die zur Ermittlung von Fehlern und Verzögerungen erforderlich sind, wenn der Benutzer die Darstellung einer Popupbenachrichtigung schließt.

- **toast_skip**: Zeichnet Informationen auf, die zur Vermeidung der verzögerten Übertragung einer Popupbenachrichtigung erforderlich sind.
- **toasttimeout**: Zeichnet Informationen auf, die zur Ermittlung von Fehlern und Verzögerungen erforderlich sind, wenn das Zeitlimit für die Darstellung einer Popupbenachrichtigung überschritten wurde.

### <a name="userbi-panelview"></a>UserBI Panelview

> [!NOTE]
> Informationen zu den Eigenschaften von UserBI Panelview-Ereignissen finden Sie unter [Eigenschaften, die mit UserBI Panelview-Ereignissen gesendet werden](#properties-sent-with-userbi-panelview-events).

- **toastshow**: Zeichnet Informationen auf, die erforderlich sind, um festzustellen, ob ein Popup gerendert wurde.

## <a name="property-lists"></a>Eigenschaftenlisten

### <a name="properties-sent-with-all-events"></a>Eigenschaften, die mit allen Ereignissen gesendet werden

| Name der Eigenschaft                              | Beschreibung                                                        |
|--------------------------------------------|--------------------------------------------------------------------|
| EventInfo_Time                             | Ereignisgenerierungszeit                                              |
| EventInfo_Name                             | Name des Ereignisses; wird verwendet, um zwischen Ereignistypen zu unterscheiden.             |
| EventInfo_BaseType/name                    | Ereignistyp; wird verwendet, um zwischen Ereignistypen in einem Ereignis zu unterscheiden. |
| EventInfo_Sequence                         | Ereignissequenz                                              |
| userAgent                                  | Zeichenfolge des Browser-Agents                                               |
| userpdclevel                               | Datenschutzeinstellung des Benutzers                           |
| eventpdclevel                              | Datenschutz-Kategorisierungsebene des Ereignisses             |
| AppInfo_Language                           | App-Sprache                                                       |
| clientType/AppInfo_ClientType              | Clienttyp, auf dem die App ausgeführt wird                               |
| environment/AppInfo_Environment            | Entwicklungsumgebung, die die Benutzeranforderung verarbeitet hat               |
| clientVersion/appversion/AppInfo_Version/desktopBuildVersion | Version der App                               |
| buildtime                                  | Zeitstempel, wann die App in den Entwicklungssystemen erstellt wurde            |
| osversion/DeviceInfo_OsVersion             | Betriebssystemversion                                                         |
| AppInfo_ProcessArchitecture                | Systemarchitektur (32bit/64bit)                                  |
| preferredLocales                           | Bevorzugtes Gebietsschema des Benutzers                                      |
| locale/AppInfo_Locale                      | App-Gebietsschema                                                         |
| os/DeviceInfo_OsName                       | Name des Betriebssystems                                                            |
| UserInfo_Language                          | Ausgewählte Benutzersprache                                             |
| UserInfo_Id                                | Benutzer-ID                                                            |
| UserInfo_TenantId/TenantId                 | Mandanten-ID                                                          |
| ring/UserInfo_Ring                         | Konzept, das bei der gestaffelten Bereitstellung von Anwendungen hilft.          |
| region                                     | Rechenzentrumsregion, in der die Anforderung des Benutzers verarbeitet wurde.                       |
| UserInfo_ConfigIds/UserInfo_Etag           | ID, mit der Benutzer in unterschiedlichen Experimenten/Rollouts identifiziert werden können.     |
| DeviceInfo_BrowserName                     | Browsername                                                       |
| DeviceInfo_BrowserVersion                  | Browserversion                                                    |
| DeviceInfo_Id/machineId/DeviceInfo_IdV2    | ID zur Identifizierung des Geräts                                  |
| totalMemory                                | Hardwarespeicher des Geräts                                      |
| cores                                      | Hardwarecores des Geräts                                       |
| cpuspeed                                   | Hardware-CPU-Geschwindigkeit des Geräts                                   |
| DeviceInfo_CpuArchitecture/cpuarchitecture | CPU-Architektur des Geräts                                     |
| UserRole                                   | Hilft bei der Identifizierung der Benutzerrolle in einem Mandanten                               |
| DeviceInfo_WindowsMode                     | Hilft bei der Identifizierung des Windows-Sicherheitsmodus                               |
| desktopSession/Session_Id                  | Hilft bei der Identifizierung einer Sitzung                                           |
| dbOpen                                     | Zeichnet den Status der lokalen Datenbank auf.                               |
| UserInfo_Upn                               | Einseitiger Hash der Benutzer-ID                                  |

### <a name="properties-sent-with-logging-events"></a>Eigenschaften, die mit Protokollereignissen gesendet werden

| Name der Eigenschaft         | Beschreibung                                                        |
|-----------------------|--------------------------------------------------------------------|
| message               | Zeichnet eine detaillierte Nachricht zum Protokoll auf                          |

### <a name="properties-sent-with-scenario-events"></a>Eigenschaften, die mit Szenario-Ereignissen gesendet werden

| Name der Eigenschaft                     | Beschreibung                                                                        |
|-----------------------------------|------------------------------------------------------------------------------------|
| Scenario_Status                   | Status eines Szenarios                                                               |
| Scenario_Step                     | Schritt in einem Szenario                                                                 |
| sequence                          | Sequenznummer des Szenarios                                                    |
| delta                             | Zum Ausführen verschiedener Schritte in einem Szenario benötigte Zeit                               |
| elapsed                           | Zeit seit dem Start des Szenarios                                                    |
| scenario                          | Eindeutige Identifizierung eines Szenarios                                                       |
| Scenario_Name                     | Name des Szenarios                                                               |
| errorInfo                         | Informationen zu dem Fehler, der während eines Szenarios evtl. aufgetreten ist.                       |
| session                           | Einmalige Sitzungs-ID                                                                  |
| freeMemory                        | Der erfasste verfügbare freie Speicher                                                     |
| processMemory                     | Der erfasste Prozessspeicher                                                            |
| scenarioDelta                     | Erfasst die zeitliche Differenz zwischen zwei Szenario-Schritten.                                   |
| Session_DesktopId                 | Einmalige Sitzungs-ID                                                                  |
| machineLocked                     | Erfasst, ob der Computer gesperrt war oder nicht.                                          |
| windowIsVisible                   | Erfasst, ob das App-Fenster für die Verwendung sichtbar war.                                      |
| appStates/webAppStates            | Erfasst eine Liste der App-Zustände, die die App durchlaufen hat. Dies hilft bei der Untersuchung von Abstürzen, weil wir sehen können, in welchem Zustand sich die App befand. |
| crashDesktopSession               | Zeichnet die ID der abgestürzten Sitzung auf.                                                 |
| appRuntime                        | Erfasst die Runtime der App.                                                        |
| diagnosticEvents                  | Letzte 50 Web-App-Diagnoseereignisse vor dem App-Absturz                                 |
| activities                        | Namen der letzten 50 Benutzerszenarien vor dem Absturz.                            |
| crashSession                      | Zeichnet die ID der abgestürzten Sitzung auf.                                                 |
| crashId                           | Zeichnet die ID der abgestürzten Sitzung auf.                                                 |
| isPreviousLifecycleValid          | Ob die App vorher vollständig initialisiert und erfolgreich beendet wurde             |
| isSettingValid                    | Ob die Einstellungen für die Vorauthentifizierung gültig sind                                                 |
| rollbackReason                    | Grund für das Zurücksetzen der App                                            |
| deeplinkType                      | Typ des Deeplinks                                                               |
| watchdogCrash                     | Ob die App abgestürzt ist, weil sie nicht mehr reagierte.                                                    |
| protocols                         | Zum Starten der App verwendetes Protokoll                                                    |
| electronBuild                     | Build-Version der elektronischen App                                                      |
| distribution                      |  Ob Microsoft Teams über exe, MSI, dmg, pkg usw. installiert wurde                    |
| updateTimeOfDay                   | Uhrzeit, zu der die App aktualisiert wurde                                                           |
| launchPath                        | Ob Microsoft Teams in %LOCALAPPDATA%, %PROGRAMFILES% oder an anderen Speicherorten installiert ist.   |
| loggedIn                          | Ob der Benutzer angemeldet war                                                          |
| envType/complianceEnvironmentType | Kommerzielle Cloud oder privat (z. B. DoD, GCC-High usw.)                              |
| cpuusage                          | CPU-Auslastung                                                                          |
| installationSource                | Der Installationstyp, über den der Benutzer verfügt                                                      |
| adalVersion                       | Version der Authentifizierungsbibliothek                                                        |
| asyncStart                        | Ob die App synchronen oder asynchronen Start verwendet.                                 |
| attempts                          | Die Anzahl der für den Benutzer vorgenommenen Online-Überprüfungsversuche, bevor ein Blockier-Bildschirm angezeigt wird. |

### <a name="properties-sent-with-tracking-events"></a>Eigenschaften, die mit Verfolgungsereignissen gesendet werden

| Name der Eigenschaft                      | Beschreibung                                                                      |
|------------------------------------|----------------------------------------------------------------------------------|
| name2                              | Erfasst den Namen des Verfolgungsereignisses.                                              |
| numVisibleNotifications            | Anzahl der sichtbaren Anwendungsbenachrichtigungen                                      |
| giphyEnabled                       | Ob der Giphy-Dienst aktiviert war                                                |
| error                              | Zeichnet Fehlerdetails im Zusammenhang mit dem Verfolgungsereignis auf.                             |
| method                             | Protokollmethode GET oder POST                                                      |
| channel                            | Erfasst den Kommunikationskanal zwischen Prozessen innerhalb der App.                      |
| windowTitle                        | Typ des Anzeigefensters, das dem Ereignis zugeordnet ist.                                     |
| message                            | Die Art der Fehlermeldung                                                        |
| crashSession/crashDesktopSession/crashId/Session_DesktopId/Session_DesktopBackgroundId | Zeichnet einmalige ID für Sitzungsdebuggingzwecke auf. |
| responseCode                       | Zeichnet den Antwortcode für den Dienstaufruf auf.                                      |
| errorUrl                           | Die URL, die nicht geladen werden konnte.                                                      |
| errorCode                          | Zeichnet den Fehlercode auf.                                                              |
| ssoEventData                       | Authentifizierungsstatus und Status                                                  |
| correlationId                      | ID zum Korrelieren von Ereignissen mit der Dienstseite für Debuggingzwecke                      |
| errorDescription                   | Erfasst die Beschreibung des Fehlercodes.                                            |
| source                             | Methode zum Abrufen der Microsoft Teams-App und des Pakettyps, von dem aus Microsoft Teams installiert wurde.       |
| windowIsDestroyed                  | True/False-Zustand von Anwendungsfenstern während des Ereignisses                             |
| windowIsFocused                    | True/False-Zustand von Anwendungsfenstern während des Ereignisses                             |
| windowIsVisible                    | Ob die Anwendung sichtbar war, als das Ereignis eingetreten ist.                                  |
| windowIsMinimized                  | True/False-Zustand von Anwendungsfenstern während des Ereignisses                             |
| windowIsMaximized                  | True/False-Zustand von Anwendungsfenstern während des Ereignisses                             |
| windowIsFullscreen                 | True/False-Zustand von Anwendungsfenstern während des Ereignisses                             |
| distSrc                            | Erfasst die Verteilungsquelle beim Landen des Benutzers in der App.                    |
| retries                            | Anzahl der erneuten Versuche, eine Verbindung mit einem Endpunkt herzustellen.                            |
| uses_slimcore                      | "True" oder "False", wenn slimcore von einem Webaufruf verwendet wird                                      |
| persistCookieExpiresIn             | Verbleibende Gültigkeit eines Webanwendungscookies                             |
| tenantName                         | Name des Mandanten für den Benutzer der Anwendung                                       |
| appStartReason                     | Wie die Anwendungssitzung gestartet wurde, z. B. durch den Benutzer initiiert, nach einem Update usw. |
| machineLocked                      | Ob der Computer während des Ereignisses gesperrt oder nicht gesperrt war.                        |
| data                               | Erfasst technische Daten für die Szenario-Untersuchung.                               |
| appRuntime                         | Erfasst die Runtime der App.                                                      |
| activities                         | Namen der letzten 50 Benutzerszenarien vor dem Absturz.                          |
| timeSinceActivity                  | Zeit seit der letzten Benutzeraktivität                                                    |
| appStates                          | Erfasst eine Liste von App-Zuständen, die die Desktop-App durchlaufen hat. Dies hilft bei der Untersuchung von Abstürzen, da erkennbar ist, in welchem Status sich die Desktop-App befand. |
| timeSinceAppState                  | Zeit seit der Änderung des App-Status                                                 |
| webAppStates                       | Erfasst eine Liste von App-Zuständen, die der Web-Client durchlaufen hat. Dies hilft bei der Untersuchung von Abstürzen, da erkennbar ist, in welchem Status sich der Web-Client befand. |
| timeSinceWebAppState               | Zeit seit der Änderung des Web-App-Zustands                                             |
| diagnosticEvents                   | Letzte 50 Web-App-Diagnoseereignisse vor dem App-Absturz                               |
| timeSinceLastDiagnosticEvent       | Zeit seit dem Senden des letzten Diagnoseereignisses                                            |
| timeSinceSecondLastDiagnosticEvent | Zeit seit dem Senden des vorletzten Diagnoseereignisses                                     |
| appInitialized                     | Ob Webanwendung gestartet wurde                                               |
| targetVersion                      | Die Version, auf die die Anwendung aktualisiert wird.                                    |
| port                               | Portnummer für Internetnachrichten                                                     |
| originalUrl                        | Ursprüngliche Adresse der gerenderten Seite                                         |
| deeplinkId                         | GUID für Zieltyp von Microsoft Teams-Link                                          |
| appSessionEnd                      | Ob das Ereignis am Ende der Anwendungssitzung eingetreten ist.                             |
| eventData                          | Zeichnet den Computerstatus und die App-Konfiguration auf, die beim Debugging bei Problemen helfen.        |
| deeplinkType                       | Typ des Deeplinks (Chat, Besprechung, Kanal)                                    |
| previousUpdateUrl                  | Die Adresse, von der die Anwendung ihr Update zuletzt abgerufen hat.                        |
| previousUpdateVersion              | Die letzte Version, auf die die Anwendung aktualisiert wurde.                                          |
| previousUpdateTime                 | Wann Binärdateien der Anwendung zuletzt aktualisiert wurden.                                      |
| protocol                           | Handlertyp für Link, z. B. Datei oder Bild                                     |
| files                              | Dateityp, der einem Ereignis zugeordnet ist, z. B. Anwendungscache oder GPU-Cache.    |
| Perf_WorkingSetSizeKB              | Größe des Arbeitsspeichercaches                                                             |
| isTimeboxingWebAppInitialize       | Ob die App vor Ablaufen des Zeitfeldrechners initialisiert wurde                          |
| isExp                              | Ob die verwendete App-Version Teil eines Tests ist                          |
| deviceType                         | Zeichnet die Art des Geräts auf.                                                      |
| sanitizedErr                       | Zeichnet die bereinigte Version der Fehlerinformationen auf.                              |
| rigelVersion                       | Erfasst die Version des Rigel-Geräts.                                                 |
| DeviceInfo_OsSku                   | Erfasst BS-SKU-Informationen.                                                      |
| isLoggedOut                        | Erfasst, ob der Benutzer abgemeldet ist.                                               |
| complianceEnvironmentType          | Kommerzielle Cloud oder privat (z. B. DoD, GCC-High usw.)                           |
| restartTimes                       | Genaue Zeiten vorheriger Neustarts                                                 |
| Skype_ResultCode                   | Zeichnet das Ergebnis der Interop-Kommunikation zwischen Skype und Microsoft Teams auf.                 |
| cpumodel                           | Erfasst das CPU-Modell.                                                            |
| isSlimCoreRunningOutproc           | Ob die Slimcore-Komponente im eigenen Prozess ausgeführt wird                         |
| isSlimCoreStartedAsync             | Art der Starts von internem Audio/Video-Stapel (A/V)                               |
| networkState                       | Erfasst den Netzwerkstatus.                                                    |
| desktopBuildAge                    | Alter des Anwendungsbuilds zum Zeitpunkt des Ereignisses.                                   |
| vdiMode                            | Erfasst, ob die App im VDI-Modus ausgeführt wird.                                       |

### <a name="properties-sent-with-userbi-panelview-events"></a>Eigenschaften, die mit UserBI Panelview-Ereignissen gesendet werden

| Eigenschaft           | Beschreibung                                              |
|--------------------|----------------------------------------------------------|
| Panel_Uri          | Der URI des für den Benutzer bereitgestellten Bereichs                   |
| Panel_Type         | Der Bereichstyp, auf den der Benutzer zugegriffen hat                          |
| Team_Id            | Die ID des Teams, in dem die Aktion vom Benutzer ausgeführt wurde. |
| Thread_Id          | Die ID des Threads, auf den der Benutzer zugegriffen hat.               |
| Panel_PreviousUri  | URI des vorhergehenden Bereichs                                |
| Panel_Region       | Region, in der der Bereich in der App gehostet wurde             |
| Panel_LaunchMethod | Methode, durch die der Bereich gestartet wurde              |
| Panel_PreviousType | Typ des vorhergehenden Bereichs                               |
| Thread_Type        | Der Typ des Threads, auf den der Benutzer zugegriffen hat                          |
| Panel_LaunchSource | Quellinformationen des gestarteten Bereichs        |
| Tab_Type           | Der Typ der Registerkarte, auf die der Benutzer zugegriffen hat                         |
| Team_Type          | Der Typ des Teams, auf das der Benutzer zugegriffen hat                            |

### <a name="properties-sent-with-userbi-panelaction-events"></a>Eigenschaften, die mit UserBI Panelaction-Ereignissen gesendet werden

| Name der Eigenschaft         | Beschreibung                                                        |
|-----------------------|--------------------------------------------------------------------|
| Action_DestinationUri | Der URI der Ressource, auf die die Benutzeraktion zugreift                  |
| Panel_Uri             | Der URI des für den Benutzer bereitgestellten Bereichs                             |
| Action_Gesture        | Die Art der vom Benutzer in der App ausgeführten Geste                       |
| Action_ScenarioType   | Featuregruppierung, die Geschäftsmetriken für das Feature entspricht.       |
| Panel_Type            | Der Bereichstyp, auf den der Benutzer zugegriffen hat                                    |
| Action_Outcome        | Ergebnis der Aktion, die vom Benutzer ausgeführt wurde                            |
| Team_Id               | Die ID des Teams, in dem die Aktion vom Benutzer ausgeführt wurde.           |
| Module_Type           | Der Typ des Moduls, das die Benutzeraktion gehostet hat                        |
| Module_Name           | Der Name des Moduls, das die Benutzeraktion gehostet hat                        |
| Module_Summary        | Zusammenfassung des Moduls, dass die Benutzeraktion gehostet hat                       |
| Thread_Id             | Die ID des Threads, auf den der Benutzer zugegriffen hat.                         |
| Panel_PreviousUri     | URI des vorhergehenden Bereichs                                          |
| Panel_Region          | Region, in der der Bereich in der App gehostet wurde                       |
| Panel_LaunchMethod    | Methode, durch die der Bereich gestartet wurde                        |
| Panel_PreviousType    | Typ des vorhergehenden Bereichs                                         |
| Thread_Type           | Der Typ des Threads, auf den der Benutzer zugegriffen hat                                    |
| Module_State          | Status des Moduls, auf das der Benutzer zugegriffen hat                               |
| Action_Scenario       | Funktion in einer Gruppe von Funktionen, die Geschäftsmetriken entspricht |
| Panel_LaunchSource    | Quellinformationen des gestarteten Bereichs                  |
| Tab_Type              | Der Typ der Registerkarte, auf die der Benutzer zugegriffen hat                                   |
| Team_Type             | Der Typ des Teams, auf das der Benutzer zugegriffen hat                                      |

### <a name="properties-sent-with-outlook-addin-events"></a>Eigenschaften, die mit Outlook-Add-In-Ereignissen gesendet werden

| Name der Eigenschaft                   | Beschreibung                                                              |
|---------------------------------|--------------------------------------------------------------------------|
| AccountComparisonFailedReason   | Das Add-In vergleicht das Konto mit dem Microsoft Teams-Konto, um zu ermitteln, ob die Erstellung zulässig ist; dieses Ereignis wird gesendet, wenn der Vergleich fehlschlägt. |
| AccountComparisonSuccessful     | Das Add-In vergleicht das Konto mit dem Microsoft Teams-Konto, um zu ermitteln, ob die Erstellung zulässig ist; dieses Ereignis wird gesendet, wenn der Vergleich erfolgreich war. |
| AdalVersion                     | Version der verwendeten Authentifizierungsbibliothek                               |
| AddinBitness                    | Version des Add-Ins                                                         |
| AddinLanguage                   | Sprache der verwendeten AddIn-Zeichenfolgen                                     |
| AggregatorSetupCompletedTime    | Einrichtungszeit für Add-In-Loader                                              |
| AppDomainCreatedTime            | Zeitpunkt, zu dem der AddIn-Loader die App-Domäne initialisiert                            |
| AppointmentDisplayTime          | Zeitpunkt, zu dem das Terminelement während der Besprechungserstellung angezeigt wurde |
| AuthenticationCompletedTime     | Zeitpunkt, zu dem die Authentifizierung für eine bestimmte Anforderung bereitgestellt wurde            |
| ConnectionMode                  | Gibt den Verbindungsmodus des primären Exchange-Kontos des Benutzers an.     |
| ConnectionStartedTime           | Uhrzeit, zu der Outlook OnConnection aufruft                                     |
| ErrorDetails                    | Zeichnet die Details zum Fehler auf.                                            |
| ErrorName                       | Zeichnet den Namen des Fehlers auf.                                               |
| ExchangeVersion                 | Erfasst die Exchange-Version.                                             |
| IsSmtpFormatError               | Fehler in SMTP-Adresse                                                    |
| IsTeamsRunning                  | Erfasst, ob ein Microsoft Teams-Prozess ausgeführt wird.                             |
| IsTeamsUserLoggedOut            | Erfasst, ob der Benutzer von Microsoft Teams abgemeldet ist.                              |
| LanguageSetupCompletedTime      | Zeitpunkt, zu dem die Spracheinrichtung abgeschlossen wurde                               |
| ManagedConnectTime              | Zeitpunkt, zu dem das verwaltete Add-In den Connect-Rückruf empfangen hat               |
| ManagedOnStartupTime            | Zeitpunkt, wenn mit dem Start begonnen hat                                    |
| MTFetchCompleted                | Zeitpunkt, zu dem die Anforderung von MT-Besprechungsoptionen abgeschlossen ist                        |
| NetFrameworkVersion             | Das verwendete .NET-Framework                                                      |
| NetworkAvailable                | Ob das Netzwerk verfügbar ist                                                     |
| OperationStartTime              |  Uhrzeit beim Start verschiedener Vorgänge                                  |
| OsBitness                       | Bitness des Betriebssystems                                                            |
| OutlookLanguage                 | Erfasst die Sprache der Outlook-App.                                     |
| OutlookVersion                  | Erfasst die Version der Outlook-App                                          |
| OwnerResolutionTime             | Zeit zum Auflösen des Besprechungsbesitzers                                        |
| ParseResponseCompletedTime      | Zeitpunkt, zu dem die Analyse der Antwort abgeschlossen ist                                  |
| RecipientResolutionError        | Fehlerdetails beim Auflösen eines Empfängers                                 |
| RecipientsResolutionTime        | Gesamtzeit, um alle Empfänger aufzulösen                                     |
| RehydrateCompletedTime          | Zeitpunkt, zu dem Eigenschaften aus Outlook gelesen werden                               |
| SaveToOutlookCompletedTime      | Zeitpunkt, zu dem Eigenschaften in Outlook gespeichert werden                                |
| ServiceRequestStartTime         | Startzeit der Serviceanfrage                                        |
| ServiceResponseReceiveTime      | Zeitpunkt der Antwort des Diensts                                        |
| SettingsInitializeCompletedTime | Zeitpunkt, zu dem die Einstellungen initialisiert wurden                                           |
| SetupLoggingCompletedTime       | Uhrzeit beim Einrichten der Protokollierung                                             |
| ShutdownBeginTime               | Zeitpunkt, zu dem das Herunterfahren des Add-Ins begonnen hat                                       |
| ShutdownCompletedTime           | Uhrzeit bei Abschluss des Herunterfahrens                                             |
| StartupBeginTime                | Zeitpunkt, zu dem das Starten des Add-Ins begonnen hat                                        |
| StartupCompletedTime            | Uhrzeit beim Abschluss des Starts                                              |
| TeamsDeployment                 | Bereitstellung des Microsoft Teams-Clients (Dev, Prod)                                   |
| TeamsRing                       | Ring des aktuellen Benutzers, der beim Microsoft Teams-Client angemeldet ist                            |
| TeamsVersion                    | Erfasst die Version der Microsoft Teams-App                                            |
| TelemetrySetupCompletedTime     | Zeitpunkt, zu dem die Telemetrie-Einrichtung abgeschlossen ist                                   |
| UpnMismatch                     | Ob eine UPN-Diskrepanz zwischen Outlook und Microsoft Teams vorliegt                  |
| UserDomain                      | Domäne des Benutzers                                                       |
| ViewUpdatedTime                 | Zeitpunkt, zu dem die Anzeige aktualisiert wurde                                           |
