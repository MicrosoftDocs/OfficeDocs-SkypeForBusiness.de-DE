---
title: Bereitstellen des Webportals für die Verwaltung von SRS v1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Das Webportal zur Verwaltung von Skype for Business Server Skype Room Systems v1 (SRS v1, früher als Lync Room System bezeichnet) ist ein Webportal, über das Organisationen ihre Skype Room Systems-Konferenzräume verwalten können. Administratoren können das Webportal für die Verwaltung von SRS v1 verwenden, um den Gerätezustand zu überwachen, z. B. durch Überwachen von Audio-/Videogeräten. Mit diesem Portal können Administratoren Remotediagnoseinformationen sammeln, um den Zustand des Konferenzraums zu überwachen.
ms.openlocfilehash: 7d7bef99149d09ebf72c9b633370f262e535b23f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804535"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Bereitstellen des Webportals für die Verwaltung von SRS v1 in Skype for Business Server

Das Webportal zur Verwaltung von Skype for Business Server Skype Room Systems v1 (SRS v1, früher als Lync Room System bezeichnet) ist ein Webportal, über das Organisationen ihre Skype Room Systems-Konferenzräume verwalten können. Administratoren können das Webportal zur Verwaltung von SRS v1 verwenden, um die Geräteintegte zu überwachen, z. B. durch Überwachen von Audio-/Videogeräten. Mit diesem Portal können Administratoren Remotediagnoseinformationen sammeln, um den Zustand des Konferenzraums zu überwachen.

Um dieses Feature verwenden zu können, muss das Webportal für die Verwaltung von SRS v1 auf jedem Skype for Business Server-Front-End-Server bereitgestellt werden. Dieses Handbuch enthält Anweisungen für Administratoren zum Installieren und Konfigurieren des Webportals für die Verwaltung von SRS. Es richtet sich an Administratoren, die über Kenntnisse der Skype for Business Server-Verwaltung verfügen und über Administratorrechte zum Ändern der Skype for Business Server-Topologie verfügen.

Nachdem das Webportal für die Verwaltung von SRS v1 auf dem Server bereitgestellt wurde, können Administratoren den Status von SRS v1-Geräten überprüfen, indem sie sich von ihren eigenen Computern oder Laptops an der Website anmelden.

> [!IMPORTANT]
> Laden Sie das Webportal zur Verwaltung von [Microsoft Skype Room Systems v1 für Skype for Business Server 2015 herunter.](https://www.microsoft.com/download/details.aspx?id=46906)

Inhalt dieses Themas:

- [Konfigurieren Der Umgebung für das Webportal für die Verwaltung von SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)

- [Installieren des Webportals für die Verwaltung von SRS v1](room-system-v1-administrative-web-portal.md#Install_SRS)

- [Verwenden des Webportals für die Verwaltung von SRS](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>Konfigurieren Der Umgebung für das Webportal für die Verwaltung von SRS v1
<a name="Config_Env"> </a>

Um das Webportal für die Verwaltung von SRS v1 zu verwenden, müssen Sie die folgenden erforderlichen Komponenten installieren oder konfigurieren.

> [!IMPORTANT]
> Wenn der Server sowohl mit kerberos- als auch mit der NTLM-Authentifizierung konfiguriert ist und SRS auf einem Computer ausgeführt wird, der nicht mitglied der Domäne ist, kann die Kerberos-Authentifizierung nicht ausgeführt werden, und dem Benutzer wird der Status von SRS im Verwaltungsportal nicht angezeigt. Um dieses Problem zu beheben, konfigurieren Sie den Server mit der NTLM-Authentifizierung oder ntLM- und TLS-DSK-Authentifizierung (ohne Kerberos), oder schließen Sie den Computer mit SRS der Domäne an.

1. Installieren Sie kumulative Updates für Skype for Business Server in der Skype for Business Server-Topologie.

    Informationen zum Update oder zum Lieferumfang finden Sie unter [Updates für Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).

2. Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer.

    Das Webportal für die Verwaltung von SRS v1 verwendet diese Anmeldeinformationen zum Abfragen von Informationen von Skype for Business Server. Der Benutzername in den Beispielen ist LRSApp.

3. Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSSupportAdminGroup.

    Erstellen Sie die Gruppe mit dem Gruppenbereich als "Global" und dem Gruppentyp "Sicherheit". SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind autorisiert, die Liste der Räume anzuzeigen und bestimmte Befehle auszuführen, z. B. das Sammeln von Protokollen.

4. Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen "LRSFullAccessAdminGroup".

    Erstellen Sie die Gruppe mit dem Gruppenbereich "Global" und dem Gruppentyp "Sicherheit.SIP-aktivierte Benutzer", die dieser Gruppe hinzugefügt werden, sind autorisiert, alle Verwaltungsportalfunktionen in einem einzigen Skype-Raum zu verwenden. Informationen zur Unterstützung der Massenverwaltung von Skype-Chats finden Sie in Schritt 5.

     ![Liste der Administratorgruppen mit Sicherheitsgruppenrolle](../../media/LRS_LRSFullAccessAdminGroup.png)

5. Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSPowerUserAdminsGroup.

    Erstellen Sie die Gruppe mit dem Gruppenbereich als "Global" und dem Gruppentyp "Sicherheit". SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind autorisiert, alle Funktionen des Verwaltungsportals zu verwenden, einschließlich der Massenverwaltung von Skype for Business-Räumen.

6. Fügen Sie LRSFullAccessAdminGroup als Mitglied der LRSSupportAdminGroup hinzu.

     ![Seite "LRSSupportAdminGroup-Eigenschaften"](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer mit dem Namen "LRSSupport". Fügen Sie diesen Benutzer zu LRSSupportAdminGroup hinzu.

     ![Seite "LRSSupportAdminGroup-Eigenschaften"](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. Installieren [ASP.NET MVC 4 für Visual Studio 2010 SP1 und Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).

## <a name="install-the-srs-v1-administrative-web-portal"></a>Installieren des Webportals für die Verwaltung von SRS v1
<a name="Install_SRS"> </a>

Laden Sie das Webportal zur Verwaltung von [Microsoft Skype Room Systems v1 für Skype for Business Server 2015 herunter.](https://www.microsoft.com/download/details.aspx?id=46906)

Verwenden Sie die folgenden Schritte, um das Webportal für die Verwaltung von SRS v1 zu installieren.

1. Konfigurieren Sie den vertrauenswürdigen Anwendungsport, indem Sie das folgende Cmdlet in der Skype for Business Server-Verwaltungsshell ausführen:

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. Laden Sie zum Installieren des Besprechungsraumportals **MeetingRoomPortalInstaller.msi** und führen Sie es dann als Administrator aus.

3. Öffnen Sie Web.config Datei an folgendem Speicherort:

    %Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\

4. Ändern Sie in der Datei Web.Config den "PortalUserName" in den Benutzernamen, der in Schritt 2 im Abschnitt "Konfigurieren Ihrer Umgebung für das Webportal für die Verwaltung von[SRS v1"](room-system-v1-administrative-web-portal.md#Config_Env)erstellt wurde (der empfohlene Name im Schritt ist LRSApp):

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. Da das SRS v1 Admin Portal eine vertrauenswürdige Anwendung ist, müssen Sie das Kennwort nicht in der Portalkonfiguration angeben. Wenn dieser Benutzer eine andere Registrierungsstelle als die lokale Registrierungsstelle verwendet, müssen Sie die Registrierungsstelle dafür angeben, indem Sie die folgende Zeile in der Web.Config hinzufügen:

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. Wenn der verwendete Port nicht 5061 ist, fügen Sie die folgende Zeile in der Web.Config hinzu:

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>Überprüfen der Installation des Webportals für die Verwaltung von SRS

Gehen Sie wie folgt vor, um die Installation des Webportals für die Verwaltung von SRS v1 zu überprüfen:

1. Navigieren Sie auf einem Front-End-Server zur folgenden URL:

    https:// \<fe-server\> /lrs

    Es sollten keine Fehler angezeigt werden, wie in der folgenden Abbildung dargestellt:

     ![Anmeldebildschirm des Lync Room System Admin Portals](../../media/LRS_AdminPortalSignIn.png)

2. Wenn keine Fehler angezeigt werden, versuchen Sie, von einem anderen Computer in der Topologie aus auf die folgende URL zu zugreifen:

    https:// \<fe-server\> /lrs

    Um auf die Seite zugreifen zu können, müssen Sie die DNS-Einträge wie unter "[Erforderliche DNS-Einträge für die automatische Client-Anmeldung" beschrieben hinzufügen.](https://go.microsoft.com/fwlink/p/?LinkId=318056)

## <a name="use-the-srs-administrative-web-portal"></a>Verwenden des Webportals für die Verwaltung von SRS
<a name="Use_Portal"> </a>

Nachdem Sie SRS auf dem Server bereitgestellt haben, können Sie den Status aller SRS-Räume überprüfen, indem Sie sich über einen Browser beim Webportal für die Verwaltung von SRS v1 anmelden.

### <a name="sign-in"></a>Anmelden

1. Navigieren Sie zur folgenden URL:

    https:// \<fe-server\> /lrs

2. Geben Sie die Anmeldeinformationen für das Konto LRSSupport oder ein Konto ein, das der Sicherheitsgruppe "LRSSupportAdminGroup" hinzugefügt wurde.

![Anmeldebildschirm des Lync Room System Admin Portals](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>Zusammenfassungsseite des Webportals für die Verwaltung von SRS

Die Zusammenfassungsseite enthält die folgenden Informationen für alle auf dem Server bereitgestellten SRS-Räume:

- **Tag** Der benutzerdefinierte Name, den der Administrator dem Raum gibt. Das Tag kann im Portal durch Klicken auf den Raumnamen festgelegt werden.

- **Integrität** Der Integritätsstatus des Raum, der vom aggregierten Integritätsstatus des Raumes abgeleitet wird, der auf der Seite "Raumeinstellungen" im Abschnitt "Integrität" angezeigt wird.

- **Nächste Besprechung** Das Datum und die Uhrzeit der nächsten Besprechung.

- **SRS-Version, Hersteller, Modell** Diese Werte sind in SRS voreingestellt. Je nach Hersteller werden diese Felder möglicherweise leer gelassen.

- **Letzte Aktualisierung** Zeigt den Zeitpunkt der letzten Aktualisierung der Webseite an.

![Zusammenfassungsansicht des Lync Room System Admin Portals](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> Das Menü "Massenverwaltung" wird nur angezeigt, wenn Sie Teil der Sicherheitsgruppe "LRSPowerUserAdminsGroup" sind.

### <a name="srs-room-information"></a>Informationen zum SRS-Raum

Im Abschnitt "Rauminformationen" des Portals können Sie einzelne SRS-Räume anzeigen und konfigurieren. Sie enthält vier Abschnitte: Einstellungen, Details, Protokollierung und Integrität.

#### <a name="settings"></a>Einstellungen

Im Abschnitt "Einstellungen" können Sie das Kennwort, das Raumtag und die Standardlautstärken für den Raum festlegen. Wenn Sie diese Einstellungen konfigurieren, werden die Änderungen erst repliziert, nachdem Sie die SRS-Konsole neu gestartet haben. Systemupdateseinstellungen für SRS-Geräte werden nur mit Version 15.12 und höher angezeigt.

![Lync Room System Admin Portal Room Settings](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>Details

Der Abschnitt "Details" enthält eine schreibgeschützte Zusammenfassung der Einstellungen des SRS-Raum, einschließlich: zeitpunkt der letzten Aktualisierung; nächste Besprechung; letzte Updates, Wartung und Kalibrierung; Standardeinstellungen für Lautsprecher, Mikrofon und Klingelton; Version; SIP-URI; Anzahl der Bildschirme und Details zu jedem Bildschirm; Status und Aktivität.

![Detailansicht des Lync Room System Admin Portals](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>Problembehandlung

Der Abschnitt "Problembehandlung" kann verwendet werden, um Protokolle remote zu erfassen und an einem angegebenen Speicherort zu speichern. Sie können auch die SRS-Konsole (SRS-Benutzeroberfläche) oder das gesamte System neu starten. Geben Sie zum Erfassen von Protokollen einen Ordnerpfad im angegebenen Format an, und stellen Sie sicher, dass der Ordner über Schreibberechtigungen für das Computerkonto des SRS verfügt. Wenn die Protokollgröße zu groß ist, kann es bis zu 5 Minuten dauern, bis die Protokollsammlung abgeschlossen ist. Wenn Sie die Seite aktualisieren, erhalten Sie den neuesten Status.

#### <a name="health"></a>Gesundheitswesen

Der Abschnitt "Integrität" enthält einen visuellen Hinweis auf die Integrität der Skype for Business Server-Verbindung, des Audiogeräts, des Videogeräts, des Ausfallsicherheitsstatus und des Bildschirmgeräts.

![Lync Room System Admin Portal Room Health](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>Zusätzliche Hinweise zum Verwaltungswebportal

> [!NOTE]
>  Einstellungsänderungen werden erst angewendet, nachdem das System SRS neu gestartet wurde.> Wenn das Kennwort des LRSApp-Kontos abläuft, können Sie den Status der Räume nicht sehen. Konfigurieren Sie das Kennwort für das LRSAppuser-Konto so, dass es nie abläuft, oder achten Sie darauf, das Kennwort zu aktualisieren, wenn es bald abläuft.> Das Webportal für die Verwaltung von SRS wird nur für lokale Bereitstellungen unterstützt.

### <a name="bulk-management"></a>Massenverwaltung

Die Massenverwaltung von SRS Rooms ist ein Feature, das für fortgeschrittene IT-Administratoren entwickelt wurde, um ihren Workflow zu vereinfachen und ihnen mit einem zeitsparenden praktischen Tool die Remoteverwaltung mehrerer Räume in Massen zu ermöglichen.

Um diese Funktionalität zu sehen, muss der Benutzer als Mitglied der speziellen Sicherheitsgruppe **LRSPowerUserAdminsGroup** bereitgestellt werden.

Die Anzahl der SRS-Räume, die Sie für die Massenverwaltung auswählen können, ist nicht begrenzt. Sie können jedoch nur einen Massenverwaltungsvorgang gleichzeitig ausführen.

Wählen Sie zum Ausführen eines Massenverwaltungsvorgangs die Räume aus, die Überwacht werden soll, und klicken Sie auf das Menü "Massenverwaltung".

### <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Warum kann ich mich nicht beim Verwaltungswebportal anmelden?

Wenn Sie öffnen, können Sie die Anmeldeseite sehen, aber wenn Sie Ihre Anmeldeinformationen eingeben, können https://localhost/lrs Sie sich nicht anmelden. In diesem Fall müssen Sie geöffnet sein, https://FQDNofFEserver/SRS um sich beim Verwaltungswebportal anmelden zu können.

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>Warum kann ich SRS v1 nicht im Verwaltungswebportal sehen?

- Stellen Sie sicher, dass Sie in Ihrer Bereitstellung über ein SRS-Konto verfügen und dass sie gemäß den Empfehlungen für die Bereitstellung des Webportals für die Verwaltung von SRS erstellt werden. Stellen Sie sicher, dass die SRS-Konten auf dem Skype for Business Server mit "Enable-CsMeetingRoom" und nicht mit "Enable-CsUser" bereitgestellt werden.

- Wenn Sie die Konten im Verwaltungswebportal erstellt haben und nicht angezeigt werden können, erfassen Sie die Serverprotokolle mithilfe des Skype for Business Server-Protokollierungstools, bei dem die **Komponente "MeetingPortal"** ausgewählt ist, und senden Sie sie dann an Ihren SRS-Supportkontakt.

- Wenn Sie EINS-SRS-Konten erstellt haben und die Konten im Webportal für die Verwaltung nicht sehen können, erfassen Sie die Clientprotokolle mithilfe von Fiddler, kopieren Sie das Konsolenprotokoll aus den Browserentwicklungstools, und senden Sie sie dann an Ihren SRS-Supportkontakt. Sie können auch den Ablaufverfolgungsebenenwert in der Web.config, um ein ausführlicheres Protokoll zu erhalten.

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>Warum kann ich den Status von SRS im Webportal für die Verwaltung nicht anzeigen?

- Stellen Sie sicher, dass das LRSApp-Benutzerkonto SIP-aktiviert ist.

- Wenn weiterhin Probleme auftreten, erfassen Sie die **Datei "Trace.log"** im SRS-System von "D:\Tracing\LRSAdminLogs", und senden Sie sie dann an Ihren \, SRS-Supportkontakt.

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>Warum kann ich die Massenverwaltungsmenüs für SRS im Verwaltungswebportal nicht anzeigen?

Stellen Sie sicher, dass das LRSApp-Benutzerkonto SIP-aktiviert ist und Teil der Sicherheitsgruppe "LRSPowerUserAdminsGroup" ist.

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>Funktioniert das Webportal für die Verwaltung von SRS v1 mit Microsoft Teams-Räumen?

Nein.


