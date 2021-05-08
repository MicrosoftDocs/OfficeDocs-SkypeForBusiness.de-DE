---
title: Bereitstellen von Microsoft Teams-Räume
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: In diesem Artikel erfahren Sie, wie Sie Microsoft Teams-Räume bereitstellen, einschließlich der Bereitstellungsphasen.
ms.openlocfilehash: 3ac6ceabd1d421551ab3b9404688bd4a9302e3d6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117463"
---
# <a name="deployment-overview"></a>Übersicht über die Bereitstellung

Die Bereitstellung Microsoft Teams-Räume im Wesentlichen in Phasen auf:

- Bestätigen, dass Ihre Bereitstellungsstandorte (Räume) den Bereitstellungsabhängigkeiten entsprechen
- Erstellen Microsoft Teams oder Skype for Business und Exchange Konten und Zuweisen dieser Konten zu Konsolengeräten (siehe Konfigurieren von Konten [für Microsoft Teams-Räume](rooms-configure-accounts.md))
- Neuimieren Microsoft Surface Tablets für die Verwendung als Microsoft Teams-Räume-Konsolen (siehe Konfigurieren einer [Microsoft Teams-Räume-Konsole](console.md) oder bereitstellen [Microsoft Teams-Räume Handbuch zur Massenbereitstellung)](rooms-scale.md)
- (Optional) Einrichten der Microsoft Operations Management Suite für Ihre Systeme (siehe [Bereitstellen Microsoft Teams-Räume Verwaltung mit Azure Monitor](azure-monitor-deploy.md)
- Einrichten von Konsolen in Besprechungsräumen und Anschließen der benötigten Peripheriegeräte (siehe OEM-Dokumentation für Ihre Gerätegruppe)

FÜR die letzte Aufgabe können AV-Techniker verwendet werden, aber die IT-Abteilung Ihrer Organisation muss die anderen Teile des Prozesses übernehmen. 


## <a name="site-readiness"></a>Websitebereitschaft 

Während die bestellten Geräte an Ihre Organisation übermittelt werden, arbeiten Sie mit Ihren Netzwerken und Einrichtungen und AV-Teams zusammen, um sicherzustellen, dass die Bereitstellungsabhängigkeiten erfüllt sind und jede Website und jeder Raum hinsichtlich Leistung, Netzwerk und Anzeige bereit ist. Stellen Sie außerdem sicher, dass die Anforderungen für die physische Installation erfüllt sind. Besuchen Sie aus Gründen der physischen Installation die Website des Herstellers, und nutzen Sie die Erfahrungen Ihres AV-Teams beim Installieren und Installieren von Bildschirmen und Ausführen der Verkabelung.

Weitere Informationen zu diesen Abhängigkeiten finden Sie unter den Links für den Planungsleitfade:

-   [Überprüfen der Netzwerkverfügbarkeit](rooms-prep.md#check-network-availability)
-   [Zertifikate](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Pro Tipp:** Wenn Sie Proxyserver verwenden möchten, um Zugriff auf Teams oder Skype for Business Online zu ermöglichen, lesen Sie zuerst [diesen Artikel.](../proxy-servers-for-skype-for-business-online.md) Wenn es um Skype for Business Proxyserver geht, empfehlen wir, die Proxyserver vollständig zu umgehen. Skype for Business Datenverkehr bereits verschlüsselt ist, sorgen Proxyserver nicht für mehr Sicherheit. Im Rahmen der breiteren Bereitstellung sollten Sie den Anweisungen unter Vorbereiten Ihres Netzwerks für [Teams](../prepare-network.md) für die Bandbreitenplanung und Bewerten der Eignung Ihres Netzwerks für Echtzeitdatenverkehr folgen.

|    |     |
|-----------|------------|
| ![Bestätigen von Websites](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Vergewissern Sie sich, dass Ihre Websites die wichtigsten Anforderungen für die Microsoft Teams-Räume.</li><li>Vergewissern Sie sich, dass Sie für jeden Standort ausreichend Bandbreite bereitgestellt haben.</li></ul>| 
| ![Planen der Gerätebereitstellung](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung der Gerätebereitstellung und -konfiguration.</li></ul>| 

## <a name="service-readiness"></a>Bereitschaft für den Dienst

Um sich auf die Microsoft Teams-Räume Bereitstellung vorzubereiten, gehen Sie wie folgt vor: Zentrale Aufgaben:

-   Definieren Microsoft Teams-Räume Dienstkontofunktionen.
-   Bereiten Sie eine Organisationseinheit und eine Active Directory-Gruppe für den Halteraum Ihres Microsoft Teams-Räume-Computer- und -Dienstkontos vor, und bereiten Sie optional Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) vor, um die PowerShell-Entfernung zu aktivieren.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Definieren Microsoft Teams-Räume Dienstkontofunktionen 

Abhängig von den Szenarien für die Zusammenarbeit, die Sie für Ihre Microsoft Teams-Räume-Bereitstellung aktiviert haben, müssen Sie die Features und Funktionen ermitteln, die Sie jedem Microsoft Teams-Räume-Dienstkonto zuweisen, das Sie aktivieren.

| **Szenario** | **Beschreibung** | **Microsoft Teams-Räume eines Dienstkontos** |
|---------- |------------- | --- |
| Interaktive Besprechungen            | Verwenden von Sprache, Video und Bildschirmfreigabe Das -Microsoft Teams-Räume zu einer buchbaren Ressource machen                     | Aktiviert für Skype for Business, aktiviert für Exchange (Ressourcenpostfach) |
| Einwahlkonferenzen            | Aktivieren von *Besprechungen, die direkt* über die Microsoft Teams-Räume-Konsole mit Einwahlkonferenzkoordinaten gestartet werden | Aktiviert für Audiokonferenzen                                          |
| Ausgehende/eingehende PSTN-Anrufe | Aktivieren der Microsoft Teams-Räume für das Anrufen und Empfangen von PSTN-Anrufen                                         | Aktiviert für Telefonsystem                                                |

Weitere Informationen zu Microsoft Teams-Räume-Konten finden Sie unter [Konfigurieren von Konten für Microsoft Teams-Räume.](rooms-configure-accounts.md)


|    |     |
|-----------|------------|
| ![Szenariounterstützung](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, welche Szenarien Unterstützt werden sollen, und identifizieren Sie die Lizenzierungsanforderungen für Ihre Microsoft Teams-Räume-Dienstkonten.</li></ul>| 
| ![Vorbereiten des Hostcomputers](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Bereiten Sie das Hosten von Computer- und Dienstkonten vor.</li></ul>| 


_Beispiel für Microsoft Teams-Räume Servicekontoplanungstabelle_

| **Standort**  | **Name des Raum** | **Raumtyp** | **Zukünftige Raumfunktionen**                                                 | **Microsoft Teams-Räume kontofeatures**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| London HQ | Curie         | Mittel        | 1 Bildschirm, Audio und Video plus Präsentation <br>Zugriff auf Einwahlkonferenzen<br> PSTN-Zugriff  | Aktiviert für Skype for Business, aktiviert für Exchange (Ressourcenpostfach) <br>Aktiviert für Audiokonferenzen <br>Aktiviert für Telefonsystem |
| Sydney HQ | Hill          | Groß         | 2 Bildschirme, Audio und Video plus Präsentation<br>Zugriff auf Einwahlkonferenzen<br> PSTN-Zugriff  | Aktiviert für Skype for Business, aktiviert für Exchange (Ressourcenpostfach)<br> Aktiviert für Audiokonferenzen <br>Aktiviert für Telefonsystem |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Vorbereiten des Hosts Microsoft Teams-Räume Computer- und Dienstkonten (optional)

Um es Ihnen zu ermöglichen, Ihre Microsoft Teams-Räume Computer- und Dienstkonten zu verwalten und zu melden, bereiten Sie Ihr lokales Active Directory oder Ihre lokale Azure Active Directory (Azure AD) vor. 

Definieren Sie ein lokales Active Directory oder eine Azure AD-Gruppe, um alle Microsoft Teams-Räume-Dienstkonten (Benutzerkonten) hinzuzufügen, und erstellen Sie dann Verwendungsberichte mithilfe des Get-CSUserSession PowerShell-Cmdlets Microsoft Teams-Räume Bereitstellung. Erstellen Sie z. B. eine Gruppe mit dem Namen SkypeRoomSystemsv2-Service-Accounts. 


Definieren Sie eine Organisationseinheit in Ihrer lokalen Active Directory- oder Azure AD-Hierarchie für alle Microsoft Teams-Räume-Computerkonten (wenn diese der Domäne beigetreten sind) und eine Organisationseinheit für alle Microsoft Teams-Räume-Benutzerkonten. Wenn Sie eine Organisationseinheit für die Microsoft Teams-Räume-Computerkonten erstellen, sollten Sie die Vererbung deaktivieren, um sicherzustellen, dass Sie nur die Richtlinien anwenden, die Sie auf die Domäne anwenden möchten, die der Domäne beigetreten Microsoft Teams-Räume. 

Erstellen Sie ein Gruppenrichtlinienobjekt, das der Organisationseinheit zugeordnet ist, die Ihre Microsoft Teams-Räume-Computerkonten enthält. Verwenden Sie diese Für: 

-   [Legen Sie die Einstellungen für ein lokales und ein lokales Konto auf](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms).
-   Aktivieren Windows Aktualisieren.
-   Aktivieren Sie die PowerShell-Entfernung. Sie können ein Startskript für die Ausführung eines Skripts konfigurieren: Enable-PSRemoting -Force

Sie können PowerShell verwenden, um mehrere Remoteverwaltungsaktivitäten durchzuführen, darunter das Abrufen und Festlegen von Konfigurationsinformationen. Die PowerShell-Entfernung muss aktiviert werden, bevor eine PowerShell-Remoteverwaltung stattfinden kann und als Teil Ihrer Bereitstellungsprozesse betrachtet oder über Gruppenrichtlinien konfiguriert werden sollte.  Weitere Informationen zu diesen Funktionen und zu deren Aktivierung finden Sie unter [Wartung und Vorgänge.](rooms-operations.md#remote-management-using-powershell) 


## <a name="configuration-and-deployment"></a>Konfiguration und Bereitstellung 

Die Planung der Konfiguration und Bereitstellung umfasst die folgenden Hauptbereiche:

-   Kontobereitstellung
-   Installation von Gerätesoftware
-   Gerätebereitstellung
-   Microsoft Teams-Räume der Konfiguration von Anwendungen und Peripheriegeräten
-    Tests
-   Postenverwaltung

### <a name="account-provisioning"></a>Kontobereitstellung 

Jedes Microsoft Teams-Räume benötigt ein dediziertes und eindeutiges Ressourcenkonto, das sowohl für Microsoft Teams als Skype for Business als auch für Exchange. Dieses Konto muss über ein Raumpostfach verfügen, das auf Exchange gehostet wird, und als Besprechungsraum in der Besprechungs- Teams oder Skype for Business aktiviert sein. Auf der Exchange Muss die Kalenderverarbeitung konfiguriert werden, damit das Gerät eingehende Besprechungsanfragen automatisch annehmen kann. Weitere Informationen zum Erstellen dieser Konten finden Sie unter [Konfigurieren von Konten für Microsoft Teams-Räume.](rooms-configure-accounts.md) 

**Pro Tipp:** Sorgen Sie dafür, dass die Anzeigenamen für diese Konten aussagekräftig und leicht verständlich sind. Dies sind die Namen, die Benutzern angezeigt werden, wenn sie Nach Besprechungen suchen und Microsoft Teams-Räume System hinzufügen. Einige Organisationen verwenden die Veranstaltung Websiteraumname ( Max. Raumkapazität )-RS, daher könnte - Curie, ein 12-Personen-Konferenzraum in London, beispielsweise den Anzeigenamen LON-CURIE(12)-RS haben. 

|    |     |
|-----------|------------|
| ![Benennungskonvention festlegen](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie die Namenskonvention für Ihre Microsoft Teams-Räume Konten.</li><li>Entscheiden Sie, ob Sie einzelne Konten erstellen oder Massenbereitstellungsskripts verwenden möchten.</li></ul>| 
| ![Nächste Schritte](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung der Gerätebereitstellung.</li></ul>| 


### <a name="device-software-installation"></a>Installation von Gerätesoftware 

Bei der Planung der Microsoft Teams-Räume haben Sie viele Optionen, die Sie in Betracht ziehen können, die erforderliche Software zu installieren. Allgemeine Szenarien und Ansätze werden in der folgenden Tabelle beschrieben. 

| **Szenario**            | **Ansatz**         |
|-------------------------|-----------------------|   
|Bereitstellen von einigen Microsoft Teams-Räume (<10). | Wenn Sie Surface Pro-basierte Microsoft Teams-Räume, befolgen Sie die Installationsanweisungen für eine [gerätebezogene Installation.](console.md) [Dieses praktische Video führt Sie durch den Prozess.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Wenn Sie eine integrierte Lösung verwenden, stellen Sie die Bereitstellung mithilfe des Anbieterbilds vor, und konfigurieren Sie die Einstellungen nach Bedarf. |
| Bereitstellung von 10 bis 50 Geräten von einem einzigen Anbieter.     | Erstellen Sie ein WIM-basiertes Bild, halten Sie nach Schritt [6 in](console.md)der Anleitung an, und erfassen Sie ein Verteilungsbild zur Verwendung mit der Klonverteilungstechnologie.    |
| Bereitstellen von mehr als 50 Microsoft Teams-Räume Geräten, Bereitstellen von Geräten von mehr als einem Anbieter oder Anforderung von organisationsspezifischen Agents als Teil der Bereitstellung. | Verwenden Sie eine Tasksequenz-basierte Software-Build- und -Verteilungsplattform, z. [B. Microsoft Endpoint Configuration Manager](rooms-scale.md).  |


**Pro Tipp:** Jedes Microsoft Teams-Räume muss einen gültigen und eindeutigen Computernamen in Ihrem Netzwerk haben. Viele Überwachungs- und Warnsysteme zeigen den Computernamen als Schlüsselbezeichner an. Daher ist es wichtig, eine Benennungskonvention für Microsoft Teams-Räume-Bereitstellungen zu entwickeln, die es den Supportmitarbeitern ermöglicht, die als Handlungsaufbehalt gekennzeichnete Microsoft Teams-Räume auf einfache Weise zu finden. Ein Beispiel könnte die Verwendung einesMtR-Site - *Room Name* (MTR-LON-CURIE) sein. 

Im Rahmen der Bereitstellung müssen Sie auch Ihre Strategie zum Verwalten [](/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) und Konfigurieren der lokalen Konten berücksichtigen, die vom Installationsprogramm Microsoft Teams-Räume werden.

Wir bieten Anleitungen zur Verwendung des [Microsoft Azure-Monitors](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) zum Überwachen der Microsoft Teams-Räume-Bereitstellung und zum Melden der Verfügbarkeit, von Hardware-/Softwarefehlern und Microsoft Teams-Räume Anwendungsversion. Wenn Sie sich für die Verwendung der Microsoft Operations Management Suite entscheiden, sollten Sie den Agent der Operations Management Suite im Rahmen des Softwareinstallationsprozesses installieren und die Arbeitsbereichsverbindungsinformationen für Ihren Arbeitsbereich konfigurieren. 

Eine zusätzliche Überlegung ist, ob die Microsoft Teams-Räume der Domäne beigetreten ist. Informationen zu den Vorteilen der Teilnahme an Domänen finden Sie in den Skype [zur Teilnahme an Domänen im Raumsystem.](domain-joining-considerations.md) 

|    |     |
|-----------|------------|
| ![Entscheidungspunkte für die Gerätebenennung](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie Microsoft Teams-Räume, welche Gerätebenennungskonvention während der Bereitstellung verwendet werden soll.</li><li>Entscheiden Sie, ob Sie Ihrer Domäne Microsoft Teams-Räume und wie Sie lokale Konten verwalten und konfigurieren möchten. </li><li>Entscheiden Sie, ob Sie die Operations Management Suite verwenden, um die Bereitstellung Microsoft Teams-Räume überwachen.</li><li>Entscheiden Sie, mit welcher Methode Sie die Software und Agents auf dem Microsoft Teams-Räume-System bereitstellen möchten, um die Gerätebereitstellung zu vorbereiten. </li></ul>| 
| ![Planen des Geräts für die nächsten Schritte](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung Ihres Gerätebereitstellungsansatzes.</li></ul>| 


### <a name="device-deployment"></a>Gerätebereitstellung

Nachdem Sie Ihre Software in den Microsoft Teams-Räume-Einheiten bereitgestellt haben, erstellen Sie Ihren Plan, um die Geräte und die ihnen zugewiesenen Peripheriegeräte an Ihre Räume zu versenden, und fahren Sie dann mit der Installation und Konfiguration fort. 


|    |     |
|-----------|------------|
| ![Verwalten der Bereitstellung von Website zu Website](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, wer die Bereitstellung von Website zu Website verwalten soll.</li><li> Ermitteln Sie die Ressourcen, die die Microsoft Teams-Räume-Geräte auf der Website installieren sollen, und übernehmen Sie die Konfiguration und Tests.</li></ul>| 
| ![Starten von Gerätetests](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Starten Sie die Gerätetests.</li></ul>| 

_Beispiel für eine Bereitstellungstabelle_

| **Standort**  | **Name des Raum** | **Raumtyp** | **Microsoft Teams-Räume System**  | **Peripheriegeräte**  | **Microsoft Teams-Räume Computername**  | **Microsoft Teams-Räume Ressourcenkonto**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| London HQ | Curie         | Mittel        |                                   |                  |                                          |                                             |
| Sydney HQ | Hill          | Groß         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams-Räume der Konfiguration von Anwendungen und Peripheriegeräten 

Nachdem jedes Microsoft Teams-Räume-System physisch bereitgestellt wurde und die unterstützten Peripheriegeräte angeschlossen wurden, müssen Sie die Microsoft Teams-Räume-Anwendung so konfigurieren, dass sie das zuvor erstellte Microsoft Teams-Räume-Ressourcenkonto und das zuvor erstellte Kennwort zuzuordnen, damit sich das Microsoft Teams-Räume-System bei Microsoft Teams oder Skype for Business und Exchange anmelden kann. Es ist wichtig, zertifizierte USB-Audio- und Videoperipheriegeräte zu nutzen, die an anderer Stelle im Dokument verknüpft sind. Wenn Sie dies nicht tun, kann dies zu unvorhergesehenem Verhalten führen. 

Sie können die einzelnen Microsoft Teams-Räume konfigurieren. Alternativ können Sie eine zentral gespeicherte, pro Microsoft Teams-Räume XML-Konfigurationsdatei gespeicherte Datei verwenden, um die Anwendungseinstellungen zu verwalten, und ein Start-GPO-Skript verwenden, um die von Ihnen jeweils Microsoft Teams-Räume-System zu starten. 

Weitere Informationen zur Verwendung der XML-Konfigurationsdatei finden Sie unter Remoteverwaltung [einer Microsoft Teams-Räume-Konsoleneinstellungen mit einer XML-Konfigurationsdatei.](xml-config-file.md) 

Sie können [Remote-PowerShell verwenden,](rooms-operations.md#remote-management-using-powershell) um die Microsoft Teams-Räume zur Berichterstellungsanforderungen zu ziehen. 

|    |     |
|-----------|------------|
| ![Entscheidungspunkt konfigurieren](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Sie jedes System manuell Microsoft Teams-Räume oder eine zentrale XML-Datei verwenden möchten (eine pro Microsoft Teams-Räume Gerät).</li></ul>| 
| ![Remoteansatz für die nächsten Schritte](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Definieren Sie den Ansatz für die Remoteverwaltung.</li></ul>| 

### <a name="testing"></a> Tests

Nachdem das Microsoft Teams-Räume bereitgestellt wurde, sollten Sie es testen. Überprüfen Sie, ob die in der Microsoft Teams-Räume [aufgeführten](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) Funktionen auf dem bereitgestellten Gerät funktionieren. Es wird dringend empfohlen, dass das Bereitstellungsteam überprüft, Microsoft Teams-Räume bei der Microsoft Operations Management Suite (falls verwendet) protokollieren wird. Außerdem ist es wichtig, dass Sie eine Reihe von Testanrufen und -besprechungen absprechen, um die Qualität zu überprüfen. Weitere Informationen finden Sie in dieser [hilfreichen Prüfliste für die Bereitstellung.](console.md#microsoft-teams-rooms-deployment-checklist)

Wir empfehlen, dass Sie im Rahmen des allgemeinen Teams- oder Skype for Business-Rollouts Gebäudedateien für das Anrufqualitätsdashboard konfigurieren, Qualitätstrends überwachen und sich für den Prozess zur Überprüfung der Qualität der Benutzererfahrung engagieren. Weitere Informationen finden Sie unter [Verbessern und Überwachen der Anrufqualität für Teams.](../monitor-call-quality-qos.md) 

### <a name="asset-management"></a>Postenverwaltung

Im Rahmen der Bereitstellung sollten Sie Ihr Ressourcenregister mit dem Raumnamen, dem Microsoft Teams-Räume-Gerätenamen, dem angemeldeten Microsoft Teams-Räume-Ressourcenkonto und den zugewiesenen Peripheriegeräten (und den verwendeten USB-Ports) aktualisieren. 

_Beispiel für eine Objekttabelle_

| **Standort**  | **Name des Raum** | **Raumtyp** | **Microsoft Teams-Räume Seriennummer.**  | **Peripheriegeräte/Seriennummern/Ports**  | **Microsoft Teams-Räume Computername**  | **Microsoft Teams-Räume-Dienstkonto**  | **Bereitgestelltes Datum** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| London HQ | Curie         | Mittel        |                                          |                                          |                                          |                                            |                   |
| Sydney HQ | Hill          | Groß         |                                          |                                          |                                          |                                            |                   |