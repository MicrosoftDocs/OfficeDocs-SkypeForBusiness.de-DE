---
title: Bereitstellen des Administrator-Web-Portals für SRS V1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Der Skype for Business-Server Skype Room Systems v1 (SRS v1, ehemals lync Room System) administratives Webportal ist ein Webportal, das Organisationen verwenden können, um Ihre Skype Room Systems-Konferenzräume zu verwalten. Administratoren können das administrative Web Portal für SRS v1 verwenden, um die Geräte Integrität zu überwachen, beispielsweisedurch überwachen von Audio/Video-Geräten. Mit diesem Portal können Administratoren über Remoteverbindungen Diagnoseinformationen sammeln, um die Konferenzraumintegrität zu überwachen.
ms.openlocfilehash: 558baac64bdb1e21ed710cb4dafb063ce75a62de
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768518"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Bereitstellen des Administrator-Web-Portals für SRS V1 in Skype for Business Server

Der Skype for Business-Server Skype Room Systems v1 (SRS v1, ehemals lync Room System) administratives Webportal ist ein Webportal, das Organisationen verwenden können, um Ihre Skype Room Systems-Konferenzräume zu verwalten. Administratoren können das administrative Web Portal für SRS v1 verwenden, um die Geräte Integrität zu überwachen, beispielsweisedurch überwachen von Audio/Video-Geräten. Mit diesem Portal können Administratoren über Remoteverbindungen Diagnoseinformationen sammeln, um die Konferenzraumintegrität zu überwachen.

Um dieses Feature verwenden zu können, muss das administrative SRS v1-Webportal auf jedem Front-End-Server von Skype for Business Server bereitgestellt werden. Dieses Handbuch enthält Anweisungen für Administratoren, wie das Webportal zur Verwaltung von SRS installiert und konfiguriert wird. Sie ist für Administratoren vorgesehen, die über Kenntnisse der Skype for Business Server-Verwaltung verfügen und über Administratorrechte verfügen, um die Skype for Business Server-Topologie zu ändern.

Nachdem das administrative SRS v1-Webportal auf dem Server bereitgestellt wurde, können Administratoren den Status SRS v1-Geräte überprüfen, indem Sie sich auf Ihren eigenen Computern oder Laptops bei der Website anmelden.

> [!IMPORTANT]
> Laden Sie das [Microsoft Skype Room Systems v1 Administrative Web-Portal für Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906)herunter.

In diesem Thema:

- [Konfigurieren Sie Ihre Umgebung für das Webportal zur Verwaltung von SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)

- [Installieren Sie das Webportal zur Verwaltung von SRS v1](room-system-v1-administrative-web-portal.md#Install_SRS)

- [Verwenden Sie das Webportal zur Verwaltung von SRS](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>Konfigurieren Sie Ihre Umgebung für das Webportal zur Verwaltung von SRS v1
<a name="Config_Env"> </a>

Zur Nutzung des Webportals für die Verwaltung des SRS v1 müssen Sie die folgenden Voraussetzungen installieren oder konfigurieren.

> [!IMPORTANT]
> Wenn für den Server sowohl Kerberos- als auch die NTLM-Authentifizerung konfiguriert wurde und SRS auf einem Computer ausgeführt wird, der nicht Teil der Domäne ist, schlägt die Kerberos-Authentifizierung fehl und dem Benutzer wird der SRS-Status im Verwaltungsportal nicht angezeigt. Sie können dieses Problem lösen, indem Sie entweder die NTLM-Authentifizierung bzw. die NTLM- und TLS-DSK-Authentifizierung (ohne Kerberos) konfigurieren oder mit dem SRS-Computer der Domäne beitreten.

1. Installieren Sie die kumulierten Updates für Skype for Business Server in der Skype for Business Server-Topologie.

    Wenn Sie das Update erhalten oder sehen möchten, was darin enthalten ist, lesen Sie [Updates für Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).

2. Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer.

    Das administrative Web Portal für SRS v1 verwendet diese Anmeldeinformationen, um Informationen von Skype for Business Server abzufragen. Der in den Beispielen verwendete Benutzername lautet LRSApp.

3. Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSSupportAdminGroup.

    Erstellen Sie die Gruppe mit dem Gruppenbereich  Global  und dem Gruppentyp  Sicherheit . SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, die Liste der Räume anzuzeigen und bestimmte Befehle auszuführen, wie das Speichern von Protokollen.

4. Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSFullAccessAdminGroup. 

    Erstellen Sie die Gruppe mit dem Gruppenbereich „Global“ und dem Gruppentyp „Sicherheit“. SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, alle Funktionen des Verwaltungsportals für einen einzelnen Skype-Raum zu nutzen. Um Unterstützung für die Massenverwaltung von Skype-Räumen zu erhalten, finden Sie unter Schritt 5. 

     ![Liste der Verwaltungsgruppen mit Sicherheitsgruppenrolle](../../media/LRS_LRSFullAccessAdminGroup.png)

5. Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSPowerUserAdminsGroup.

    Erstellen Sie die Gruppe mit dem Gruppenbereich  Global  und dem Gruppentyp  Sicherheit . SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, alle Funktionen des Administrator Portals einschließlich der Massenverwaltung von Skype for Business-Räumen zu verwenden.

6. Fügen Sie LRSFullAccessAdminGroup als Mitglied von LRSSupportAdminGroup hinzu.

     ![LRSSupportAdminGroup-Eigenschaftenmember (Seite)](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer mit dem Namen LRSSupport. Fügen Sie diesen Benutzer zu LRSSupportAdminGroup hinzu.

     ![LRSSupportAdminGroup-Eigenschaftenmember (Seite)](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. Installieren Sie [ASP.NET MVC 4 für Visual Studio 2010 SP1 und Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).

## <a name="install-the-srs-v1-administrative-web-portal"></a>Installieren Sie das Webportal zur Verwaltung von SRS v1
<a name="Install_SRS"> </a>

Laden Sie das [Microsoft Skype Room Systems v1 Administrative Web-Portal für Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906)herunter.

Wenn Sie das Webportal zur Verwaltung von SRS v1 installieren möchten, gehen Sie wie folgt vor.

1. Konfigurieren Sie den Port für vertrauenswürdige Anwendungen, indem Sie das folgende Cmdlet in der Skype for Business Server-Verwaltungsshell ausführen:

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. Installieren Sie das Besprechungsraum-Administratorportal. Laden Sie dazu **MeetingRoomPortalInstaller.msi** herunter, und führen Sie das Programm anschließend als Administrator aus.

3. Öffnen Sie die Datei Web.config aus folgendem Speicherort:

    % Program Files%\Skype for Business Server 2015 \ Web Components\Meeting Room Portal\Int\Handler\

4. Ändern Sie in der Datei Web. config die PortalUserName in den in Schritt 2 erstellten Benutzernamen unter dem Abschnitt "[Konfigurieren der Umgebung für das administrative Web-Portal für SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)" (der empfohlene Name im Schritt lautet LRSApp):

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. Da das Webportal zur Verwaltung von SRS v1 eine vertrauenswürdige Anwendung ist, müssen Sie das Kennwort bei der Portalkonfiguration nicht angeben. Wenn für diesen Benutzer nicht die lokale Registrierungsstelle, sondern eine andere Registrierungsstelle verwendet wird, müssen Sie diese für den Benutzer angeben, indem Sie folgende Zeile in die Datei Web.Config einfügen: 

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. Wenn der verwendete Port nicht der Port 5061 ist, fügen Sie folgende Zeile in die Datei Web.Config ein: 

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>Überprüfen Sie die Installation des Webportals zur Verwaltung von SRS

Wenn Sie die Installation des Webportals zur Verwaltung von SRS v1 überprüfen möchten, gehen Sie wie folgt vor.

1. Navigieren Sie auf einem Front-End-Server zur folgenden URL:

    https://\<FE-Server\>/LRS

    Sie sollten keine Fehler sehen (siehe folgende Abbildung):

     ![Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortalSignIn.png)

2. Wenn Sie keine Fehler sehen, versuchen Sie, über einen anderen Computer in der Topologie auf die folgende URL zuzugreifen:

    https://\<FE-Server\>/LRS

    Wenn Sie auf die Seite zugreifen möchten, müssen Sie die DNS-Einträge hinzufügen, wie unter "[erforderliche DNS-Einträge für die automatische Client Anmeldung](https://go.microsoft.com/fwlink/p/?LinkId=318056)" beschrieben ist.

## <a name="use-the-srs-administrative-web-portal"></a>Verwenden Sie das Webportal zur Verwaltung von SRS
<a name="Use_Portal"> </a>

Nach der Bereitstellung von SRS auf dem Server können Sie den Status aller SRS-Räume überprüfen, indem Sie sich von einem Browser beim Webportal für die Verwaltung von SRS v1 anmelden.

### <a name="sign-in"></a>Anmelden

1. Navigieren Sie zu der folgenden URL:

    https://\<FE-Server\>/LRS

2. Geben Sie die Anmeldeinformationen für das LRSSupport-Konto oder ein Konto ein, das der Sicherheitsgruppe LRSSupportAdminGroup hinzugefügt wurde.

![Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>Übersichtsseite für das Webportal für die Verwaltung von SRS

Die Übersichtsseite stellt die folgenden Informationen für alle SRS-Räume bereit, die auf dem Server bereitgestellt werden:

- - **Tag** Der benutzerdefinierte Name, den der Administrator dem Chatroom übergibt. Das Tag kann im Portal festgelegt werden, indem Sie auf den Raumnamen klicken.

- **Gesundheit** Der Integritätsstatus des Raums, der aus dem Aggregat Integritätsstatus des Raums abgeleitet wird, der im Abschnitt "Gesundheit" auf der Seite "Raumeinstellungen" angezeigt wird.

- **Nächste Besprechung** Das Datum und die Uhrzeit, zu der die nächste Besprechung geplant ist.

- **SRS-Version, Hersteller, Modell** Diese Werte werden in SRS voreingestellt. Je nach Hersteller können diese Felder auch leer sein.

- **Letzte Aktualisierung** Zeigt den Zeitpunkt an, zu dem die Webseite zuletzt aktualisiert wurde.

![Zusammenfassungsansicht für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> Wenn Sie zur LRSPowerUserAdminsGroup-Sicherheitsgruppe gehören, wird das Menü Massenverwaltung nur angezeigt.

### <a name="srs-room-information"></a>SRS-Rauminformationen

Im Abschnitt zu den Rauminformationen des Portals können Sie individuelle SRS-Räume anzeigen und konfigurieren. Hier finden Sie vier Abschnitte zu Einstellungen, Details, Protokollierung und Integrität.

#### <a name="settings"></a>Einstellungen

Im Abschnitt zu den Einstellungen können Sie das Kennwort, das Tag für den Raum und die Standardlautstärke für den Raum festlegen. Wenn Sie diese Einstellungen konfigurieren, werden die Änderungen erst repliziert, nachdem Sie die SRS-Konsole neu gestartet haben. Ihnen werden nur die System-Updates-Einstellungen für SRS-Geräte angezeigt, die Version 15.12 oder höher verwenden.

![Einstellungen für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>Details

Der Abschnitt Details enthält eine schreibgeschützte Zusammenfassung der Einstellungen des SRS-Raums, einschließlich: die Uhrzeit der letzten Aktualisierung. nächste Besprechung; Letzte Updates, Wartung und Kalibrierung; Standardeinstellungen für Lautsprecher, Mikrofon und Klingelton Version SIP-URI; Anzahl der Bildschirme und Details zu jedem Bildschirm; Status und Aktivität.

![Detailansicht für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>Problembehandlung

Im Abschnitt zur Problembehandlung können Sie remote Protokolle erfassen und sie an einem angegebenen Standort speichern. Sie können außerdem die SRS-Konsole (SRS-Benutzeroberfläche) oder das gesamte System neu starten. Stellen Sie zur Erfassung von Protokollen einen Ordnerpfad im angegebenen Format bereit und vergewissern Sie sich, dass der Ordner über Schreibberechtigungen für das SRS-Computerkonto verfügt. Bei einer sehr umfangreichen Protokollgröße kann es bis zu 5 Minuten dauern, bis der Vorgang zur Erfassung der Protokolle abgeschlossen ist. Sie erhalten den aktuellen Status, wenn Sie die Seite aktualisieren.

#### <a name="health"></a>Integrität

Der Abschnitt "Gesundheit" bietet eine visuelle Anzeige des Zustands der Skype for Business-Server Verbindung, des Audiogeräts, des Videogeräts, des Stabilitäts Status und des Bildschirmgeräts.

![Integrität für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>Weitere Hinweise zum Webportal für die Verwaltung

> [!NOTE]
>  Das Festlegen von Änderungen wird erst nach einem Neustart des SRS-Systems übernommen. #a0 Wenn das LRSApp-Kontokennwort abläuft, können Sie den Status der Räume nicht sehen. Konfigurieren Sie das Kennwort für das LRSAppuser-Konto so, dass es nie abläuft, oder aktualisieren Sie das Kennwort, wenn es nahezu abgelaufen ist. #a0 das SRS-Verwaltungs Webportal wird nur für lokale Bereitstellungen unterstützt.

### <a name="bulk-management"></a>Massenverwaltung 

Die Massenverwaltung von SRS-Räumen ist eine Funktion, die für fortgeschrittene IT-Administratoren entwickelt wurde, um den Workflow zu vereinfachen und durch ein zeitsparendes praktisches Tool die Remote-Verwaltung mehrerer Räume in Form eines Massenvorgangs zu ermöglichen.

Um diese Funktion anzuzeigen, muss der Benutzer als ein Mitglied der besonderen Sicherheitsgruppe **LRSPowerUserAdminsGroup** eingerichtet sein.  

Die Anzahl der für die Massenverwaltung auswählbaren SRS-Räume ist nicht begrenzt. Sie können jedoch immer nur einen Massenverwaltungsvorgang durchführen.

Wählen Sie zum Durchführen eines Massenverwaltungsvorgangs die Räume, die Sie überwachen möchten, und klicken sie auf das Massenverwaltungsmenü. 

### <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Warum kann ich mich nicht beim administrativen Webportal anmelden?

Wenn Sie öffnen https://localhost/lrs, können Sie die Anmeldeseite sehen, aber wenn Sie Ihre Anmeldeinformationen eingeben, können Sie sich nicht anmelden. In diesem Fall müssen Sie die Anmeldung https://FQDNofFEserver/SRS beim Administrator-Webportal öffnen.

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>Warum kann ich SRS v1 nicht im Administrator-Webportal sehen?

- Stellen Sie sicher, dass Sie SRS-Konten in Ihrer Bereitstellung haben und diese nach den Empfehlungen für die Bereitstellung des Webportals für die SRS-Verwaltung erstellt werden. Stellen Sie sicher, dass die SRS-Konten mithilfe von enable-CsMeetingRoom, nicht enable-CsUser, auf dem Skype for Business-Server bereitgestellt werden.

- Wenn Sie SRS-Konten erstellt haben und die Konten im administrativen Webportal nicht sehen können, sammeln Sie die Serverprotokolle mithilfe des Skype for Business Server-Protokollierungstools, wobei die **MeetingPortal** -Komponente ausgewählt ist, und senden Sie Sie dann an Ihren SRS-Support Kontakt.

- Wenn Sie SRS-Konten erstellt haben und die Konten im Webportal für die Verwaltung nicht sehen können, erfassen Sie die Clientprotokolle unter Verwendung von Fiddler, kopieren Sie das Konsolenprotokoll aus den Browserentwicklungstools und senden Sie diese dann an Ihren SRS-Supportkontakt. Sie können außerdem den Wert für die Verfolgungsstufe in der Datei Web.Confi ändern, um ein ausführliches Protokoll zu erhalten.

  ```xml
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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>Warum wird der Status von SRS im Administrator-Webportal nicht angezeigt?

- Stellen Sie sicher, dass für das LRSApp-Benutzerkonto SIP aktiviert ist.

- Wenn weiterhin Probleme auftreten, sammeln Sie die Datei **Trace. log** im SRS-System von D:\Tracing\LRSAdminLogs\, , und senden Sie Sie dann an Ihren SRS-Support Kontakt.

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>Warum werden die Menüs für die Massenverwaltung für SRS im administrativen Webportal nicht angezeigt?

Stellen Sie sicher, dass das LRSApp-Benutzerkonto SIP-fähig ist und Teil der LRSPowerUserAdminsGroup-Sicherheitsgruppe ist.

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>Funktioniert das administrative SRS v1-Webportal mit Microsoft Teams-Räumen?

Nein.


