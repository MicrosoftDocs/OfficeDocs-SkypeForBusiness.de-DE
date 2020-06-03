---
title: Bereitstellen des administrativen SRS v1-Webportals in Skype for Business Server
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
description: Das Skype for Business Server Skype Room Systems v1 (SRS v1, früher als lync Room System bezeichnet) administratives Webportal ist ein Webportal, mit dem Organisationen ihre Skype Room Systems-Konferenzräume aufrecht erhalten können. Administratoren können das administrative Webportal von SRS v1 verwenden, um die Geräte Integrität zu überwachen, beispielsweisedurch Überwachung von Audio/Videogeräten. Mit diesem Portal können Administratoren Remote Diagnoseinformationen sammeln, um die Integrität des Konferenzraums zu überwachen.
ms.openlocfilehash: d718adb60437fdd7e08724a5ba5fc48fa120425e
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "42045898"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Bereitstellen des administrativen SRS v1-Webportals in Skype for Business Server

Das Skype for Business Server Skype Room Systems v1 (SRS v1, früher als lync Room System bezeichnet) administratives Webportal ist ein Webportal, mit dem Organisationen ihre Skype Room Systems-Konferenzräume aufrecht erhalten können. Administratoren können das administrative Webportal von SRS v1 verwenden, um die Geräte Integrität zu überwachen, beispielsweisedurch Überwachung von Audio/Videogeräten. Mit diesem Portal können Administratoren Remote Diagnoseinformationen sammeln, um die Integrität des Konferenzraums zu überwachen.

Um dieses Feature verwenden zu können, muss das administrative Webportal SRS v1 auf jeder Skype for Business Server Front-End-Server bereitgestellt werden. Dieses Handbuch enthält Anweisungen für Administratoren zum Installieren und Konfigurieren des Webportals für die SRS-Verwaltung. Sie richtet sich an Administratoren, die über Kenntnisse in Skype for Business Server Verwaltung verfügen und über Administratorrechte verfügen, um die Skype for Business Server Topologie zu ändern.

Nachdem das Verwaltungsportal SRS v1 auf dem Server bereitgestellt wurde, können Administratoren den Status SRS v1-Geräte überprüfen, indem Sie sich über ihre eigenen Computer oder Laptops an der Website anmelden.

> [!IMPORTANT]
> Laden Sie das [Microsoft Skype Room Systems v1-Verwaltungs Webportal für Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906)herunter.

Inhalt dieses Themas:

- [Konfigurieren der Umgebung für das administrative Webportal von SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)

- [Installieren des Administrator-Webportals für SRS v1](room-system-v1-administrative-web-portal.md#Install_SRS)

- [Verwenden des Webportals für die SRS-Verwaltung](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>Konfigurieren der Umgebung für das administrative Webportal von SRS v1
<a name="Config_Env"> </a>

Um das administrative Webportal SRS v1 verwenden zu können, müssen Sie die folgenden Voraussetzungen installieren oder konfigurieren.

> [!IMPORTANT]
> Wenn der Server mit der Kerberos-und der NTLM-Authentifizierung konfiguriert ist und SRS auf einem Computer ausgeführt wird, der nicht der Domäne angehört, schlägt die Kerberos-Authentifizierung fehl, und der Benutzer kann den Status SRS nicht im Verwaltungsportal sehen. Um dieses Problem zu beheben, konfigurieren Sie den Server mit NTLM-Authentifizierung oder mit NTLM-und TLS-DSK-Authentifizierung (ohne Kerberos), oder verbinden Sie den SRS-Computer mit der Domäne.

1. Installieren Sie Skype for Business Server kumulierten Updates in der Skype for Business Server-Topologie.

    Informationen zum Abrufen des Updates oder zum Anzeigen der darin enthaltenen Informationen finden Sie unter [Updates für Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).

2. Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer.

    Das administrative Webportal SRS v1 verwendet diese Anmeldeinformationen zum Abfragen von Informationen aus Skype for Business Server. Der Benutzername in den angegebenen Beispielen lautet LRSApp.

3. Erstellen Sie eine Active Directory Sicherheitsgruppe mit dem Namen LRSSupportAdminGroup.

    Erstellen Sie die Gruppe mit dem Gruppenbereich als globaler und Gruppentyp als Sicherheit. SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, die Liste der Räume anzuzeigen und bestimmte Befehle auszuführen, beispielsweise das Sammeln von Protokollen.

4. Erstellen Sie eine Active Directory Sicherheitsgruppe mit dem Namen LRSFullAccessAdminGroup.

    Erstellen Sie die Gruppe mit Gruppenbereich als globaler und Gruppentyp als Sicherheit. SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, alle Verwaltungsportal Funktionen in einem einzelnen Skype-Raum zu verwenden. Wenn Sie Unterstützung für die Massenverwaltung von Skype-Räumen einschließen möchten, lesen Sie Schritt 5.

     ![Liste der Administratorgruppen mit der Rolle "Sicherheitsgruppe"](../../media/LRS_LRSFullAccessAdminGroup.png)

5. Erstellen Sie eine Active Directory Sicherheitsgruppe mit dem Namen LRSPowerUserAdminsGroup.

    Erstellen Sie die Gruppe mit dem Gruppenbereich als globaler und Gruppentyp als Sicherheit. SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, alle Verwaltungsportal Funktionen einschließlich der Massenverwaltung von Skype for Business Chatrooms zu verwenden.

6. Fügen Sie LRSFullAccessAdminGroup als Mitglied von LRSSupportAdminGroup hinzu.

     ![LRSSupportAdminGroup-Eigenschaften-Mitgliederseite](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. Erstellen Sie einen SIP-aktivierten Active Directory Benutzer mit dem Namen LRSSupport. Fügen Sie diesen Benutzer zu LRSSupportAdminGroup hinzu.

     ![LRSSupportAdminGroup-Eigenschaften-Mitgliederseite](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. Installieren Sie [ASP.NET MVC 4 für Visual Studio 2010 SP1 und Visual-webdeveloper 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).

## <a name="install-the-srs-v1-administrative-web-portal"></a>Installieren des Administrator-Webportals für SRS v1
<a name="Install_SRS"> </a>

Laden Sie das [Microsoft Skype Room Systems v1-Verwaltungs Webportal für Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906)herunter.

Führen Sie die folgenden Schritte aus, um das administrative Webportal von SRS V1 zu installieren.

1. Konfigurieren Sie den Port für vertrauenswürdige Anwendungen, indem Sie das folgende Cmdlet in Skype for Business Server Management Shell ausführen:

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. Um das Besprechungsraum Portal zu installieren, laden Sie **MeetingRoomPortalInstaller. msi** herunter, und führen Sie es dann als Administrator aus.

3. Öffnen Sie die Datei "file. config" unter folgendem Speicherort:

    % Programm-files%\Skype for Business Server 2015 \ Components\Meeting Raum Portal\Int\Handler\

4. Ändern Sie in der Datei "file. config" den PortalUserName in den in Schritt 2 erstellten Benutzernamen im Abschnitt "[Konfigurieren der Umgebung für das administrative Webportal der SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)" (der empfohlene Name im Schritt lautet LRSApp):

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. Da das SRS v1-Verwaltungsportal eine vertrauenswürdige Anwendung ist, müssen Sie das Kennwort nicht in der Portal Konfiguration angeben. Wenn dieser Benutzer eine andere Registrierungsstelle als die lokale Registrierungsstelle verwendet, müssen Sie die Registrierungsstelle dafür angeben, indem Sie die folgende in der Datei "Internet. config" hinzufügen:

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. Wenn es sich bei dem verwendeten Port nicht um 5061 handelt, fügen Sie die folgende in der Datei "Internet. config" hinzu:

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>Überprüfen der Installation des Webportals für die SRS-Verwaltung

Führen Sie die folgenden Schritte aus, um die Installation des administrativen Webportal SRS V1 zu überprüfen:

1. Navigieren Sie auf einem Front-End-Server zur folgenden URL:

    https:// \<fe-server\> /LRS

    Es sollten keine Fehler angezeigt werden, wie in der folgenden Abbildung dargestellt:

     ![Anmeldebildschirm des lync Room-System Administrator Portals](../../media/LRS_AdminPortalSignIn.png)

2. Wenn keine Fehler angezeigt werden, versuchen Sie von einem anderen Computer in der Topologie aus auf die folgende URL zuzugreifen:

    https:// \<fe-server\> /LRS

    Um auf die Seite zugreifen zu können, müssen Sie die DNS-Einträge wie unter "[erforderliche DNS-Einträge für die automatische Client Anmeldung](https://go.microsoft.com/fwlink/p/?LinkId=318056)" beschrieben hinzufügen.

## <a name="use-the-srs-administrative-web-portal"></a>Verwenden des Webportals für die SRS-Verwaltung
<a name="Use_Portal"> </a>

Nachdem Sie SRS auf dem Server bereitgestellt haben, können Sie den Status aller SRS-Räume überprüfen, indem Sie sich über einen Browser beim administrativen Webportal SRS v1 anmelden.

### <a name="sign-in"></a>Anmelden

1. Wechseln Sie zur folgenden URL:

    https:// \<fe-server\> /LRS

2. Geben Sie die Anmeldeinformationen für das LRSSupport-Konto oder ein Konto ein, das der Sicherheitsgruppe LRSSupportAdminGroup hinzugefügt wurde.

![Anmeldebildschirm des lync Room-System Administrator Portals](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>Seite "Zusammenfassung der SRS-administrativen Webportale"

Die Zusammenfassungsseite enthält die folgenden Informationen für alle auf dem Server bereitgestellten SRS-Räume:

- - **Tag** Der benutzerdefinierte Name, den der Administrator dem Chatroom übergibt. Das-Tag kann im Portal festgelegt werden, indem auf den Raumnamen geklickt wird.

- **Integrität** Der Integritätsstatus des Raums, der vom aggregierten Integritätsstatus des Raums abgeleitet wird, der auf der Seite "Raumeinstellungen" im Abschnitt "Integrität" angezeigt wird.

- **Nächste Besprechung** Das Datum und die Uhrzeit, zu denen die nächste Besprechung geplant ist.

- **SRS-Version, Hersteller, Modell** Diese Werte sind in SRS voreingestellt. Je nach Hersteller können diese Felder leer bleiben.

- **Letzte Aktualisierung** Zeigt an, wann die Webseite zuletzt aktualisiert wurde.

![Zusammenfassung der lync Room System-Administrator Portal-Ansicht](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> Das Menü Massenverwaltung wird nur angezeigt, wenn Sie Mitglied der Sicherheitsgruppe LRSPowerUserAdminsGroup sind.

### <a name="srs-room-information"></a>SRS-Rauminformationen

Im Abschnitt Rauminformationen des Portals können Sie einzelne SRS-Räume anzeigen und konfigurieren. Es enthält vier Abschnitte: Einstellungen, Details, Protokollierung und Integrität.

#### <a name="settings"></a>Einstellungen

Im Abschnitt "Einstellungen" können Sie das Kennwort, das Raum-Tag und die Standardlautstärke für den Raum festlegen. Wenn Sie diese Einstellungen konfigurieren, werden die Änderungen erst nach dem Neustart der SRS-Konsole repliziert. Es werden nur System Updateeinstellungen für SRS-Geräte mithilfe von Version 15,12 und höher angezeigt.

![Raum System-Administrator Portal-Einstellungen für lync Room-Systeme](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>Details

Der Abschnitt Details enthält eine schreibgeschützte Zusammenfassung der Einstellungen des SRS-Raums, einschließlich: der Zeitpunkt der letzten Aktualisierung; nächste Besprechung; Letzte Aktualisierungen, Wartung und Kalibrierung; Standardeinstellungen für Lautsprecher, Mic und Rufton; Version SIP-URI; Anzahl der Bildschirme und Details zu jedem Bildschirm; Status und Aktivität.

![Detail Ansicht des lync Room-System Administrator Portals](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>Problembehandlung

Der Abschnitt Problembehandlung kann verwendet werden, um Protokolle Remote zu sammeln und Sie an einem angegebenen Speicherort zu speichern. Sie können auch die SRS-Konsole (SRS-Benutzeroberfläche) neu starten oder das gesamte System neu starten. Geben Sie zum Sammeln von Protokollen einen Ordnerpfad im angegebenen Format an, und stellen Sie sicher, dass der Ordner über Schreibberechtigungen verfügt, die für das Konto des SRS-Computers erteilt wurden. Wenn die Protokollgröße zu groß ist, kann es bis zu 5 Minuten dauern, bis das Sammeln von Protokollen abgeschlossen ist. Wenn Sie die Seite aktualisieren, erhalten Sie den neuesten Status.

#### <a name="health"></a>Gesundheitswesen

Der Abschnitt "Integrität" gibt einen visuellen Hinweis auf die Integrität der Skype for Business Server-Verbindung, des Audiogeräts, des Videogeräts, des Zustands der Ausfallsicherheit und des Bildschirmgeräts.

![Raum System-Administrator Portal für lync Room-Integrität](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>Zusätzliche Hinweise zum administrativen Webportal

> [!NOTE]
>  Einstellungsänderungen werden erst dann angewendet, wenn das SRS-System neu gestartet wird. > Wenn das LRSApp-Kontokennwort abgelaufen ist, können Sie den Status der Räume nicht anzeigen. Konfigurieren Sie das Kennwort für das LRSAppuser-Konto so, dass es nie abläuft, oder aktualisieren Sie das Kennwort, wenn es sich in der Nähe des Ablaufs befindet. > das SRS-Verwaltungsportal wird nur für lokale Bereitstellungen unterstützt.

### <a name="bulk-management"></a>Massenverwaltung

Die Massenverwaltung von SRS Rooms ist ein Feature, das für fortgeschrittene IT-Administratoren entwickelt wurde, um den Workflow zu vereinfachen und Sie mit einem zeitsparenden, bequemen Tool zur Remoteverwaltung mehrerer Räume in massenweise zu ermöglichen.

Um diese Funktionalität sehen zu können, muss der Benutzer als Mitglied der speziellen Sicherheitsgruppe " **LRSPowerUserAdminsGroup**" bereitgestellt werden.

Es gibt keine Beschränkung für die Anzahl der SRS-Räume, die Sie für die Massenverwaltung auswählen können. Sie können jedoch jeweils nur einen Massen Verwaltungsvorgang ausführen.

Wählen Sie zum Durchführen eines Massen Verwaltungsvorgangs die Räume aus, die Sie überwachen möchten, und klicken Sie dann auf das Massen Verwaltungsmenü.

### <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Warum kann ich mich nicht beim administrativen Webportal anmelden?

Wenn Sie öffnen https://localhost/lrs , werden Sie die Anmeldeseite sehen können, aber wenn Sie Ihre Anmeldeinformationen eingeben, können Sie sich nicht anmelden. In diesem Fall müssen Sie sich öffnen, um https://FQDNofFEserver/SRS sich beim administrativen Webportal anzumelden.

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>Warum wird SRS v1 nicht im administrativen Webportal angezeigt?

- Stellen Sie sicher, dass Sie über SRS-Konten in Ihrer Bereitstellung verfügen und dass Sie gemäß den Bereitstellungsempfehlungen für das SRS-Verwaltungsportal erstellt wurden. Stellen Sie sicher, dass die SRS-Konten mithilfe von enable-csmeetingroom ", not enable-CsUser, im Skype for Business Server bereitgestellt werden.

- Wenn Sie SRS-Konten erstellt haben und die Konten im administrativen Webportal nicht sehen können, sammeln Sie die Serverprotokolle mithilfe des Skype for Business Server Protokollierungstools, wobei die **MeetingPortal** -Komponente ausgewählt ist, und senden Sie Sie dann an Ihren SRS-Support Kontakt.

- Wenn Sie SRS-Konten erstellt haben und die Konten im administrativen Webportal nicht sehen können, sammeln Sie die Clientprotokolle mit Fiddler und kopieren Sie das Konsolenprotokoll auch aus den Browser Entwicklungstools, und senden Sie Sie dann an Ihren SRS-Support Kontakt. Sie können den Wert der Ablaufverfolgungsstufe auch in der Datei "Internet. config" ändern, um ein detaillierteres Protokoll zu erhalten.

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>Warum kann ich den Status von SRS nicht im administrativen Webportal anzeigen?

- Stellen Sie sicher, dass das LRSApp-Benutzerkonto SIP-aktiviert ist.

- Wenn Sie weiterhin Probleme haben, sammeln Sie die Datei **Trace. log** im SRS-System von D:\Tracing\LRSAdminLogs, \, und senden Sie Sie dann an Ihren SRS-Support Kontakt.

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>Warum kann ich die Menüs für die Massenverwaltung für SRS nicht im administrativen Webportal anzeigen?

Stellen Sie sicher, dass das LRSApp-Benutzerkonto SIP-aktiviert ist und Teil der Sicherheitsgruppe LRSPowerUserAdminsGroup ist.

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>Funktioniert das administrative Webportal SRS V1 mit Microsoft Teams-Räumen?

Nein.


