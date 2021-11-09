---
title: Bereitstellen des Webportals für die Verwaltung von SRS v1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Das Skype for Business Server Skype Verwaltungswebportal für Raumsysteme v1 (SRS v1, vormals Lync Room System) ist ein Webportal, mit dem Organisationen ihre Skype Room Systems-Konferenzräume verwalten können. Administratoren können das Webportal zur Verwaltung von SRS v1 verwenden, um die Geräteintegrität zu überwachen, z. B. durch Überwachen von Audio-/Videogeräten. Mit diesem Portal können Administratoren Diagnoseinformationen remote sammeln, um die Integrität von Konferenzräumen zu überwachen.
ms.openlocfilehash: c25671717db51af880bd4b7e2700bb9e795f2790
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843968"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Bereitstellen des Webportals für die Verwaltung von SRS v1 in Skype for Business Server

Das Skype for Business Server Skype Verwaltungswebportal für Raumsysteme v1 (SRS v1, vormals Lync Room System) ist ein Webportal, mit dem Organisationen ihre Skype Room Systems-Konferenzräume verwalten können. Administratoren können das Webportal zur Verwaltung von SRS v1 verwenden, um die Geräteintegrität zu überwachen, z. B. durch Überwachen von Audio-/Videogeräten. Mit diesem Portal können Administratoren Diagnoseinformationen remote sammeln, um die Integrität von Konferenzräumen zu überwachen.

Um dieses Feature zu verwenden, muss das Webportal zur Verwaltung von SRS v1 auf jedem Skype for Business Server Front-End-Server bereitgestellt werden. Dieses Handbuch enthält Anweisungen für Administratoren zum Installieren und Konfigurieren des Webportals für die Verwaltung von SRS. Sie richtet sich an Administratoren, die über Kenntnisse in Skype for Business Server Verwaltung verfügen und über Administratorrechte zum Ändern der Skype for Business Server Topologie verfügen.

Nachdem das Webportal zur Verwaltung von SRS v1 auf dem Server bereitgestellt wurde, können Administratoren den Status von SRS v1-Geräten überprüfen, indem sie sich von ihren eigenen Computern oder Laptops an der Website anmelden.

> [!IMPORTANT]
> Laden Sie das [Microsoft Skype Room Systems v1 Administrative Web Portal für Skype for Business Server 2015 herunter.](https://www.microsoft.com/download/details.aspx?id=46906)

Inhalt dieses Themas:

- [Konfigurieren Ihrer Umgebung für das Webportal für die Verwaltung von SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)

- [Installieren des Webportals für die Verwaltung von SRS v1](room-system-v1-administrative-web-portal.md#Install_SRS)

- [Verwenden des Webportals für die Verwaltung von SRS](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>Konfigurieren Ihrer Umgebung für das Webportal für die Verwaltung von SRS v1
<a name="Config_Env"> </a>

Um das Webportal zur Verwaltung von SRS v1 zu verwenden, müssen Sie die folgenden Voraussetzungen installieren oder konfigurieren.

> [!IMPORTANT]
> Wenn der Server mit Kerberos- und NTLM-Authentifizierung konfiguriert ist und SRS auf einem Computer ausgeführt wird, der nicht mit der Domäne verbunden ist, schlägt die Kerberos-Authentifizierung fehl, und der Benutzer sieht den Status von SRS im Verwaltungsportal nicht. Um dieses Problem zu beheben, konfigurieren Sie den Server mit NTLM-Authentifizierung oder ntlm- und TLS-DSK-Authentifizierung (ohne Kerberos), oder verknüpfen Sie den SRS-Computer mit der Domäne.

1. Installieren Sie Skype for Business Server kumulativen Updates in der Skype for Business Server Topologie.

    Informationen zum Abrufen des Updates oder zum Lieferumfang finden Sie unter [Updates für Skype for Business Server 2015.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)

2. Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer.

    Das Webportal zur Verwaltung von SRS v1 verwendet diese Anmeldeinformationen, um Informationen von Skype for Business Server abzufragen. Der Benutzername in den beispielen ist LRSApp.

3. Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen "LRSSupportAdminGroup".

    Erstellen Sie die Gruppe mit "Gruppenbereich" als "Global" und "Gruppentyp als Sicherheit". SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, die Liste der Räume anzuzeigen und bestimmte Befehle auszuführen, z. B. das Sammeln von Protokollen.

4. Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSFullAccessAdminGroup.

    Erstellen Sie die Gruppe mit dem Gruppenbereich "Global" und dem Gruppentyp "Security.SIP", die dieser Gruppe hinzugefügt werden, berechtigt sind, alle Verwaltungsportalfunktionen in einem einzelnen Skype Raum zu verwenden. Informationen zur Unterstützung der Massenverwaltung von Skype Chatrooms finden Sie in Schritt 5.

     ![Liste der Administratorgruppen mit Sicherheitsgruppenrolle.](../../media/LRS_LRSFullAccessAdminGroup.png)

5. Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSPowerUserAdminsGroup.

    Erstellen Sie die Gruppe mit "Gruppenbereich" als "Global" und "Gruppentyp als Sicherheit". SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, alle Funktionen des Verwaltungsportals zu verwenden, einschließlich der Massenverwaltung von Skype for Business Chatrooms.

6. Fügen Sie LRSFullAccessAdminGroup als Mitglied von LRSSupportAdminGroup hinzu.

     ![Seite "LRSSupportAdminGroup Properties Members".](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer mit dem Namen LRSSupport. Fügen Sie diesen Benutzer zu LRSSupportAdminGroup hinzu.

     ![Seite "LRSSupportAdminGroup Properties Members".](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. Installieren Sie [ASP.NET MVC 4 für Visual Studio 2010 SP1 und Visual Web Developer 2010 SP1.](https://go.microsoft.com/fwlink/p/?LinkId=323967)

## <a name="install-the-srs-v1-administrative-web-portal"></a>Installieren des Webportals für die Verwaltung von SRS v1
<a name="Install_SRS"> </a>

Laden Sie das [Microsoft Skype Room Systems v1 Administrative Web Portal für Skype for Business Server 2015 herunter.](https://www.microsoft.com/download/details.aspx?id=46906)

Führen Sie die folgenden Schritte aus, um das Webportal für die Verwaltung von SRS v1 zu installieren.

1. Konfigurieren Sie den Port für vertrauenswürdige Anwendungen, indem Sie das folgende Cmdlet in Skype for Business Server Verwaltungsshell ausführen:

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. Laden Sie zum Installieren des Besprechungsraum Portals **MeetingRoomPortalInstaller.msi** herunter, und führen Sie es dann als Administrator aus.

3. Öffnen Sie die Web.config-Datei am folgenden Speicherort:

    %Program Files%\Skype for Business Server 2015\Web Components\Besprechungsraum Portal\Int\Handler\

4. Ändern Sie in der Web.Config Datei den PortalUserName in den Benutzernamen, der in Schritt 2 unter dem Abschnitt "[Konfigurieren Ihrer Umgebung für das Webportal für die Verwaltung von SRS v1"](room-system-v1-administrative-web-portal.md#Config_Env)erstellt wurde (der empfohlene Name im Schritt lautet LRSApp):

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. Da das SRS v1-Verwaltungsportal eine vertrauenswürdige Anwendung ist, müssen Sie das Kennwort nicht in der Portalkonfiguration angeben. Wenn dieser Benutzer eine andere Registrierungsstelle als die lokale Registrierungsstelle verwendet, müssen Sie die Registrierungsstelle dafür angeben, indem Sie die folgende Zeile in der datei Web.Config hinzufügen:

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. Wenn der verwendete Port nicht 5061 ist, fügen Sie die folgende Zeile in der datei Web.Config hinzu:

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>Überprüfen der Installation des Webportals für die Verwaltung von SRS

Gehen Sie folgendermaßen vor, um die Installation des Webportals für die Verwaltung von SRS v1 zu überprüfen:

1. Navigieren Sie auf einem Front-End-Server zur folgenden URL:

    https:// \<fe-server\> /lrs

    Es sollten keine Fehler angezeigt werden, wie in der folgenden Abbildung dargestellt:

     ![Anmeldebildschirm des Lync Room System-Verwaltungsportals.](../../media/LRS_AdminPortalSignIn.png)

2. Wenn keine Fehler angezeigt werden, versuchen Sie, von einem anderen Computer in der Topologie aus auf die folgende URL zuzugreifen:

    https:// \<fe-server\> /lrs

    Um auf die Seite zuzugreifen, müssen Sie die DNS-Einträge wie unter["Erforderliche DNS-Einträge für die automatische Clientanmeldung"](/previous-versions/office/communications-server/bb663700(v=office.12))beschrieben hinzufügen.

## <a name="use-the-srs-administrative-web-portal"></a>Verwenden des Webportals für die Verwaltung von SRS
<a name="Use_Portal"> </a>

Nachdem Sie SRS auf dem Server bereitgestellt haben, können Sie den Status aller SRS-Räume überprüfen, indem Sie sich über einen Browser beim Webportal für die Verwaltung von SRS v1 anmelden.

### <a name="sign-in"></a>Anmelden

1. Navigieren Sie zur folgenden URL:

    https:// \<fe-server\> /lrs

2. Geben Sie die Anmeldeinformationen für das LRSSupport-Konto oder ein Konto ein, das der Sicherheitsgruppe "LRSSupportAdminGroup" hinzugefügt wurde.

![Anmeldebildschirm des Lync Room System-Verwaltungsportals.](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>Zusammenfassungsseite des SRS-Verwaltungswebportals

Die Zusammenfassungsseite enthält die folgenden Informationen für alle SRS-Räume, die auf dem Server bereitgestellt werden:

- **Tag** Der benutzerdefinierte Name, den der Administrator dem Raum gibt. Das Tag kann im Portal durch Klicken auf den Raumnamen festgelegt werden.

- **Integrität** Der Integritätsstatus des Raums, der vom Aggregierten Integritätsstatus des Raums abgeleitet wird, der im Abschnitt "Integrität" der Seite "Raum Einstellungen" angezeigt wird.

- **Nächste Besprechung** Das Datum und die Uhrzeit, zu der die nächste Besprechung geplant ist.

- **SRS-Version, Hersteller, Modell** Diese Werte sind in SRS voreingestellt. Je nach Hersteller bleiben diese Felder möglicherweise leer.

- **Letzte Aktualisierung** Zeigt an, wie die Webseite das letzte Mal aktualisiert wurde.

![Lync Room System Admin Portal Summary View.](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> Das Menü "Massenverwaltung" wird nur angezeigt, wenn Sie Teil der Sicherheitsgruppe "LRSPowerUserAdminsGroup" sind.

### <a name="srs-room-information"></a>SRS-Rauminformationen

Im Abschnitt "Rauminformationen" des Portals können Sie einzelne SRS-Räume anzeigen und konfigurieren. Es enthält vier Abschnitte: Einstellungen, Details, Protokollierung und Integrität.

#### <a name="settings"></a>Einstellungen

Im Abschnitt Einstellungen können Sie das Kennwort, das Raumtag und die Standardlautstärke für den Raum festlegen. Wenn Sie diese Einstellungen konfigurieren, werden die Änderungen erst repliziert, nachdem Sie die SRS-Konsole neu gestartet haben. Es werden nur Systemupdates-Einstellungen für SRS-Geräte mit Version 15.12 und höher angezeigt.

![Chatroom Einstellungen des Lync Room System-Verwaltungsportals.](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>Details

Der Abschnitt "Details" enthält eine schreibgeschützte Zusammenfassung der Einstellungen des SRS-Raums, einschließlich: Zeitpunkt der letzten Aktualisierung; nächste Besprechung; letzte Updates, Wartung und Kalibrierung; Standardeinstellungen für Lautsprecher, Mikrofon und Ringer; Version; SIP-URI; Anzahl der Bildschirme und Details zu den einzelnen Bildschirmen; Status und Aktivität.

![Detailansicht des Lync Room System-Verwaltungsportals.](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>Problembehandlung

Der Abschnitt "Problembehandlung" kann verwendet werden, um Protokolle remote zu erfassen und an einem angegebenen Speicherort zu speichern. Sie können auch die SRS-Konsole (SRS-Benutzeroberfläche) oder das gesamte System neu starten. Geben Sie zum Sammeln von Protokollen einen Ordnerpfad im angegebenen Format an, und stellen Sie sicher, dass dem Ordner Schreibberechtigungen für das SRS-Computerkonto erteilt wurden. Wenn die Protokollgröße zu groß ist, kann es bis zu 5 Minuten dauern, bis die Erfassung von Protokollen abgeschlossen ist. Wenn Sie die Seite aktualisieren, erhalten Sie den neuesten Status.

#### <a name="health"></a>Health

Der Abschnitt "Integrität" gibt einen visuellen Hinweis auf den Zustand der Skype for Business Server Verbindung, des Audiogeräts, des Videogeräts, des Ausfallsicherheitszustands und des Bildschirmgeräts.

![Lync Room System Admin Portal Room Health.](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>Zusätzliche Hinweise zum Webportal für die Verwaltung

> [!NOTE]
>  Einstellungsänderungen werden erst angewendet, nachdem das SRS-System neu gestartet wurde.> Wenn das LRSApp-Kontokennwort abläuft, können Sie den Status der Räume nicht sehen. Konfigurieren Sie das LRSAppuser-Kontokennwort so, dass es nie abläuft, oder aktualisieren Sie das Kennwort, wenn es bald abläuft.> Das SRS-Verwaltungswebportal wird nur für lokale Bereitstellungen unterstützt.

### <a name="bulk-management"></a>Massenverwaltung

Die Massenverwaltung von SRS-Chatrooms ist ein Feature, das für fortgeschrittene IT-Administratoren entwickelt wurde, um deren Workflow zu vereinfachen und ihnen ein zeitsparendes, praktisches Tool zur remoten Verwaltung mehrerer Räume in massenweiser Weise zu ermöglichen.

Um diese Funktionalität anzuzeigen, muss der Benutzer als Mitglied der speziellen Sicherheitsgruppe **LRSPowerUserAdminsGroup** bereitgestellt werden.

Die Anzahl der SRS-Räume, die Sie für die Massenverwaltung auswählen können, ist nicht begrenzt. Sie können jedoch jeweils nur einen Massenverwaltungsvorgang ausführen.

Wählen Sie zum Ausführen eines Massenverwaltungsvorgangs die Räume aus, die Sie überwachen möchten, und klicken Sie auf das Menü "Massenverwaltung".

### <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Warum kann ich mich nicht beim Verwaltungswebportal anmelden?

Wenn Sie https://localhost/lrs öffnen, können Sie die Anmeldeseite sehen, aber wenn Sie Ihre Anmeldeinformationen eingeben, können Sie sich nicht anmelden. In diesem Fall müssen Sie sich öffnen, https://FQDNofFEserver/SRS um sich beim Verwaltungswebportal anzumelden.

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>Warum kann ich SRS v1 im Webportal für die Verwaltung nicht sehen?

- Stellen Sie sicher, dass SRS-Konten in Ihrer Bereitstellung vorhanden sind und dass sie gemäß den Bereitstellungsempfehlungen des Webportals für die Verwaltung von SRS erstellt werden. Stellen Sie sicher, dass die SRS-Konten im Skype for Business Server mit "Enable-CsMeetingRoom" und nicht mit "Enable-CsUser" bereitgestellt werden.

- Wenn Sie SRS-Konten erstellt haben und die Konten im Verwaltungswebportal nicht angezeigt werden können, erfassen Sie die Serverprotokolle mithilfe des Tools für die Skype for Business Server Protokollierung, wobei die **MeetingPortal-Komponente** ausgewählt ist, und senden Sie sie dann an Ihren SRS-Supportkontakt.

- Wenn Sie SRS-Konten erstellt haben und die Konten im Verwaltungswebportal nicht sehen können, erfassen Sie die Clientprotokolle mit Fiddler, kopieren Sie außerdem das Konsolenprotokoll aus den Browserentwicklungstools, und senden Sie sie dann an Ihren SRS-Supportkontakt. Sie können auch den Wert der Ablaufverfolgungsebene im Web.config ändern, um ein detaillierteres Protokoll zu erhalten.

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>Warum kann ich den Status von SRS nicht im Webportal für die Verwaltung anzeigen?

- Stellen Sie sicher, dass das LRSApp-Benutzerkonto SIP-aktiviert ist.

- Wenn weiterhin Probleme auftreten, erfassen Sie die Datei **Trace.log** im SRS-System von D:\Tracing\LRSAdminLogs, und senden Sie \, sie dann an Ihren SRS-Supportkontakt.

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>Warum kann ich die Massenverwaltungsmenüs für SRS nicht im Webportal für die Verwaltung anzeigen?

Stellen Sie sicher, dass das LRSApp-Benutzerkonto SIP-fähig ist und Teil der Sicherheitsgruppe "LRSPowerUserAdminsGroup" ist.

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>Funktioniert das Webportal zur Verwaltung von SRS v1 mit Microsoft Teams-Räume?

Nein.