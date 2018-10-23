---
title: Bereitstellen von Skype Room Systems v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lesen Sie diesen Artikel, erfahren Sie mehr über die Bereitstellung von Skype Raum Systemen v2.
ms.openlocfilehash: dac4929338ded6fdb3b7af1dadfb3b1ce5675b97
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699630"
---
# <a name="deployment-overview"></a>Übersicht über die Bereitstellung

Bereitstellung von Skype Raum Systemen v2 bricht im Wesentlichen in Phasen:

- Bestätigen, dass Ihre Bereitstellung Speicherorte (Chatrooms) die Bereitstellung Abhängigkeiten erfüllt
- Skype für Geschäfts- und Exchange-Konten erstellen und Zuweisen der Konsolengeräte (finden Sie unter [Konfigurieren von Konten für Skype Raum Systemen v2](room-systems-v2-configure-accounts.md))
- Erstellen eines neuen Image Microsoft Surface Tablets als Skype Raum Systemen v2 Konsolen verwendbar sind (siehe [Konfigurieren einer Skype Raum Systemen v2 Konsole](console.md) oder [Bereitstellen von Skype Raum Systemen v2 Massen-e-Bereitstellungshandbuch](room-systems-scale.md))
- (Optional) Einrichten von Microsoft Operations Management Suite für die Systeme (finden Sie unter [Bereitstellen von Skype Raum v2 systemverwaltung mit OMS](with-oms.md))
- Einrichten von Konsolen in Besprechungsräumen und verbinden die Peripheriegeräte müssen Sie (OEM-Dokumentation für den Satz von Geräten finden Sie unter)

A/v-Techs für die letzte Aufgabe, aber Ihrer Organisation verwendet werden können IT-Abteilung müssen die andere Teile des Prozesses. 


## <a name="site-readiness"></a>Website-Bereitschaft 

Während die sortierten und Geräte in Ihrer Organisation zugestellt werden, arbeiten mit Ihrer Netzwerk- und den Funktionen und die a/v-Teams dafür sorgen, dass Bereitstellung Abhängigkeiten erfüllt werden, und jede Website und Raum im Hinblick auf Leistung ist, Netzwerk, bereit und anzeigen. Stellen Sie außerdem sicher, dass die physische Installationsanforderungen erfüllt sind. Physische installationsüberlegungen finden Sie auf der Hersteller-Website, und nutzen Sie die Erfahrung Ihrer a/v-Team beim Installieren und Bereitstellen von Bildschirmen und Verkabelung ausgeführt.

Sie können diese Abhängigkeiten in die Planung Anleitungen Links unten erkunden:

-   [Überprüfen der Netzwerkverfügbarkeit](../../plan-your-deployment/clients-and-devices/srs-v2-prep.md#check-network-availability) 
-   [Zertifikate](../../plan-your-deployment/clients-and-devices/srs-v2-prep.md#certificates)
-   [Proxy](../../plan-your-deployment/clients-and-devices/srs-v2-prep.md#proxy)

**Pro Tipp** - Wenn Sie beabsichtigen, Proxyserver verwenden, um Zugriff auf das Skype für Business Online ersten [Dieser Artikel enthält](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online). Beachten Sie, dass bei Skype für Business-Datenverkehr über Proxyserver, sollten umgehen von Proxyservern vollständig. Skype für Business Datenverkehr ist damit Proxy-Server sicherer machen nicht bereits verschlüsselt. Als Teil Ihrer breiter Skype für die Business-Bereitstellung wird empfohlen, dass Sie die Anleitung in [Meine Umgebung bewerten](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) für Bandbreite planen und Bewerten des Netzwerks Eignung für Real-Time-Datenverkehr zu befolgen. Verwenden Sie für die gesamte Bandbreite Planung der [MyAdvisor Netzwerk Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner). (Wir empfehlen, dass Sie eine Rolle Skype Raum Systeme v2 erstellen, um entsprechend der vorgesehenen Skype Raum v2 Systemverwendung [Video, Bildschirmfreigabe, Audio], und weisen Sie eine Anzahl von Benutzern, die die Anzahl der Einheiten an jedem Standort bereitgestellt werden Skype Raum Systeme entspricht). 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Vergewissern Sie sich, dass Ihre Websites die wichtigsten Skype Raum Systemen v2 erfüllen.</li><li>Vergewissern Sie sich, dass Sie genügend Bandbreite für jede Website bereitgestellt haben.</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Planen der gerätebereitstellung und der Konfiguration beginnen.</li></ul>| 

**Pro-Info-** Website-Planung im Hinblick auf nützlich die folgenden Ressourcen sind. Mehr als nur Skype Raum Systemen v2 abdecken, und können in eine vollständige Einführung von Skype für Business Online verwendet werden:

-   [Einführung/Websitemigration Übermittlung Planungshandbuch](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_24)

-   [Einführung und Planung der Migration - Website (Playbook)](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_16)

    > [!NOTE]
    > Führen Sie in der Playbook die Aufgaben im Abschnitt "4.3 – > Konferenzräume" unter dem Blatt "4-Endpunkte" für jeden Standort, auf dem Sie planen, Skype Raum Systemen v2 Geräte bereitstellen. Dies ermöglicht Ihnen das Skript später im Vorgang provisioning Massen-Konto verwenden. 

## <a name="service-readiness"></a>Bereitschaft für den Dienst

Führen Sie zur Vorbereitung Ihrer bereitstellungs Skype Raum Systeme die folgenden Schlüssel, zentralen Aufgaben aus:

-   Definieren Sie Skype Raum Systeme Service Account-Features.
-   Vorbereiten einer Organisationseinheit und Active Directory-Gruppe, halten Sie Ihren Computer Skype Raum Systeme und-Dienstkonten und – optional – Vorbereiten von Gruppenrichtlinienobjekten (GPOs) PowerShell-Remoting aktivieren.

### <a name="define-skype-room-systems-service-account-features"></a>Definieren von Skype Raum Systeme Service Account-features 

Je nach den Szenarien für die Zusammenarbeit, die Sie mit der Skype Raum Systemen v2-Bereitstellung aktivieren entschieden haben, müssen Sie die Features und Funktionen, die Sie für jede Skype Raum Systemen v2-Dienstkonto zuweisen, mit denen Sie bestimmen.

| **Szenario** | **Beschreibung** | **Skype Raum Systeme v2 Service Account-Funktion** |
|---------- |------------- | --- |
| Interaktive Besprechungen            | Verwenden von Sprach-, Video- und Bildschirmfreigabe; Durchführen der Skype Raum Systemen v2 eine bookable Ressource                     | Für die Skype für Unternehmen, für Exchange (Ressourcenpostfach) aktiviert aktiviert |
| Einwahlkonferenzen            | Schritte Besprechungen *direkt* aus der Skype Raum Systemen v2-Konsole mit einwahlkonferenzen Koordinaten aktivieren | Für Audiokonferenzen aktiviert                                          |
| Ausgehend/eingehende PSTN aufrufen | Aktivieren der Skype Raum Systemen v2-Konsole das tätigen und annehmen von PSTN-Anrufe                                         | Für Telefonsystem aktiviert                                                |

Weitere Informationen zu Skype Raum Systeme-Konten finden Sie unter [Konfigurieren von Konten für Skype Raum Systemen v2](room-systems-v2-configure-accounts.md).


|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, welche Szenarien Sie unterstützen und lizenzierungsanforderungen für die Skype Raum Systemen v2 Dienstkonten zu identifizieren.</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Vorbereiten der host Computer und Dienstkonten.</li></ul>| 


_Beispiel Skype Raum Systemen v2-Dienstkonto planning-Tabelle_

| **Standort**  | **Raumname** | **Raum-Typ** | **Zukünftige Raum-Funktionen**                                                 | **Skype-Chatroom-Systemen v2 Kontofeatures**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| London Unternehmenszentrale | Curie         | Mittel        | 1 Bildschirm, Audio- und Videodaten plus Präsentation <br>Einwahlkonferenzen Zugriff<br> PSTN-Zugang  | Für die Skype für Unternehmen, für Exchange (Ressourcenpostfach) aktiviert aktiviert <br>Für Audiokonferenzen aktiviert <br>Für Telefonsystem aktiviert |
| Australische Unternehmenszentrale | Hill          | Groß         | 2 Bildschirme, Audio- und Videodaten plus Präsentation<br>Einwahlkonferenzen Zugriff<br> PSTN-Zugang  | Für die Skype für Unternehmen, für Exchange (Ressourcenpostfach) aktiviert aktiviert<br> Für Audiokonferenzen aktiviert <br>Für Telefonsystem aktiviert |


### <a name="prepare-to-host-skype-room-systems-v2-machine-and-service-accounts-optional"></a>Vorbereiten Sie der Hostcomputer Skype Raum Systemen v2 und Dienstkonten Sie (optional)

So aktivieren Sie Sie verwalten und Berichten über Computers v2 Skype Raum Systeme und Dienstkonten, bereiten Sie Ihre lokale Active Directory oder Azure Active Directory (AD Azure) vor. 

Definieren Sie eine lokale Active Directory oder Azure AD-Gruppe alle Skype Raum Systemen v2 (Benutzer) Dienstkonten auf Hinzufügen, und klicken Sie dann erstellen Sie Verwendungsberichte mithilfe des Get-CSUserSession-PowerShell-Cmdlets für Ihre Bereitstellung der Skype Raum Systemen v2. Beispielsweise erstellen Sie eine Gruppe namens SkypeRoomSystemsv2 Dienstkonten. 


Definieren einer Organisationseinheit in Ihrer lokalen Active Directory oder Azure AD-Hierarchie, die alle Skype Raum Systemen v2 Computerkonten enthalten soll (Wenn sie mit der Domäne verknüpft sind) und einer Organisationseinheit, um alle Skype Raum Systemen v2-Benutzerkonten zu halten. Wenn Sie eine Organisationseinheit für die Skype Raum Systemen v2 Konten auf dem Computer erstellen, sollten Sie Deaktivieren der Vererbung, um sicherzustellen, dass Sie nur die Richtlinien gelten, die Sie für die Domäne eingebundener Skype Raum Systemsv2 gelten soll. 

Erstellen Sie ein Gruppenrichtlinienobjekt mit der Organisationseinheit, die Ihre Computerkonten Skype Raum Systeme enthält zugewiesen. Verwenden Sie diese Option, um: 

-   [Power und Einstellungen für lokales Konto festgelegt](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#configuring-group-policy-for-skype-room-systems-v2).
-   Aktivieren Sie Windows Update.
-   PowerShell-Remoting zu aktivieren. Sie können ein Start-Skript zum Ausführen eines einfachen Skripts konfigurieren: Enable-psremoting sieht - Force

PowerShell können Sie eine Reihe von remote-Management-Aktivitäten, einschließlich Abrufen und Festlegen von Konfigurationsinformationen ausführen. PowerShell-Remoting aktiviert *vor* jeder PowerShell-Remoteverwaltung ergreifen kann, platzieren und sollte als Teil Ihrer Bereitstellungsprozesse berücksichtigt werden muss, oder über eine Gruppenrichtlinie konfiguriert. Weitere Informationen zu diesen Funktionen und ermöglicht es ihnen finden Sie unter [Wartung und Betrieb](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Konfiguration und Bereitstellung 

Planen der Konfiguration und Bereitstellung umfasst die folgenden wichtige Bereiche:

-   Bereitstellen von Konten
-   Gerät für die Softwareinstallation
-   Gerätebereitstellung
-   Skype-Chatroom-Systemen v2 Anwendung und peripherer Gerätekonfiguration
-    Tests
-   Ressourcenmanagement

### <a name="account-provisioning"></a>Bereitstellen von Konten 

Jedes Skype Raum Systemen v2 Gerät erfordert eine dedizierte und eindeutige Ressourcenkonto, die für beide Skype für Unternehmen und Exchange aktiviert werden muss. Dieses Konto muss ein Raumpostfach auf Exchange gehostet und als einen Besprechungsraum in der Skype für die Bereitstellung von Business aktiviert sein. Auf der Seite Exchange muss kalenderverarbeitung konfiguriert sein, damit das Gerät automatisch eingehende Besprechungsanfragen akzeptieren kann. Weitere Informationen zum Erstellen dieser Konten finden Sie unter [Konfigurieren von Konten für Skype Raum Systemen v2](room-systems-v2-configure-accounts.md). 

**Tipp pro** – stellen die Anzeige für diese benennt Konten beschreibende und leicht zu verstehen. Dies sind die Namen, die Benutzern angezeigt werden, wenn für Suchen und Hinzufügen von Skype Raum v2-basierte Systeme zu Besprechungen. Manche Organisationen verwenden die Konvention *Website*-*Raumname*(*Max Raum Kapazität*)-RS, also beispielsweise Curie – eine 12 Person Konferenzraum in London – möglicherweise den Anzeigenamen LON CURIE (12)-RS. 

Wenn Ihre Organisation viele Konferenzräume, die mehrere erfordern verfügt, bereitgestellten Konten empfiehlt [Skype Raum Systeme Konten Provisioning Skripts](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_2_0_4,5_2_0_5) Massen-Bereitstellung mehrere Dienstkonten automatisiert zu verwenden. 


|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie die Benennungskonvention für Ihre Skype Raum Systemen v2 Konten.</li><li>Entscheiden Sie, ob Sie einzelne Konten erstellen, oder verwenden Sie Skripts Massen-Bereitstellung.</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung Ihrer gerätebereitstellung.</li></ul>| 


### <a name="device-software-installation"></a>Gerät für die Softwareinstallation 

Bei der Planung von Skype Raum Systemsv2 bereitstellen, müssen Sie eine Anzahl von Optionen, um die erforderliche Software installieren. Häufige Probleme und Ansätze werden in der folgenden Tabelle beschrieben. 

| **Szenario**            | **Ansatz**         |
|-------------------------|-----------------------|   
|Eine kleine Anzahl von Skype Raum Systeme Geräten bereitstellen (< 10). | Wenn Surface Pro-basierten Skype Raum Systemen v2 verwenden, führen Sie die [installationsanweisungen pro Gerät installieren](console.md). [In diesem Video praktisch führt Sie durch den Prozess.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Wenn Sie eine integrierte Lösung verwenden, mithilfe der Hersteller Bilds bereitstellen und Konfigurieren von Einstellungen nach Bedarf. |
| Bereitstellen von zwischen 10 und 50 Geräte von einem einzigen Anbieter.     | Erstellen Sie ein Bild WIM-basierte, pause nach [Schritt 6 in der Anleitung](console.md)und erfassen Sie ein Bild Verteilung mit Ihrer Klonen Verteilung Technologie verwendet werden.    |
| Bereitstellen von mehr als 50 Skype Raum Systeme Geräten, Bereitstellen von Geräten von mehr als einem Hersteller oder organisationsspezifischen Agents im Rahmen der Bereitstellung erfordern. | Verwenden Sie eine Aufgabe Sequencer basierenden Build und Verteilung Softwareplattform, wie [System Center Configuration Manager](with-oms.md).  |

**Tipp pro** - Each Skype Raum Systemen v2 muss eine gültige und eindeutige Computername in Ihrem Netzwerk befinden. Viele für Überwachung und Warnungen Systeme zeigt den Namen des Computers als Schlüssel-ID, damit es ist wichtig, eine Benennungskonvention für Skype Raum Systemen v2 Bereitstellungen zu entwickeln, die können für das Supportpersonal auf einfache Weise die v2 Skype Raum Systeme finden, die als markiert wurde eine Aktion kommunizieren können. Ein Beispiel verwendet möglicherweise ein Muster der SRS -*Website*-*Raumname* (SRS LON CURIE). 


Im Rahmen der Bereitstellung müssen Sie auch sollten Ihre Strategie für die Verwaltung und Konfiguration von der [lokalen Konten](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) , die durch das Installationsprogramm der Skype Raum Systeme erstellt werden.

Wir bieten einen Leitfaden zum Verwenden der [Microsoft Operations Management Suite](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/oms-management) zum Überwachen der Skype Raum Systemen v2-bereitstellungs und Berichten über Verfügbarkeit, Hardware und Software-Fehlern und Skype Raum Systemen v2 Anwendungsversion. Wenn Sie Microsoft Operations Management-Suite verwenden möchten, installieren Sie den Agent Vorgänge Management Suite als Teil der Installation der Software und konfigurieren die Workspace-Verbindungsinformationen für den Arbeitsbereich. 

Eine zusätzliche Überlegung ist, ob die Skype Raum Systemen v2 Domäne beigetreten sein soll. Informationen zu den Vorteilen der Domäne beitreten kann in [Skype Raum System Domäne beitretenden Aspekte](domain-joining-considerations.md)gefunden werden. 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, der Skype Raum Systeme Gerät-Benennungskonvention während der Bereitstellung verwendet werden.</li><li>Entscheiden Sie, ob Sie Skype Raum Systemen v2 Geräte an Ihre Domäne und zum Verwalten und Konfigurieren von lokalen Konten teilnehmen können. </li><li>Entscheiden Sie, ob Sie zum Überwachen der bereitstellungs der Skype Raum Systemen v2 Operations Management Suite verwenden.</li><li>Entscheiden Sie, welche Methode Sie zum Bereitstellen von Software und Agents mit dem Skype Raum Systemen v2 System im Rahmen der Vorbereitung für die Bereitstellung des verwenden. </li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Starten Sie die Bereitstellungsmethode Gerät planen.</li></ul>| 


### <a name="device-deployment"></a>Gerätebereitstellung

Nachdem Sie Ihre Software entsprechen den v2 Einheiten Skype Raum Systeme bereitgestellt haben, erstellen Sie Ihr Plan zur liefern die Geräte und ihre zugeordneten Peripheriegeräte zu Ihrer Räumen, und fahren Sie mit der Installation und Konfiguration. 


|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, wer die Website-Bereitstellung verwalten werden.</li><li> Identifizieren Sie die Ressourcen, die die Skype Raum Systemen v2 Geräte auf Website installiert und verpflichten sich die Konfiguration und Tests.</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Starten Sie das Gerät zu testen.</li></ul>| 

_Beispieltabelle für die Bereitstellung_

| **Standort**  | **Raumname** | **Raum-Typ** | **Skype-Chatroom-Systemen v2 system**  | **Peripheriegeräte**  | **Skype-Chatroom-Systemen v2-Computername**  | **Skype-Chatroom-Systemen v2 Ressourcenkonto**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| London Unternehmenszentrale | Curie         | Mittel        |                                   |                  |                                          |                                             |
| Australische Unternehmenszentrale | Hill          | Groß         |                                   |                  |                                          |                                             |

### <a name="skype-room-systems-v2-application-and-peripheral-device-configuration"></a>Skype-Chatroom-Systemen v2 Anwendung und peripherer Gerätekonfiguration 

Nach jedem Skype Raum Systemen v2 System physisch bereitgestellt wurde, und die unterstützten Peripheriegeräte verbunden ist, Sie die Skype Raum Systemen v2-Anwendung zum Zuweisen der Skype Raum Systemen v2 Ressourcenkonto und die zuvor erstellte Kennwort konfigurieren müssen auf Damit das Skype Raum Systemen v2 System für Unternehmen und Exchange Skype anmelden. Es handelt sich um Schlüssel Skype für USB-audio und video Peripheriegeräte an anderer Stelle im Dokument verknüpft certified Business verwenden können. Nicht auf diese Weise kann zu unvorhersehbaren führen. 

Sie können jedes Skype Raum Systemen v2 System manuell konfigurieren. Sie können auch eine zentral gespeicherten pro – Skype Raum Systeme XML-Konfigurationsdatei zum Verwalten der Einstellungen und Nutzen eines Startpfade GPO-Skripts, um die Konfiguration angewendet werden soll, jedes Mal Skype Raum Systemen v2 Systemstart. 

Weitere Informationen zur Verwendung von XML-Konfigurationsdatei finden Sie unter [Konsolenstamm Remote mit einer XML-Konfigurationsdatei Verwalten einer Skype Raum Systemen v2](../../manage/skype-room-systems-v2/xml-config-file.md). 

[Remote-PowerShell](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#remote-management-using-powershell) können Sie die Konfiguration der Skype Raum Systemen v2 für berichterstellungsanforderungen pull. 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Sie manuell konfigurieren Sie jedes Skype Raum Systemen v2 System oder eine zentrale XML-Datei (eine pro Skype Raum Systemen v2 Gerät) verwenden.</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Definieren Sie Ihren Ansatz für die Remoteverwaltung.</li></ul>| 

### <a name="testing"></a> Tests

Nachdem das Skype Raum Systemen v2 System bereitgestellt wurde, sollten Sie sie testen. Überprüfen Sie, dass die Funktionen in [Skype Raum Systemen v2 Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) aufgeführten auf dem Gerät bereitgestellt werden. Es wird dringend empfohlen, dass das Bereitstellungsteam stellen Sie sicher, dass die Skype Raum Systemen v2 Microsoft Operations Management Suite Protokollierung ist (falls verwendet). Es ist außerdem wichtig, dass Sie eine Reihe von Test-Aufrufe und Besprechungen auf Anrufqualität prüfen vornehmen. Weitere Informationen finden Sie unter diese [Prüfliste für die Bereitstellung hilfreich](console.md#skype-room-systems-v2-deployment-checklist). 

Es wird empfohlen, im Rahmen der allgemeinen Skype für Business Einführung, Erstellen von Dateien für aufrufen Quality Dashboard (CQD) konfigurieren, überwacht die Qualität Trends und Teilnahme an die Qualität der Erfahrung Überprüfungsprozess. Weitere Informationen finden Sie im [Erfahrung überprüfen Handbuch für Quality of](https://aka.ms/qerguide). 

**Tipp pro** – die [Matrix testen](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) von [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) enthält eine Registerkarte mit einer Anzahl von Skype Raum Systemen v2 Tests, die Sie als Teil der Tests überprüfen sollten. 

### <a name="asset-management"></a>Ressourcenmanagement 

Im Rahmen der Bereitstellung, Ihre Anlage Register Raumname, Skype Raum Systemen v2 Gerätename, angemeldeten Skype Raum Systemen v2-Ressourcenkonto aktualisieren möchten, und Peripheriegeräte zugewiesen (und welche USB-Anschlüsse verwenden). 

_Anlage Beispieltabelle_

| **Standort**  | **Raumname** | **Raum-Typ** | **Skype-Chatroom-Systemen v2 seriellen No.**  | **Peripheriegeräte / seriellen Selected / Ports**  | **Skype-Chatroom-Systemen v2-Computername**  | **Skype-Chatroom-Systemen v2-Dienstkonto**  | **Datum bereitgestellt** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| London Unternehmenszentrale | Curie         | Mittel        |                                          |                                          |                                          |                                            |                   |
| Australische Unternehmenszentrale | Hill          | Groß         |                                          |                                          |                                          |                                            |                   |


