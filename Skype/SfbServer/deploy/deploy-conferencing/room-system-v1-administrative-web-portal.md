---
title: Bereitstellen von SRS v1 Administrative Webportal in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Die Skype für Server Skype Raum Geschäftssystemen v1 (SRS v1, früher bekannt als Lync Raum System) Administrative Webportal ist ein Webportal, mit denen Organisationen können der Konferenzräume Skype Raum Systeme verwalten. Administratoren können dem SRS v1 Administrative Webportal Gerät Zustand, beispielsweise zu überwachen, durch die Überwachung der a/v-Geräte verwenden. Mit diesem Portal können Administratoren über Remoteverbindungen Diagnoseinformationen sammeln, um die Konferenzraumintegrität zu überwachen.
ms.openlocfilehash: b616084016a3b660f4af5bcd3bda6926dfc7e286
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012905"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Bereitstellen von SRS v1 Administrative Webportal in Skype für Business Server

Die Skype für Server Skype Raum Geschäftssystemen v1 (SRS v1, früher bekannt als Lync Raum System) Administrative Webportal ist ein Webportal, mit denen Organisationen können der Konferenzräume Skype Raum Systeme verwalten. Administratoren können dem SRS v1 Administrative Webportal Gerät Zustand, beispielsweise zu überwachen, durch die Überwachung der a/v-Geräte verwenden. Mit diesem Portal können Administratoren über Remoteverbindungen Diagnoseinformationen sammeln, um die Konferenzraumintegrität zu überwachen.

Um dieses Feature verwenden können, muss dem SRS v1 Administrative Webportal auf jedem Skype für Business Server-Front-End-Server bereitgestellt werden. Dieses Handbuch enthält Anweisungen für Administratoren, wie das Webportal zur Verwaltung von SRS installiert und konfiguriert wird. Es ist für Administratoren vorgesehen, die Skype-Kenntnisse für die Verwaltung der Business Server besitzen und über Administratorrechte verfügen, um die Skype für Business Server-Topologie ändern verfügen.

Nach der SRS v1, den administrativen Webportal auf dem Server bereitgestellt wird, können Administratoren von ihren eigenen Computern oder Laptops an der Website anmelden, um den Status SRS v1-Geräten überprüfen.

> [!IMPORTANT]
> Laden Sie das [Microsoft Skype Raum Systeme v1 Administrative Webportal für Skype für Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).

In diesem Thema:

- [Konfigurieren Sie Ihre Umgebung für das Webportal zur Verwaltung von SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)

- [Installieren Sie das Webportal zur Verwaltung von SRS v1](room-system-v1-administrative-web-portal.md#Install_SRS)

- [Verwenden Sie das Webportal zur Verwaltung von SRS](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>Konfigurieren Sie Ihre Umgebung für das Webportal zur Verwaltung von SRS v1
<a name="Config_Env"> </a>

Zur Nutzung des Webportals für die Verwaltung des SRS v1 müssen Sie die folgenden Voraussetzungen installieren oder konfigurieren.

> [!IMPORTANT]
> Wenn für den Server sowohl Kerberos- als auch die NTLM-Authentifizerung konfiguriert wurde und SRS auf einem Computer ausgeführt wird, der nicht Teil der Domäne ist, schlägt die Kerberos-Authentifizierung fehl und dem Benutzer wird der SRS-Status im Verwaltungsportal nicht angezeigt. Sie können dieses Problem lösen, indem Sie entweder die NTLM-Authentifizierung bzw. die NTLM- und TLS-DSK-Authentifizierung (ohne Kerberos) konfigurieren oder mit dem SRS-Computer der Domäne beitreten.

1. Installieren Sie Skype für Business Server kumulativen Updates in der Skype für Business Server-Topologie.

    Um das Update oder Umfang mit angezeigt wird, finden Sie unter [Updates für Skype für Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).

2. Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer.

    Der SRS v1 Administrative Webportal verwendet diese Anmeldeinformationen zur Abfrage von Informationen von Skype für Business Server. Der in den Beispielen verwendete Benutzername lautet LRSApp.

3. Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSSupportAdminGroup.

    Erstellen Sie die Gruppe mit dem Gruppenbereich  Global  und dem Gruppentyp  Sicherheit . SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, die Liste der Räume anzuzeigen und bestimmte Befehle auszuführen, wie das Speichern von Protokollen.

4. Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSFullAccessAdminGroup. 

    Erstellen Sie die Gruppe mit dem Gruppenbereich „Global“ und dem Gruppentyp „Sicherheit“. SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, alle Funktionen des Verwaltungsportals für einen einzelnen Skype-Raum zu nutzen. Um Unterstützung für die Massenverwaltung von Skype-Räumen zu erhalten, finden Sie unter Schritt 5. 

     ![Liste der Verwaltungsgruppen mit Sicherheitsgruppenrolle](../../media/LRS_LRSFullAccessAdminGroup.png)

5. Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSPowerUserAdminsGroup.

    Erstellen Sie die Gruppe mit dem Gruppenbereich  Global  und dem Gruppentyp  Sicherheit . SIP-aktivierten Benutzer, die dieser Gruppe hinzugefügt werden alle einschließlich Massen Verwaltung von Skype für Räume Business Portal Admin-Funktionen verwenden dürfen.

6. Fügen Sie als Mitglied der LRSSupportAdminGroup LRSFullAccessAdminGroup hinzu.

     ![LRSSupportAdminGroup-Eigenschaftenmember (Seite)](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer mit dem Namen LRSSupport. Fügen Sie diesen Benutzer zu LRSSupportAdminGroup hinzu.

     ![LRSSupportAdminGroup-Eigenschaftenmember (Seite)](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. Installieren Sie [ASP.NET MVC 4 für Visual Studio 2010 SP1 und Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).

## <a name="install-the-srs-v1-administrative-web-portal"></a>Installieren Sie das Webportal zur Verwaltung von SRS v1
<a name="Install_SRS"> </a>

Laden Sie das [Microsoft Skype Raum Systeme v1 Administrative Webportal für Skype für Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).

Wenn Sie das Webportal zur Verwaltung von SRS v1 installieren möchten, gehen Sie wie folgt vor.

1. Konfigurieren Sie die vertrauenswürdige Anwendung Port durch das folgende Cmdlet in Skype für Business Server-Verwaltungsshell ausführen:

   ```
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. Installieren Sie das Besprechungsraum-Administratorportal. Laden Sie dazu **MeetingRoomPortalInstaller.msi** herunter, und führen Sie das Programm anschließend als Administrator aus.

3. Öffnen Sie die Datei Web.config aus folgendem Speicherort:

    %Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\

4. Ändern Sie die PortalUserName in der Datei "Web.config" für den Benutzernamen, die in Schritt2 erstellt haben, klicken Sie im Abschnitt "[Konfigurieren der Umgebung für die SRS v1 Administrative Webportal](room-system-v1-administrative-web-portal.md#Config_Env)" (der empfohlene Name im Schritt ist LRSApp):

    ```
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. Da das Webportal zur Verwaltung von SRS v1 eine vertrauenswürdige Anwendung ist, müssen Sie das Kennwort bei der Portalkonfiguration nicht angeben. Wenn für diesen Benutzer nicht die lokale Registrierungsstelle, sondern eine andere Registrierungsstelle verwendet wird, müssen Sie diese für den Benutzer angeben, indem Sie folgende Zeile in die Datei Web.Config einfügen: 

   ```
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. Wenn der verwendete Port nicht der Port 5061 ist, fügen Sie folgende Zeile in die Datei Web.Config ein: 

   ```
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>Überprüfen Sie die Installation des Webportals zur Verwaltung von SRS

Wenn Sie die Installation des Webportals zur Verwaltung von SRS v1 überprüfen möchten, gehen Sie wie folgt vor.

1. Navigieren Sie auf einem Front-End-Server zur folgenden URL:

    https://\<Fe-Server\>/lrs

    Sie sollten keine Fehler sehen (siehe folgende Abbildung):

     ![Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortalSignIn.png)

2. Wenn Sie keine Fehler sehen, versuchen Sie, über einen anderen Computer in der Topologie auf die folgende URL zuzugreifen:

    https://\<Fe-Server\>/lrs

    Um die Seite zu öffnen, müssen Sie die DNS-Datensätze hinzufügen, wie unter "[DNS-Einträge für die automatische Clientanmeldung erforderlich](https://go.microsoft.com/fwlink/p/?LinkId=318056)."

## <a name="use-the-srs-administrative-web-portal"></a>Verwenden Sie das Webportal zur Verwaltung von SRS
<a name="Use_Portal"> </a>

Nach der Bereitstellung von SRS auf dem Server können Sie den Status aller SRS-Räume überprüfen, indem Sie sich von einem Browser beim Webportal für die Verwaltung von SRS v1 anmelden.

### <a name="sign-in"></a>Anmelden

1. Navigieren Sie zu der folgenden URL:

    https://\<Fe-Server\>/lrs

2. Geben Sie die Anmeldeinformationen für das LRSSupport-Konto oder ein Konto ein, das der Sicherheitsgruppe LRSSupportAdminGroup hinzugefügt wurde.

![Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>Übersichtsseite für das Webportal für die Verwaltung von SRS

Die Übersichtsseite stellt die folgenden Informationen für alle SRS-Räume bereit, die auf dem Server bereitgestellt werden:

- **Tag** Der benutzerdefinierte Name, den der Administrator auf dem Raum ermöglicht. Das Tag kann im Portal festgelegt werden, indem Sie auf den Raumnamen klicken.

- **Integrität** Den Status des Raums, die von der aggregierte Integritätsstatus Raum abgeleitet wird der Abschnitt Integrität von der Seite Einstellungen für Raum angezeigt wird.

- **Nächsten Besprechung** Datum und Uhrzeit der nächsten Besprechung geplant ist.

- **SRS Version, Hersteller, Modell** Diese Werte werden in SRS voreinstellen. Je nach Hersteller können diese Felder auch leer sein.

- **Letzte Aktualisierung** Zeigt das letzte Mal die Webseite aktualisiert wurde.

![Zusammenfassungsansicht für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> Klicken Sie im Menü Bulk Management wird nur angezeigt, wenn Sie Mitglied der Sicherheitsgruppe LRSPowerUserAdminsGroup sind.

### <a name="srs-room-information"></a>SRS-Rauminformationen

Im Abschnitt zu den Rauminformationen des Portals können Sie individuelle SRS-Räume anzeigen und konfigurieren. Hier finden Sie vier Abschnitte zu Einstellungen, Details, Protokollierung und Integrität.

#### <a name="settings"></a>Einstellungen

Im Abschnitt zu den Einstellungen können Sie das Kennwort, das Tag für den Raum und die Standardlautstärke für den Raum festlegen. Wenn Sie diese Einstellungen konfigurieren, werden die Änderungen erst repliziert, nachdem Sie die SRS-Konsole neu gestartet haben. Ihnen werden nur die System-Updates-Einstellungen für SRS-Geräte angezeigt, die Version 15.12 oder höher verwenden.

![Einstellungen für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>Details

Im Detailbereich enthält eine schreibgeschützte Zusammenfassung der Einstellungen für den SRS Raum sowie: der Zeitpunkt der letzten Aktualisierung; nächsten Besprechung; zuletzt aktualisiert, Wartung und Kalibrierung; Standard Lautsprecher und Mikrofon sowie Rufton; Version. SIP-URI; die Anzahl der Bildschirme und Details zu jedem Bildschirm; Status und Aktivität.

![Detailansicht für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>Problembehandlung

Im Abschnitt zur Problembehandlung können Sie remote Protokolle erfassen und sie an einem angegebenen Standort speichern. Sie können außerdem die SRS-Konsole (SRS-Benutzeroberfläche) oder das gesamte System neu starten. Stellen Sie zur Erfassung von Protokollen einen Ordnerpfad im angegebenen Format bereit und vergewissern Sie sich, dass der Ordner über Schreibberechtigungen für das SRS-Computerkonto verfügt. Bei einer sehr umfangreichen Protokollgröße kann es bis zu 5 Minuten dauern, bis der Vorgang zur Erfassung der Protokolle abgeschlossen ist. Sie erhalten den aktuellen Status, wenn Sie die Seite aktualisieren.

#### <a name="health"></a>Integrität

Bereich "Health" bietet eine visuelle Darstellung der die Integrität der Skype für Business Server-Verbindung, Audiogerät, Videogerät, Resiliency Zustand und Bildschirm Gerät.

![Integrität für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>Weitere Hinweise zum Webportal für die Verwaltung

> [!NOTE]
>  Ändert sich die Einstellung werden angewendet, wenn das System SRS .> neu gestartet ist, wenn das Kontokennwort LRSApp abläuft, Sie werden nicht den Status der Chatrooms anzeigen. Konfigurieren Sie das Kontokennwort LRSAppuser, sodass es nie abläuft, oder müssen Sie unbedingt das Kennwort aktualisieren, wenn es in der Nähe der SRS administrative Expiration.>, dass nur lokale Bereitstellungen Webportal geführt wird.

### <a name="bulk-management"></a>Massenverwaltung 

Die Massenverwaltung von SRS-Räumen ist eine Funktion, die für fortgeschrittene IT-Administratoren entwickelt wurde, um den Workflow zu vereinfachen und durch ein zeitsparendes praktisches Tool die Remote-Verwaltung mehrerer Räume in Form eines Massenvorgangs zu ermöglichen.

Um diese Funktion anzuzeigen, muss der Benutzer als ein Mitglied der besonderen Sicherheitsgruppe **LRSPowerUserAdminsGroup** eingerichtet sein.  

Die Anzahl der für die Massenverwaltung auswählbaren SRS-Räume ist nicht begrenzt. Sie können jedoch immer nur einen Massenverwaltungsvorgang durchführen.

Wählen Sie zum Durchführen eines Massenverwaltungsvorgangs die Räume, die Sie überwachen möchten, und klicken sie auf das Massenverwaltungsmenü. 

### <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Warum anmelden kann nicht Bereiche der administrativen Webportal?

Beim Öffnen https://localhost/lrs, können die Anmeldeseite angezeigt, doch wenn Sie in Ihre Anmeldeinformationen eingeben, Sie können sich nicht anmelden. In diesem Fall müssen Sie öffnen https://FQDNofFEserver/SRS zur Anmeldung bei des administrative Webportals.

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>Warum wird angezeigt nicht SRS v1 in den administrativen Webportal?

- Stellen Sie sicher, dass Sie SRS-Konten in Ihrer Bereitstellung haben und diese nach den Empfehlungen für die Bereitstellung des Webportals für die SRS-Verwaltung erstellt werden. Stellen Sie sicher, dass die SRS-Konten über Enable-CsMeetingRoom, nicht Enable-CsUser, bei der Skype für Business Server bereitgestellt werden.

- Wenn Sie SRS Konten erstellt haben und die Konten in administrative Webportal wird nicht angezeigt, sammeln Sie die Serverprotokolle mithilfe der Skype für Business Server-Protokollierungstool mit der **MeetingPortal** Komponente ausgewählt, und senden Sie diese dann an den SRS Supportmitarbeiter.

- Wenn Sie SRS-Konten erstellt haben und die Konten im Webportal für die Verwaltung nicht sehen können, erfassen Sie die Clientprotokolle unter Verwendung von Fiddler, kopieren Sie das Konsolenprotokoll aus den Browserentwicklungstools und senden Sie diese dann an Ihren SRS-Supportkontakt. Sie können außerdem den Wert für die Verfolgungsstufe in der Datei Web.Confi ändern, um ein ausführliches Protokoll zu erhalten.

  ```
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>Warum wird angezeigt den Status der SRS in den administrativen Webportal nicht?

- Stellen Sie sicher, dass für das LRSApp-Benutzerkonto SIP aktiviert ist.

- Wenn Sie immer noch Probleme auftreten, sammeln Sie die Datei **Trace.log** im System SRS aus D:\Tracing\LRSAdminLogs\, und senden Sie sie an den SRS-Supportmitarbeiter.

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>Warum wird angezeigt nicht die Massen Management Menüs für SRS in den administrativen Webportal?

Stellen Sie sicher, dass das Benutzerkonto LRSApp SIP aktiviert ist, und Teil der Sicherheitsgruppe LRSPowerUserAdminsGroup ist.

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>Funktioniert das Webportal SRS v1 administrative mit Microsoft-Teams Räumen?

Nein.


