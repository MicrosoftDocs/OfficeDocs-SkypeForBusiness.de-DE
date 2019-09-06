---
title: Bereitstellen von Microsoft Teams-Räumen
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lesen Sie diesen Artikel, um Informationen zum Bereitstellen von Microsoft Teams-Räumen zu erhalten.
ms.openlocfilehash: 132c40c674824bb763ea2087318423ca3677f506
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775128"
---
# <a name="deployment-overview"></a>Übersicht über die Bereitstellung

Die Bereitstellung von Microsoft Teams-Räumen gliedert sich im Wesentlichen in Phasen:

- Bestätigen, dass Ihre Bereitstellungs Standorte (Räume) die Bereitstellungs Abhängigkeiten erfüllen
- Erstellen von Microsoft Teams oder Skype for Business-und Exchange-Konten und Zuweisen dieser zu den Konsolen Geräten (siehe [Konfigurieren von Konten für Microsoft Teams-Räume](room-systems-v2-configure-accounts.md))
- Umbilden von Microsoft Surface Tablets zur Arbeit als Microsoft Teams-Chatrooms (siehe [Konfigurieren einer Microsoft Teams rooms-Konsole](console.md) oder [Bereitstellen von Microsoft Teams Room-Massen Bereitstellungshandbuch](room-systems-scale.md))
- Optional Einrichten von Microsoft Operations Management Suite für Ihre Systeme (siehe [Bereitstellen von Microsoft Teams rooms Management mit Azure Monitor](azure-monitor-deploy.md)
- Einrichten von Konsolen in Besprechungsräumen und Verbinden der benötigten Peripheriegeräte (siehe OEM-Dokumentation für Ihre Gerätegruppe)

AV-Techs können für die letzte Aufgabe verwendet werden, aber die IT-Abteilung Ihrer Organisation muss die anderen Teile des Prozesses durchführen. 


## <a name="site-readiness"></a>Website Bereitschaft 

Während die bestellten Geräte an Ihre Organisation geliefert werden, arbeiten Sie mit Ihrem Netzwerk und ihren Einrichtungen und AV-Teams zusammen, um sicherzustellen, dass die Bereitstellungs Abhängigkeiten erfüllt sind und jeder Standort und jeder Raum in Bezug auf Leistung, Netzwerk und Anzeige bereit ist. Stellen Sie außerdem sicher, dass die Anforderungen für die physische Installation erfüllt sind. Überlegungen zur physikalischen Installation finden Sie auf der Website des Anbieters und nutzen Sie die Erfahrung Ihres AV-Teams beim Installieren und montieren von Bildschirmen und beim Ausführen von Kabeln.

Weitere Informationen zu diesen Abhängigkeiten finden Sie in den folgenden Links zu den Planungsanleitungen:

-   [Überprüfen der Netzwerkverfügbarkeit](srs-v2-prep.md#check-network-availability) 
-   [Zertifikate](srs-v2-prep.md#certificates)
-   [Proxy](srs-v2-prep.md#proxy)

**Pro Tipp** : Wenn Sie beabsichtigen, Proxy Server für den Zugriff auf Microsoft Teams oder Skype for Business Online zu verwenden, [Lesen Sie diesen Artikel](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online)zuerst. Beachten Sie, dass es bei Skype for Business-Datenverkehr über Proxy-Server empfehlenswert ist, Proxy Server komplett zu umgehen. Skype for Business-Datenverkehr ist bereits verschlüsselt, sodass Proxy Server ihn nicht sicherer machen. Im Rahmen ihrer umfassenderen Bereitstellung empfehlen wir, dass Sie die Anleitungen unter [evaluieren meiner Umgebung](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) für die Bandbreitenplanung befolgen und die Eignung Ihres Netzwerks für den Echtzeitverkehr bewerten.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Vergewissern Sie sich, dass Ihre Websites die wichtigsten Anforderungen für Microsoft Teams-Chatrooms erfüllen.</li><li>Vergewissern Sie sich, dass Sie für jede Website genügend Bandbreite bereitgestellt haben.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung Ihrer Gerätebereitstellung und-Konfiguration.</li></ul>| 

## <a name="service-readiness"></a>Bereitschaft für den Dienst

Führen Sie die folgenden zentralen Aufgaben aus, um die Bereitstellung Ihrer Microsoft Teams-Räume vorzubereiten:

-   Definieren Sie die Features des Microsoft Teams rooms-Dienstkontos.
-   Vorbereiten einer Organisationseinheit und einer Active Directory-Gruppe, um die Computer-und Dienstkonten von Microsoft Teams Rooms zu speichern, und – optional – Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) vorzubereiten, um PowerShell-Remoting zu ermöglichen.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Definieren von Microsoft Teams rooms-Dienstkonto Features 

Je nach den Zusammenarbeitsszenarien, die Sie für die Bereitstellung in Microsoft Teams rooms aktivieren möchten, müssen Sie die Features und Funktionen ermitteln, die Sie jedem Microsoft Teams rooms-Dienstkonto zuweisen, das Sie aktivieren.

| **Szenario** | **Beschreibung** | **Microsoft Teams rooms-Dienstkonto Feature** |
|---------- |------------- | --- |
| Interaktive Besprechungen            | Verwenden von sprach-, Video-und Bildschirm Freigaben Bereitstellen von Microsoft Teams-Räumen als buchbare Ressource                     | Aktiviert für Skype for Business, aktiviert für Exchange (Ressourcenpostfach) |
| Einwahlkonferenzen            | Aktivieren von Besprechungen, die *direkt* von der Microsoft Teams rooms-Konsole aus mit Einwahlkonferenz Koordinaten gestartet wurden | Für Audiokonferenzen aktiviert                                          |
| Ausgehende/eingehende PSTN-Anrufe | Aktivieren der Microsoft Teams rooms-Konsole zum tätigen und empfangen von PSTN-anrufen                                         | Für Telefon System aktiviert                                                |

Weitere Informationen zu Microsoft Teams rooms-Konten finden Sie unter [Konfigurieren von Konten für Microsoft Teams-Chatrooms](room-systems-v2-configure-accounts.md).


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, welche Szenarien unterstützt werden sollen, und ermitteln Sie die Lizenzierungsanforderungen für Ihre Microsoft Teams rooms-Dienstkonten.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Vorbereiten des Hostens von Computer-und Dienstkonten</li></ul>| 


_Beispiel für die Planning-Tabelle des Microsoft Teams rooms-servicekontos_

| **Standort**  | **Name des Raums** | **Zimmerkategorie** | **Zukünftige Raumfunktionen**                                                 | **Microsoft Teams rooms-Konto Features**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| Londoner HQ | Curie         | Mittel        | 1 Bildschirm, Audio-und Video plus Präsentation <br>Zugriff auf Einwahlkonferenzen<br> PSTN-Zugriff  | Aktiviert für Skype for Business, aktiviert für Exchange (Ressourcenpostfach) <br>Für Audiokonferenzen aktiviert <br>Für Telefon System aktiviert |
| Sydney HQ | Hill          | Große         | 2 Bildschirme, Audio-und Video plus Präsentation<br>Zugriff auf Einwahlkonferenzen<br> PSTN-Zugriff  | Aktiviert für Skype for Business, aktiviert für Exchange (Ressourcenpostfach)<br> Für Audiokonferenzen aktiviert <br>Für Telefon System aktiviert |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Vorbereiten des Hostens von Microsoft Teams rooms-Maschinen-und Dienstkonten (optional)

Damit Sie Ihre Microsoft Teams rooms-Computer-und-Dienstkonten verwalten und melden können, bereiten Sie Ihr lokales Active Directory oder Azure Active Directory (Azure AD) vor. 

Definieren Sie eine lokale Active Directory-oder Azure Ad-Gruppe, um alle Konten von Microsoft Teams rooms Service (Benutzer) zu hinzuzufügen, und erstellen Sie dann Nutzungsberichte mithilfe des Cmdlets Get-CSUserSession PowerShell in der Bereitstellung von Microsoft Teams rooms. Erstellen Sie beispielsweise eine Gruppe mit dem Namen SkypeRoomSystemsv2-Service-Accounts. 


Definieren Sie eine Organisationseinheit in Ihrer lokalen Active Directory-oder Azure AD-Hierarchie, um alle Microsoft Teams rooms-Computerkonten (wenn Sie der Domäne beigetreten sind) und eine Organisationseinheit für alle Microsoft Teams rooms-Benutzerkonten zu speichern. Wenn Sie eine Organisationseinheit für die Microsoft Teams rooms-Computerkonten erstellen, sollten Sie die Vererbung deaktivieren, um sicherzustellen, dass Sie nur die Richtlinien anwenden, die Sie für die Domäne verwenden möchten, die zu den Microsoft Teams-Räumen beigetreten sind. 

Erstellen Sie ein Gruppenrichtlinienobjekt, das der Organisationseinheit zugeordnet ist, die Ihre Microsoft Teams rooms-Computerkonten enthält. Verwenden Sie Folgendes, um Folgendes zu tun: 

-   [Festlegen der Einstellungen für Energie und lokales Konto](room-systems-v2-operations.md#configuring-group-policy-for-microsoft-teams-rooms)
-   Aktivieren Sie Windows Update.
-   Aktivieren von PowerShell-Remoting Sie können ein Startskript so konfigurieren, dass ein einfaches Skript ausgeführt wird: enable-PSRemoting-Force

Sie können PowerShell zum Ausführen einer Reihe von Remote Verwaltungsaktivitäten verwenden, einschließlich Abrufen und Festlegen von Konfigurationsinformationen. PowerShell-Remoting muss aktiviert sein, *bevor* eine PowerShell-Remoteverwaltung durchgeführt werden kann, und sollte als Teil ihrer Bereitstellungsprozesse betrachtet oder über Gruppenrichtlinien konfiguriert werden. Weitere Informationen zu diesen Funktionen und deren Aktivierung finden Sie unter [Wartung und Vorgänge](room-systems-v2-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Konfiguration und Bereitstellung 

Die Planung für Konfiguration und Bereitstellung umfasst die folgenden Hauptbereiche:

-   Kontobereitstellung
-   Geräte Software Installation
-   Gerätebereitstellung
-   Microsoft Teams rooms-Konfiguration der Anwendungs-und Peripheriegeräte
-    Tests
-   Ressourcenverwaltung

### <a name="account-provisioning"></a>Kontobereitstellung 

Für jedes Microsoft Teams rooms-Gerät ist ein dediziertes und eindeutiges Ressourcenkonto erforderlich, das für Microsoft Teams oder Skype for Business und Exchange aktiviert sein muss. Dieses Konto muss über ein Chatroom-Postfach verfügen, das in Exchange gehostet wird, und als Besprechungsraum in der Microsoft Teams-oder Skype for Business-Bereitstellung aktiviert sein. Auf der Exchange-Seite muss die Kalenderverarbeitung so konfiguriert werden, dass das Gerät eingehende Besprechungsanfragen automatisch annehmen kann. Weitere Informationen zum Erstellen dieser Konten finden Sie unter [Konfigurieren von Konten für Microsoft Teams-Chatrooms](room-systems-v2-configure-accounts.md). 

**Pro-Tipp** : Stellen Sie die Anzeigenamen für diese Konten anschaulich und verständlich dar. Dies sind die Namen, die Benutzern beim Suchen und Hinzufügen von Microsoft Teams rooms-Systemen zu Besprechungen angezeigt werden. Einige Organisationen verwenden den*Namen*der Konventions *Website*-(*Max. Raumkapazität*)-RS, also beispielsweise Curie – einen 12-Personen-Konferenzraum in London – den Anzeigenamen Lon-Curie (12)-Rs. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie sich für die Benennungskonvention für Ihre Microsoft Teams rooms-Konten.</li><li>Entscheiden Sie, ob Sie einzelne Konten erstellen oder Massen Bereitstellungsskripts verwenden möchten.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung der Gerätebereitstellung.</li></ul>| 


### <a name="device-software-installation"></a>Geräte Software Installation 

Wenn Sie die Bereitstellung von Microsoft Teams-Räumen planen, haben Sie eine Reihe von Optionen, die Sie zum Installieren der erforderlichen Software in Frage stellen müssen. In der folgenden Tabelle werden häufige Szenarien und Ansätze beschrieben. 

| **Szenario**            | **Ansatz**         |
|-------------------------|-----------------------|   
|Bereitstelleneiner kleinen Anzahl von Microsoft Teams rooms-Geräten (<10). | Wenn Sie Surface pro-basierte Microsoft Teams-Räume verwenden, folgen Sie den [Installationsanweisungen für die Installation pro Gerät](console.md). [Dieses handliche Video führt Sie durch den Vorgang.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Wenn Sie eine integrierte Lösung verwenden, verwenden Sie das Image des Herstellers, und konfigurieren Sie die Einstellungen nach Bedarf. |
| Bereitstellen von 10-und 50-Geräten von einem einzelnen Anbieter.     | Erstellen Sie ein WIM-basiertes Bild, pausieren Sie nach [Schritt 6 in der Anleitung](console.md), und erfassen Sie ein Verteilungs Bild, das mit ihrer Verteilungstechnologie für das Klonen verwendet werden soll.    |
| Bereitstellen von mehr als 50 Microsoft Teams rooms-Geräten, Bereitstellen von Geräten von mehr als einem Anbieter oder Anfordern von organisationsspezifischen Agents als Teil der Bereitstellung. | Verwenden Sie eine auf Task Sequenzer basierende Software-Build-und-Verteilungsplattform, wie etwa [System Center Configuration Manager](room-systems-scale.md).  |

**Pro-Tipp** – jeder Microsoft Teams-Chatroom muss über einen gültigen und eindeutigen Computernamen in Ihrem Netzwerk verfügen. Viele Überwachungs-und Warnungssysteme zeigen den Computernamen als Schlüsselbezeichner an, daher ist es wichtig, eine Benennungskonvention für Microsoft Teams rooms-Bereitstellungen zu entwickeln, mit deren Hilfe das Supportpersonal problemlos nach den gekennzeichneten Microsoft Teams-Räumen suchen kann. eine Aktion erforderlich ist. Ein Beispiel ist möglicherweise die Verwendung eines Musters des MTR-*Site*-*Room Name* (MTR-Lon-Curie). 

Als Teil der Bereitstellung müssen Sie auch Ihre Strategie für die Verwaltung und Konfiguration der [lokalen Konten](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) in Frage stellen, die vom Installationsprogramm für Microsoft Teams rooms erstellt werden.

Wir bieten eine Anleitung zur Verwendung des [Microsoft Azure Monitors](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) , um die Bereitstellung von Microsoft Teams Rooms zu überwachen und auf Verfügbarkeit, Hardware/Softwarefehler und Microsoft Teams rooms-Anwendungsversion zu melden. Wenn Sie sich entschließen, Microsoft Operations Management Suite zu verwenden, sollten Sie den Operations Management Suite-Agent als Teil des Software Installationsprozesses installieren und die Arbeitsbereichs Verbindungsinformationen für Ihren Arbeitsbereich konfigurieren. 

Eine weitere Überlegung ist, ob die Microsoft Teams-Chatrooms Domänen verbunden sind. Informationen zu den Vorteilen einer Domänenmitgliedschaft finden Sie unter [Überlegungen zu den Domänenbeitritt von Skype Room System](domain-joining-considerations.md). 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie sich für die Microsoft Teams rooms-Geräte Benennungskonvention, die während der Bereitstellung verwendet werden soll.</li><li>Entscheiden Sie, ob Sie Microsoft Teams rooms-Geräten zu Ihrer Domäne beitreten möchten, und wie Sie lokale Konten verwalten und konfigurieren. </li><li>Entscheiden Sie, ob Sie die Operations Management Suite zum Überwachen der Microsoft Teams rooms-Bereitstellung verwenden werden.</li><li>Entscheiden Sie, welche Methode Sie für die Bereitstellung der Software und der Agents im Microsoft Teams Room-System zur Vorbereitung der Gerätebereitstellung verwenden werden. </li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung Ihres Geräte Bereitstellungsansatzes.</li></ul>| 


### <a name="device-deployment"></a>Gerätebereitstellung

Nachdem Sie Ihre Software in den Räumen von Microsoft Teams bereitgestellt haben, erstellen Sie Ihren Plan, um die Geräte und die Ihnen zugewiesenen Peripheriegeräte an Ihre Räume zu senden, und fahren Sie dann mit Installation und Konfiguration fort. 


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, wer die Site-by-Site-Bereitstellung verwalten soll.</li><li> Ermitteln Sie die Ressourcen, die die Microsoft Teams rooms-Geräte auf der Website installieren, und führen Sie die Konfiguration und Tests durch.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Starten Sie den Gerätetest.</li></ul>| 

_Beispiel Bereitstellungs Tabelle_

| **Standort**  | **Name des Raums** | **Zimmerkategorie** | **Microsoft Teams rooms-System**  | **Peripheriegeräte**  | **Microsoft Teams rooms-Computername**  | **Ressourcenkonto für Microsoft Teams rooms**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| Londoner HQ | Curie         | Mittel        |                                   |                  |                                          |                                             |
| Sydney HQ | Hill          | Große         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams rooms-Konfiguration der Anwendungs-und Peripheriegeräte 

Nachdem jedes Microsoft Teams rooms-System physisch bereitgestellt wurde und die unterstützten Peripheriegeräte verbunden sind, müssen Sie die Microsoft Teams rooms-Anwendung so konfigurieren, dass das zuvor erstellte Ressourcenkonto und Kennwort für Microsoft Teams rooms zugewiesen wird. , um das Microsoft Teams rooms-System für die Anmeldung bei Microsoft Teams oder Skype for Business und Exchange zu aktivieren. Der Schlüssel zur Nutzung von zertifizierten USB-Audio-und-Video-Peripheriegeräten, die an anderer Stelle im Dokument miteinander verbunden sind. Wenn Sie dies nicht tun, kann dies zu einem unvorhersehbaren Verhalten führen. 

Sie können jedes Microsoft Teams Room-System manuell konfigurieren. Alternativ können Sie eine zentral gespeicherte XML-Konfigurationsdatei für Microsoft Teams-Räume verwenden, um die Anwendungseinstellungen zu verwalten und ein Start-GPO-Skript zu nutzen, um die gewünschte Konfiguration jedes Mal erneut anzuwenden, wenn die Microsoft Teams rooms-System bootet. 

Weitere Informationen zum Verwenden der XML-Konfigurationsdatei finden Sie unter [Verwalten von Microsoft Teams rooms-Konsoleneinstellungen Remote mit einer XML-Konfigurationsdatei](xml-config-file.md). 

Sie können [Remote-PowerShell](room-systems-v2-operations.md#remote-management-using-powershell) verwenden, um die Microsoft Teams rooms-Konfiguration für Berichterstattungsanforderungen abzurufen. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Sie jedes Microsoft Teams Room-System manuell konfigurieren oder eine zentrale XML-Datei verwenden möchten (eine pro Microsoft Teams rooms-Gerät).</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Definieren Ihres Remote Verwaltungsansatzes</li></ul>| 

### <a name="testing"></a> Tests

Nachdem das Microsoft Teams rooms-System bereitgestellt wurde, sollten Sie es testen. Überprüfen Sie, ob die in [Microsoft Teams-Chatrooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) aufgeführten Funktionen auf dem bereitgestellten Gerät funktionieren. Wir empfehlen dringend, dass das Bereitstellungsteam überprüft, ob die Microsoft Teams-Räume in Microsoft Operations Management Suite (falls verwendet) angemeldet sind. Es ist auch wichtig, dass Sie eine Reihe von Testanrufen und Besprechungen vornehmen, um die Qualität zu überprüfen. Weitere Informationen finden Sie in dieser [hilfreichen Bereitstellungscheckliste](console.md#microsoft-teams-rooms-deployment-checklist).

Wir empfehlen, dass Sie im Rahmen der allgemeinen Teams oder des Skype for Business-Rollouts Bausteine für das Anruf Qualitäts Dashboard (CQD) konfigurieren, qualitätstrends überwachen und sich an der Prüfung der Qualität der Erfahrung beteiligen. Weitere Informationen finden Sie im [Leitfaden zur Überprüfung der Qualität der Benutzerfreundlichkeit](https://aka.ms/qerguide). 

### <a name="asset-management"></a>Ressourcenverwaltung

Als Teil der Bereitstellung sollten Sie Ihr Anlagenregister mit dem Raumnamen, dem Gerätenamen für Microsoft Teams rooms, dem Ressourcenkonto für signierte Microsoft Teams und den zugewiesenen Peripheriegeräten (und den verwendeten USB-Ports) aktualisieren. 

_Beispiel für eine Anlagentabelle_

| **Standort**  | **Name des Raums** | **Zimmerkategorie** | **Microsoft Teams rooms Serial-Nr.**  | **Peripheriegeräte/serielle Nummern/Anschlüsse**  | **Microsoft Teams rooms-Computername**  | **Microsoft Teams rooms-Dienstkonto**  | **Bereitstellungsdatum** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| Londoner HQ | Curie         | Mittel        |                                          |                                          |                                          |                                            |                   |
| Sydney HQ | Hill          | Große         |                                          |                                          |                                          |                                            |                   |


