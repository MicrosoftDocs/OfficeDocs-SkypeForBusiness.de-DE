---
title: Bereitstellen von Microsoft-Teams, Räume
ms.author: Turgayo
author: Turgayo
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: In diesem Artikel erfahren Sie mehr über die Bereitstellung von Microsoft-Teams Chatrooms zu lesen.
ms.openlocfilehash: e17d607a18729cef23d98fbe9e9baf0144c50b3e
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362828"
---
# <a name="deployment-overview"></a>Übersicht über die Bereitstellung

Bereitstellung von Microsoft-Teams Chatrooms bricht im Wesentlichen in Phasen:

- Bestätigen, dass Ihre Bereitstellung Speicherorte (Chatrooms) die Bereitstellung Abhängigkeiten erfüllt
- Microsoft-Teams oder Skype für Geschäfts- und Exchange-Konten erstellen und Zuweisen der Konsolengeräte (finden Sie unter [Konfigurieren von Konten für Microsoft Teams Chatrooms](room-systems-v2-configure-accounts.md))
- Erstellen eines neuen Image Microsoft Surface Tablets als Microsoft Teams Chatrooms Konsolen verwendbar sind (siehe [Konfigurieren einer Microsoft-Teams Chatrooms Konsole](console.md) oder [Bereitstellen von Microsoft Teams Chatrooms Masse Bereitstellungshandbuch](room-systems-scale.md))
- (Optional) Einrichten von Microsoft Operations Management Suite für die Systeme (finden Sie unter [Bereitstellen von Microsoft Teams Chatrooms Management mit Azure Monitor](azure-monitor-deploy.md)
- Einrichten von Konsolen in Besprechungsräumen und verbinden die Peripheriegeräte müssen Sie (OEM-Dokumentation für den Satz von Geräten finden Sie unter)

A/v-Techs für die letzte Aufgabe, aber Ihrer Organisation verwendet werden können IT-Abteilung müssen die andere Teile des Prozesses. 


## <a name="site-readiness"></a>Website-Bereitschaft 

Während die sortierten und Geräte in Ihrer Organisation zugestellt werden, arbeiten mit Ihrer Netzwerk- und den Funktionen und die a/v-Teams dafür sorgen, dass Bereitstellung Abhängigkeiten erfüllt werden, und jede Website und Raum im Hinblick auf Leistung ist, Netzwerk, bereit und anzeigen. Stellen Sie außerdem sicher, dass die physische Installationsanforderungen erfüllt sind. Physische installationsüberlegungen finden Sie auf der Hersteller-Website, und nutzen Sie die Erfahrung Ihrer a/v-Team beim Installieren und Bereitstellen von Bildschirmen und Verkabelung ausgeführt.

Sie können diese Abhängigkeiten in die Planung Anleitungen Links unten erkunden:

-   [Überprüfen der Netzwerkverfügbarkeit](srs-v2-prep.md#check-network-availability) 
-   [Zertifikate](srs-v2-prep.md#certificates)
-   [Proxy](srs-v2-prep.md#proxy)

**Pro Tipp** - Wenn Sie beabsichtigen, Proxyserver verwenden, um Zugriff auf das Microsoft-Teams oder Skype für Business Online ersten [Dieser Artikel enthält](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online). Beachten Sie, dass bei Skype für Business-Datenverkehr über Proxyserver, sollten umgehen von Proxyservern vollständig. Skype für Business Datenverkehr ist damit Proxy-Server sicherer machen nicht bereits verschlüsselt. Als Teil Ihrer Bereitstellung breiter wird empfohlen, dass Sie die Anleitung in [Meine Umgebung bewerten](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) für Bandbreite planen und Bewerten des Netzwerks Eignung für Real-Time-Datenverkehr zu befolgen. Verwenden Sie für die gesamte Bandbreite Planung der [MyAdvisor Netzwerk Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner). (Wir empfehlen, dass Sie erstellen eine Rolle Microsoft Teams Rooms um aktualisiert die beabsichtigte Verwendung der Microsoft-Teams Chatrooms [Video, Bildschirmfreigabe, Audio], und weisen Sie eine Anzahl von Benutzern, die ermittelt die Anzahl der Einheiten von Microsoft-Teams Chatrooms für jeden Standort bereitgestellt werden.) 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Vergewissern Sie sich, dass Ihre Websites für Microsoft-Teams Chatrooms wichtigen Anforderungen erfüllen.</li><li>Vergewissern Sie sich, dass Sie genügend Bandbreite für jede Website bereitgestellt haben.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Planen der gerätebereitstellung und der Konfiguration beginnen.</li></ul>| 

**Pro-Info-** Website-Planung im Hinblick auf nützlich die folgenden Ressourcen sind. Mehr als nur Microsoft-Teams Chatrooms abdecken, und können in eine vollständige Einführung von Skype für Business Online verwendet werden:

-   [Einführung/Websitemigration Übermittlung Planungshandbuch](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_24)

-   [Einführung und Planung der Migration - Website (Playbook)](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_16)

    > [!NOTE]
    > Führen Sie in der Playbook die Aufgaben im Abschnitt "4.3 – > Konferenzräume" unter dem Blatt "4-Endpunkte" für jeden Standort, auf dem Sie vorab Microsoft Teams Chatrooms Geräte bereitstellen. Dies ermöglicht Ihnen das Skript später im Vorgang provisioning Massen-Konto verwenden. 

## <a name="service-readiness"></a>Bereitschaft für den Dienst

Führen Sie zur Vorbereitung der bereitstellungs von Microsoft-Teams Chatrooms den folgenden Schlüssel, zentralen Aufgaben aus:

-   Microsoft-Teams Chatrooms Service Account-Features zu definieren.
-   Vorbereiten einer Organisationseinheit und Active Directory-Gruppe, halten Sie den Microsoft-Teams Chatrooms Computer und Dienstkonten, und – optional – Vorbereiten von Gruppenrichtlinienobjekten (GPOs) PowerShell-Remoting aktivieren.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Definieren von Microsoft-Teams Chatrooms Service Account-features 

Je nach den Szenarien für die Zusammenarbeit, die Sie mit der Bereitstellung von Microsoft-Teams Chatrooms aktivieren entschieden haben, müssen Sie die Features und Funktionen, die Sie für jede Microsoft-Teams Chatrooms-Dienstkonto zuweisen, mit denen Sie bestimmen.

| **Szenario** | **Beschreibung** | **Microsoft Teams Chatrooms Service Account-Funktion** |
|---------- |------------- | --- |
| Interaktive Besprechungen            | Verwenden von Sprach-, Video- und Bildschirmfreigabe; tätigen von Chatrooms den Microsoft-Teams eine bookable Ressource                     | Für die Skype für Unternehmen, für Exchange (Ressourcenpostfach) aktiviert aktiviert |
| Einwahlkonferenzen            | Enable-Besprechungen *direkt* aus der Microsoft-Teams Räume-Konsole mit einwahlkonferenzen Koordinaten gestartet. | Für Audiokonferenzen aktiviert                                          |
| Ausgehend/eingehende PSTN aufrufen | Aktivieren Sie die Microsoft-Teams Chatrooms Konsole tätigen und annehmen von PSTN-Anrufe                                         | Für Telefonsystem aktiviert                                                |

Weitere Informationen zu Microsoft-Teams Räume-Konten finden Sie unter [Konten für Microsoft Teams Chatrooms konfigurieren](room-systems-v2-configure-accounts.md).


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, welche Szenarien Sie unterstützen und lizenzierungsanforderungen für die Microsoft-Teams Chatrooms Dienstkonten zu identifizieren.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Vorbereiten der host Computer und Dienstkonten.</li></ul>| 


_Planen der Tabelle Dienstkonto Microsoft Teams Chatrooms Beispiel_

| **Standort**  | **Raumname** | **Raum-Typ** | **Zukünftige Raum-Funktionen**                                                 | **Microsoft-Teams Chatrooms Kontofeatures**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| London Unternehmenszentrale | Curie         | Mittel        | 1 Bildschirm, Audio- und Videodaten plus Präsentation <br>Einwahlkonferenzen Zugriff<br> PSTN-Zugang  | Für die Skype für Unternehmen, für Exchange (Ressourcenpostfach) aktiviert aktiviert <br>Für Audiokonferenzen aktiviert <br>Für Telefonsystem aktiviert |
| Australische Unternehmenszentrale | Hill          | Große         | 2 Bildschirme, Audio- und Videodaten plus Präsentation<br>Einwahlkonferenzen Zugriff<br> PSTN-Zugang  | Für die Skype für Unternehmen, für Exchange (Ressourcenpostfach) aktiviert aktiviert<br> Für Audiokonferenzen aktiviert <br>Für Telefonsystem aktiviert |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Vorbereiten der zum Hosten von Microsoft-Teams Chatrooms Computer und Dienstkonten (optional)

Um ermöglichen es Ihnen, verwalten und Berichte zu Ihrem Microsoft-Teams Chatrooms Computer- und Dienstkonten, bereiten Sie Ihre lokale Active Directory oder Azure Active Directory (AD Azure). 

Definieren Sie eine lokale Active Directory oder Azure AD-Gruppe, um alle Microsoft-Teams Chatrooms (Benutzer) Dienstkonten auf Hinzufügen, und klicken Sie dann erstellen Sie Verwendungsberichte mithilfe des Get-CSUserSession-PowerShell-Cmdlets für Ihre Bereitstellung von Microsoft-Teams Chatrooms. Beispielsweise erstellen Sie eine Gruppe namens SkypeRoomSystemsv2 Dienstkonten. 


Definieren einer Organisationseinheit in Ihrer lokalen Active Directory oder Azure AD-Hierarchie für alle Microsoft-Teams Chatrooms Computerkonten Artikelseite (Wenn sie mit der Domäne verknüpft sind) und einer Organisationseinheit, um alle Microsoft-Teams Chatrooms Benutzerkonten zu halten. Wenn Sie eine Organisationseinheit für den Microsoft-Teams Chatrooms Computerkonten erstellen, sollten Sie Deaktivieren der Vererbung, um sicherzustellen, dass Sie nur die Richtlinien gelten, die Sie für die Domäne eingebundener Microsoft Teams Chatrooms gelten soll. 

Erstellen Sie ein Gruppenrichtlinienobjekt mit der Organisationseinheit, die Ihre Computerkonten Microsoft Teams Räume enthält zugewiesen. Verwenden Sie diese Option, um: 

-   [Power und Einstellungen für lokales Konto festgelegt](room-systems-v2-operations.md#configuring-group-policy-for-microsoft-teams-rooms).
-   Aktivieren Sie Windows Update.
-   PowerShell-Remoting zu aktivieren. Sie können ein Start-Skript zum Ausführen eines einfachen Skripts konfigurieren: Enable-psremoting sieht - Force

PowerShell können Sie eine Reihe von remote-Management-Aktivitäten, einschließlich Abrufen und Festlegen von Konfigurationsinformationen ausführen. PowerShell-Remoting aktiviert *vor* jeder PowerShell-Remoteverwaltung ergreifen kann, platzieren und sollte als Teil Ihrer Bereitstellungsprozesse berücksichtigt werden muss, oder über eine Gruppenrichtlinie konfiguriert. Weitere Informationen zu diesen Funktionen und ermöglicht es ihnen finden Sie unter [Wartung und Betrieb](room-systems-v2-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Konfiguration und Bereitstellung 

Planen der Konfiguration und Bereitstellung umfasst die folgenden wichtige Bereiche:

-   Bereitstellen von Konten
-   Gerät für die Softwareinstallation
-   Gerätebereitstellung
-   Microsoft-Teams Chatrooms Anwendung und peripherer Gerätekonfiguration
-    Tests
-   Ressourcenmanagement

### <a name="account-provisioning"></a>Bereitstellen von Konten 

Jedes Microsoft Teams Chatrooms Gerät erfordert eine dedizierte und eindeutige Ressourcenkonto, das für Microsoft-Teams oder Skype für Unternehmen und Exchange aktiviert werden muss. Dieses Konto muss ein Raumpostfach auf Exchange gehostet und als einen Besprechungsraum in der Teams oder Skype für die Bereitstellung von Business aktiviert sein. Auf der Seite Exchange muss kalenderverarbeitung konfiguriert sein, damit das Gerät automatisch eingehende Besprechungsanfragen akzeptieren kann. Weitere Informationen zum Erstellen dieser Konten finden Sie unter [Konfigurieren von Konten für Microsoft Teams Chatrooms](room-systems-v2-configure-accounts.md). 

**Tipp pro** – stellen die Anzeige für diese benennt Konten beschreibende und leicht zu verstehen. Dies sind die Namen, die Benutzern beim Suchen und Hinzufügen von Microsoft-Teams Chatrooms Systemen zu Besprechungen angezeigt wird. Manche Organisationen verwenden die Konvention *Website*-*Raumname*(*Max Raum Kapazität*)-RS, also beispielsweise Curie – eine 12 Person Konferenzraum in London – möglicherweise den Anzeigenamen LON CURIE (12)-RS. 

Wenn Ihre Organisation viele Konferenzräume, die mehrere erfordern verfügt, bereitgestellten Konten empfiehlt [Skype Raum Systeme Konten Provisioning Skripts](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_2_0_4,5_2_0_5) Massen-Bereitstellung mehrere Dienstkonten automatisiert zu verwenden.


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie die Benennungskonvention für Ihre Microsoft-Teams Chatrooms Konten.</li><li>Entscheiden Sie, ob Sie einzelne Konten erstellen, oder verwenden Sie Skripts Massen-Bereitstellung.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung Ihrer gerätebereitstellung.</li></ul>| 


### <a name="device-software-installation"></a>Gerät für die Softwareinstallation 

Bei der Planung von Microsoft-Teams Chatrooms bereitstellen, müssen Sie eine Anzahl von Optionen, um die erforderliche Software installieren. Häufige Probleme und Ansätze werden in der folgenden Tabelle beschrieben. 

| **Szenario**            | **Ansatz**         |
|-------------------------|-----------------------|   
|Eine kleine Anzahl von Microsoft-Teams Räume-Geräten (<10) bereitstellen. | Wenn Surface Pro-basierten Microsoft Teams Chatrooms verwenden möchten, führen Sie die [installationsanweisungen pro Gerät installieren](console.md). [In diesem Video praktisch führt Sie durch den Prozess.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Wenn Sie eine integrierte Lösung verwenden, mithilfe der Hersteller Bilds bereitstellen und Konfigurieren von Einstellungen nach Bedarf. |
| Bereitstellen von zwischen 10 und 50 Geräte von einem einzigen Anbieter.     | Erstellen Sie ein Bild WIM-basierte, pause nach [Schritt 6 in der Anleitung](console.md)und erfassen Sie ein Bild Verteilung mit Ihrer Klonen Verteilung Technologie verwendet werden.    |
| Bereitstellen von mehr als 50 Geräte von Microsoft Teams Chatrooms, Bereitstellen von Geräten von mehr als einem Hersteller oder erfordern organisationsspezifischen Agents im Rahmen der Bereitstellung. | Verwenden Sie eine Aufgabe Sequencer basierenden Build und Verteilung Softwareplattform, wie [System Center Configuration Manager](room-systems-scale.md).  |

**Tipp pro** - jede Microsoft-Teams Räume muss eine gültige und eindeutige Computername in Ihrem Netzwerk befinden. Viele für Überwachung und Warnungen Systeme zeigt den Namen des Computers als Schlüssel-ID, daher ist es wichtig zu eine Benennungskonvention für Microsoft-Teams Chatrooms Bereitstellungen zu entwickeln, die können für das Supportpersonal auf einfache Weise die Microsoft-Teams Räume zu finden, die markiert wurde erfordert eine Aktion. Ein Beispiel verwendet möglicherweise ein Muster der MTR -*Website*-*Raumname* (MTR LON CURIE). 

Im Rahmen der Bereitstellung müssen Sie auch sollten Ihre Strategie für die Verwaltung und Konfiguration von der [lokalen Konten](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) , die durch das Installationsprogramm der Microsoft-Teams Räume erstellt werden.

Wir bieten einen Leitfaden zum Verwenden der [Microsoft Azure Monitor](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) zum Überwachen der Bereitstellung von Microsoft-Teams Chatrooms und Verfügbarkeit, Hardware und Software Fehler und Microsoft Teams Chatrooms Anwendungsversion melden. Wenn Sie Microsoft Operations Management-Suite verwenden möchten, installieren Sie den Agent Vorgänge Management Suite als Teil der Installation der Software und konfigurieren die Workspace-Verbindungsinformationen für den Arbeitsbereich. 

Eine zusätzliche Überlegung ist, ob die Microsoft-Teams Räume Domäne beigetreten sein soll. Informationen zu den Vorteilen der Domäne beitreten kann in [Skype Raum System Domäne beitretenden Aspekte](domain-joining-considerations.md)gefunden werden. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, die Microsoft-Teams Chatrooms Gerät-Benennungskonvention während der Bereitstellung verwendet werden.</li><li>Entscheiden Sie, ob Sie Microsoft-Teams Chatrooms Geräte an Ihre Domäne und zum Verwalten und Konfigurieren von lokalen Konten teilnehmen können. </li><li>Entscheiden Sie, ob Sie zum Überwachen der bereitstellungs von Microsoft-Teams Chatrooms Vorgänge Management Suite verwenden.</li><li>Entscheiden Sie, welche Methode Sie zum Bereitstellen von Software und Agents mit dem Microsoft-Teams Chatrooms System im Rahmen der Vorbereitung für die Bereitstellung des verwenden. </li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Starten Sie die Bereitstellungsmethode Gerät planen.</li></ul>| 


### <a name="device-deployment"></a>Gerätebereitstellung

Nachdem Sie Ihre Software auf die Microsoft-Teams Chatrooms Einheiten bereitgestellt haben, erstellen Sie Ihr Plan zur liefern die Geräte und ihre zugeordneten Peripheriegeräte zu Ihrer Räumen, und fahren Sie mit der Installation und Konfiguration. 


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, wer die Website-Bereitstellung verwalten werden.</li><li> Identifizieren Sie die Ressourcen, die die Microsoft-Teams Chatrooms Geräte auf Website installiert und verpflichten sich die Konfiguration und Tests.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Starten Sie das Gerät zu testen.</li></ul>| 

_Beispieltabelle für die Bereitstellung_

| **Standort**  | **Raumname** | **Raum-Typ** | **Microsoft-Teams Chatrooms system**  | **Peripheriegeräte**  | **Microsoft-Teams Chatrooms Computername**  | **Microsoft-Teams Chatrooms Ressourcenkonto**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| London Unternehmenszentrale | Curie         | Mittel        |                                   |                  |                                          |                                             |
| Australische Unternehmenszentrale | Hill          | Große         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft-Teams Chatrooms Anwendung und peripherer Gerätekonfiguration 

Nach dem jede Microsoft-Teams Chatrooms System physisch bereitgestellt wurde, und die unterstützten Peripheriegeräte verbunden ist, müssen Sie die Anwendung Microsoft-Teams Chatrooms, weisen Sie das Microsoft-Teams Chatrooms Ressourcenkonto und Kennwort zuvor erstellten konfigurieren , um die Microsoft-Teams Chatrooms System Microsoft-Teams oder Skype für Unternehmen und Exchange anmelden zu ermöglichen. Der Schlüssel zertifizierten USB-audio und video Peripheriegeräte an anderer Stelle im Dokument verknüpft verwenden können. Nicht auf diese Weise kann zu unvorhersehbaren führen. 

Sie können jede Microsoft-Teams Chatrooms System manuell konfigurieren. Alternativ können Sie eine zentral gespeicherten verwenden – Microsoft Teams Chatrooms XML-Konfigurationsdatei zum Verwalten der Einstellungen und Nutzen eines Startpfade GPO-Skripts, um die Konfiguration angewendet werden soll, jedes Mal Microsoft Teams Chatrooms Systemstart. 

Weitere Informationen zur Verwendung von XML-Konfigurationsdatei finden Sie unter [Verwalten von einer Microsoft-Teams Chatrooms Konsole Einstellungen Remote mit einer XML-Konfigurationsdatei](xml-config-file.md). 

[Remote-PowerShell](room-systems-v2-operations.md#remote-management-using-powershell) können Sie die Konfiguration der Microsoft-Teams Chatrooms für berichterstellungsanforderungen ziehen. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Sie manuell konfigurieren Sie jedes System Microsoft Teams Chatrooms oder eine zentrale XML-Datei (eine pro Gerät Microsoft Teams Chatrooms) verwenden.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Definieren Sie Ihren Ansatz für die Remoteverwaltung.</li></ul>| 

### <a name="testing"></a> Tests

Nachdem das Microsoft-Teams Chatrooms System bereitgestellt wurde, sollten Sie sie testen. Überprüfen Sie, dass die Funktionen aufgeführt, die in der [Hilfe zu Microsoft-Teams Chatrooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) auf dem Gerät bereitgestellt werden. Es wird dringend empfohlen, dass das Bereitstellungsteam stellen Sie sicher, dass die Microsoft-Teams Räume Microsoft Operations Management Suite Protokollierung ist (falls verwendet). Es ist außerdem wichtig, dass Sie eine Reihe von Test-Aufrufe und Besprechungen auf Anrufqualität prüfen vornehmen. Weitere Informationen finden Sie unter diese [Prüfliste für die Bereitstellung hilfreich](console.md#microsoft-teams-rooms-deployment-checklist).

Es wird empfohlen, im Rahmen des allgemeinen Teams oder Skype für Business Einführung, Erstellen von Dateien für aufrufen Quality Dashboard (CQD) konfigurieren, überwacht die Qualität Trends und Teilnahme an die Qualität der Erfahrung Überprüfungsprozess. Weitere Informationen finden Sie im [Erfahrung überprüfen Handbuch für Quality of](https://aka.ms/qerguide). 

**Tipp pro** – die [Matrix testen](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) von [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) enthält eine Registerkarte mit einer Reihe von Microsoft-Teams Chatrooms Tests, die Sie als Teil der Tests überprüfen sollten. 

### <a name="asset-management"></a>Ressourcenmanagement 

Im Rahmen der Bereitstellung, Ihre Anlage Register Raumname, Gerätename Microsoft Teams Chatrooms, angemeldeten Microsoft Teams Chatrooms Ressourcenkonto aktualisieren möchten, und Peripheriegeräte zugewiesen (und welche USB-Anschlüsse verwenden). 

_Anlage Beispieltabelle_

| **Standort**  | **Raumname** | **Raum-Typ** | **Microsoft-Teams Chatrooms seriellen No.**  | **Peripheriegeräte / seriellen Selected / Ports**  | **Microsoft-Teams Chatrooms Computername**  | **Microsoft-Teams Räume-Dienstkonto**  | **Datum bereitgestellt** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| London Unternehmenszentrale | Curie         | Mittel        |                                          |                                          |                                          |                                            |                   |
| Australische Unternehmenszentrale | Hill          | Große         |                                          |                                          |                                          |                                            |                   |


