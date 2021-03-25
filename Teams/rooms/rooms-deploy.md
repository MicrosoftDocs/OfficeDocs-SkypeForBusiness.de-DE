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
description: In diesem Artikel erfahren Sie, wie Sie Microsoft Teams Rooms bereitstellen, einschließlich der Bereitstellungsphasen.
ms.openlocfilehash: 3ac6ceabd1d421551ab3b9404688bd4a9302e3d6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117463"
---
# <a name="deployment-overview"></a>Übersicht über die Bereitstellung

Die Bereitstellung von Microsoft Teams Rooms bricht im Wesentlichen in Phasen auf:

- Bestätigen, dass Ihre Bereitstellungsstandorte (Räume) den Bereitstellungsabhängigkeiten entsprechen
- Erstellen von Microsoft Teams- oder Skype for Business- und Exchange-Konten und Zuweisen dieser Konten zu Konsolengeräten (siehe Konfigurieren von Konten [für Microsoft Teams-Räume](rooms-configure-accounts.md))
- Erneutes Microsoft Surface von Tablets für die Verwendung als Microsoft Teams Rooms-Konsolen (siehe Konfigurieren einer [Microsoft Teams Rooms-Konsole](console.md) oder [Bereitstellen von Microsoft Teams Rooms –Massenbereitstellungshandbuch)](rooms-scale.md)
- (Optional) Einrichten der Microsoft Operations Management Suite für Ihre Systeme (siehe Bereitstellen der Verwaltung von [Microsoft Teams-Räumen mit Azure Monitor](azure-monitor-deploy.md)
- Einrichten von Konsolen in Besprechungsräumen und Anschließen der benötigten Peripheriegeräte (siehe OEM-Dokumentation für Ihre Gerätegruppe)

Av-Techs können für die letzte Aufgabe verwendet werden, aber die IT-Abteilung Ihrer Organisation muss die anderen Teile des Prozesses übernehmen. 


## <a name="site-readiness"></a>Websitebereitschaft 

Während die bestellten Geräte an Ihre Organisation geliefert werden, arbeiten Sie mit Ihren Netzwerken und Einrichtungen und AV-Teams zusammen, um sicherzustellen, dass Die Bereitstellungsabhängigkeiten erfüllt werden und jede Website und jeder Raum hinsichtlich Leistung, Netzwerk und Anzeige bereit ist. Stellen Sie außerdem sicher, dass die Anforderungen für die physische Installation erfüllt sind. Aus Gründen der physischen Installation besuchen Sie die Website des Herstellers, und nutzen Sie die Benutzererfahrung Ihres AV-Teams, wenn Sie Bildschirme installieren und installieren und Verkabelungen ausführen.

Weitere Informationen zu diesen Abhängigkeiten finden Sie unten in den Links zu Planungsleitfäden:

-   [Überprüfen der Netzwerkverfügbarkeit](rooms-prep.md#check-network-availability)
-   [Zertifikate](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Tipp pro** : Wenn Sie Proxyserver verwenden möchten, um Zugriff auf Teams oder Skype for Business Online zu ermöglichen, lesen Sie [zuerst diesen Artikel.](../proxy-servers-for-skype-for-business-online.md) Wenn es um Skype for Business-Datenverkehr über Proxyserver geht, empfehlen wir, Proxyserver vollständig zu umgehen. Der Skype for Business-Datenverkehr ist bereits verschlüsselt, sodass Proxyserver ihn nicht sicherer machen. Im Rahmen Ihrer breiteren Bereitstellung empfehlen wir, die Anleitung unter Vorbereiten Ihres Netzwerks für [Teams](../prepare-network.md) für die Bandbreitenplanung und die Bewertung der Eignung Ihres Netzwerks für den Echtzeitdatenverkehr zu befolgen.

|    |     |
|-----------|------------|
| ![Bestätigen von Websites](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Vergewissern Sie sich, dass Ihre Websites die wichtigsten Anforderungen für Microsoft Teams Rooms erfüllen.</li><li>Vergewissern Sie sich, dass Sie für jede Website eine ausreichende Bandbreite bereitgestellt haben.</li></ul>| 
| ![Planen der Gerätebereitstellung](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung der Gerätebereitstellung und -konfiguration.</li></ul>| 

## <a name="service-readiness"></a>Bereitschaft für den Dienst

Zum Vorbereiten der Bereitstellung von Microsoft Teams Rooms müssen Sie die folgenden zentralen Aufgaben ausführen:

-   Definieren Sie Microsoft Teams Rooms-Dienstkontofeatures.
-   Bereiten Sie eine Organisationseinheit und eine Active Directory-Gruppe so vor, dass Sie Ihre Microsoft Teams Rooms-Computer- und Dienstkonten speichern, und bereiten Sie – optional – Gruppenrichtlinienobjekte (Gruppenrichtlinienobjekte) vor, um das PowerShell-Remoting zu aktivieren.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Definieren von Microsoft Teams Rooms-Dienstkontofeatures 

Je nach den Szenarien für die Zusammenarbeit, die Sie mit Ihrer Microsoft Teams Rooms-Bereitstellung aktivieren möchten, müssen Sie die Features und Funktionen ermitteln, die Sie jedem von Ihnen aktivierten Microsoft Teams Rooms-Dienstkonto zuweisen.

| **Szenario** | **Beschreibung** | **Dienstkontofeature von Microsoft Teams Rooms** |
|---------- |------------- | --- |
| Interaktive Besprechungen            | Verwenden von Sprach-, Video- und Bildschirmfreigaben Machen der Microsoft Teams Rooms zu einer buchbaren Ressource                     | Aktiviert für Skype for Business, aktiviert für Exchange (Ressourcenpostfach) |
| Einwahlkonferenzen            | Aktivieren von *Besprechungen, die direkt* über die Microsoft Teams Rooms-Konsole gestartet werden, mit Einwahlkonferenzkoordinaten | Für Audiokonferenzen aktiviert                                          |
| Ausgehende/eingehende PSTN-Anrufe | Aktivieren der Microsoft Teams Rooms-Konsole zum Starten und Empfangen von PSTN-Anrufen                                         | Aktiviert für Telefonsystem                                                |

Weitere Informationen zu Microsoft Teams Rooms-Konten finden Sie unter [Konfigurieren von Konten für Microsoft Teams Rooms](rooms-configure-accounts.md).


|    |     |
|-----------|------------|
| ![Szenariounterstützung](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, welche Szenarien Sie unterstützen, und ermitteln Sie die Lizenzierungsanforderungen für Ihre Microsoft Teams Rooms-Dienstkonten.</li></ul>| 
| ![Vorbereiten des Hostcomputers](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Vorbereiten des Hostens von Computer- und Dienstkonten</li></ul>| 


_Beispiel für eine Tabelle zur Planung von Microsoft Teams Rooms-Dienstkontos_

| **Standort**  | **Raumname** | **Raumtyp** | **Zukünftige Raumfunktionen**                                                 | **Microsoft Teams Rooms-Kontofeatures**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| London HQ | Curie         | Mittel        | 1 Bildschirm, Audio und Video plus Präsentation <br>Zugriff auf Einwahlkonferenzen<br> PSTN-Zugriff  | Aktiviert für Skype for Business, aktiviert für Exchange (Ressourcenpostfach) <br>Für Audiokonferenzen aktiviert <br>Aktiviert für Telefonsystem |
| Sydney HQ | Hill          | Groß         | 2 Bildschirme, Audio und Video plus Präsentation<br>Zugriff auf Einwahlkonferenzen<br> PSTN-Zugriff  | Aktiviert für Skype for Business, aktiviert für Exchange (Ressourcenpostfach)<br> Für Audiokonferenzen aktiviert <br>Aktiviert für Telefonsystem |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Vorbereiten des Hostens von Computer- und Dienstkonten für Microsoft Teams Rooms (optional)

Damit Sie Ihre Computer- und Dienstkonten von Microsoft Teams Rooms verwalten und melden können, bereiten Sie Ihr lokales Active Directory oder Azure Active Directory (Azure AD) vor. 

Definieren Sie ein lokales Active Directory oder eine Azure AD-Gruppe, um alle Microsoft Teams Rooms-Dienstkonten (Benutzerkonten) hinzuzufügen, und erstellen Sie dann Nutzungsberichte mithilfe des Get-CSUserSession PowerShell-Cmdlets für Ihre Microsoft Teams Rooms-Bereitstellung. Erstellen Sie beispielsweise eine Gruppe mit dem Namen SkypeRoomSystemsv2-Service-Accounts. 


Definieren Sie eine Organisationseinheit in Ihrer lokalen Active Directory- oder Azure AD-Hierarchie, um alle Microsoft Teams Rooms-Computerkonten (wenn sie der Domäne beigetreten sind) und eine Organisationseinheit für alle Microsoft Teams Rooms-Benutzerkonten zu halten. Wenn Sie eine Organisationseinheit für die Microsoft Teams Rooms-Computerkonten erstellen, sollten Sie die Vererbung deaktivieren, um sicherzustellen, dass Sie nur die Richtlinien anwenden, die Sie auf die mit der Domäne verbundenen Microsoft Teams Rooms anwenden möchten. 

Erstellen Sie ein Gruppenrichtlinienobjekt, das der Organisationseinheit zugewiesen ist, die Ihre Microsoft Teams Rooms-Computerkonten enthält. Verwenden Sie dies für: 

-   [Legen Sie die Einstellungen für Strom und lokale Konten ein.](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)
-   Aktivieren Sie Windows Update.
-   Aktivieren sie das PowerShell-Remoting. Sie können ein Startskript für die Ausführung eines Skripts konfigurieren: Enable-PSRemoting -Force

Sie können PowerShell verwenden, um mehrere Remoteverwaltungsaktivitäten durchzuführen, einschließlich abrufen und Festlegen von Konfigurationsinformationen. PowerShell-Remoting muss  aktiviert sein, bevor eine PowerShell-Remoteverwaltung stattfinden kann und als Teil Ihrer Bereitstellungsprozesse betrachtet oder über Gruppenrichtlinien konfiguriert werden sollte. Weitere Informationen zu diesen Funktionen und deren Aktivierung finden Sie unter [Wartung und Vorgänge.](rooms-operations.md#remote-management-using-powershell) 


## <a name="configuration-and-deployment"></a>Konfiguration und Bereitstellung 

Die Planung der Konfiguration und Bereitstellung umfasst die folgenden Schlüsselbereiche:

-   Kontobereitstellung
-   Installation von Gerätesoftware
-   Gerätebereitstellung
-   Konfiguration von Microsoft Teams Rooms für Anwendungen und Peripheriegeräte
-    Tests
-   Ressourcenverwaltung

### <a name="account-provisioning"></a>Kontobereitstellung 

Jedes Microsoft Teams Rooms-Gerät erfordert ein dediziertes und eindeutiges Ressourcenkonto, das sowohl für Microsoft Teams als auch für Skype for Business und Exchange aktiviert werden muss. Dieses Konto muss über ein in Exchange gehostetes Raumpostfach verfügen und als Besprechungsraum in der Bereitstellung von Teams oder Skype for Business aktiviert sein. Auf der Exchange-Seite muss die Kalenderverarbeitung konfiguriert werden, damit das Gerät eingehende Besprechungsanfragen automatisch annehmen kann. Weitere Informationen zum Erstellen dieser Konten finden Sie unter [Konfigurieren von Konten für Microsoft Teams Rooms](rooms-configure-accounts.md). 

**Pro-Tipp** – Machen Sie die Anzeigenamen für diese Konten beschreibend und leicht verständlich. Dies sind die Namen, die Benutzern angezeigt werden, wenn sie nach Microsoft Teams Rooms-Systemen suchen und sie zu Besprechungen hinzufügen. Einige Organisationen verwenden den Websiteraumnamen der Konvention ( Max. Raumkapazität )-RS, sodass z. B. Curie – ein Konferenzraum mit 12 Personen in London – den Anzeigenamen - LON-CURIE(12)-RS haben kann. 

|    |     |
|-----------|------------|
| ![Benennungskonvention entscheiden](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie die Benennungskonvention für Ihre Microsoft Teams Rooms-Konten.</li><li>Entscheiden Sie, ob Sie einzelne Konten erstellen oder Massenbereitstellungsskripts verwenden.</li></ul>| 
| ![Nächste Schritte](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung der Gerätebereitstellung.</li></ul>| 


### <a name="device-software-installation"></a>Installation von Gerätesoftware 

Bei der Planung der Bereitstellung von Microsoft Teams Rooms gibt es viele Möglichkeiten, die erforderliche Software zu installieren. Allgemeine Szenarien und Ansätze werden in der folgenden Tabelle beschrieben. 

| **Szenario**            | **Ansatz**         |
|-------------------------|-----------------------|   
|Bereitstellen von einigen Microsoft Teams Rooms-Geräten (<10). | Wenn Sie Surface Pro Microsoft Teams Rooms verwenden, folgen Sie den Installationsanweisungen für eine [Geräteinstallation.](console.md) [Dieses praktische Video führt Sie durch den Prozess.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Wenn Sie eine integrierte Lösung verwenden, stellen Sie die Bereitstellung mithilfe des Lieferantenimages ein, und konfigurieren Sie die Einstellungen nach Bedarf. |
| Bereitstellen zwischen 10 und 50 Geräten von einem einzigen Anbieter.     | Erstellen Sie ein WIM-basiertes Bild, halten Sie nach Schritt [6 in](console.md)der Anleitung an, und erfassen Sie ein Verteilungsbild, das mit Ihrer Klonverteilungstechnologie verwendet werden soll.    |
| Bereitstellen von mehr als 50 Microsoft Teams Rooms-Geräten, Bereitstellen von Geräten von mehreren Lieferanten oder Anforderung organisationsspezifischer Agents als Teil der Bereitstellung. | Verwenden Sie eine Tasksequenzer-basierte Software-Build- und -Verteilungsplattform, z. B. [Microsoft Endpoint Configuration Manager.](rooms-scale.md)  |


**Pro Tipp:** Jeder Microsoft Teams Rooms muss einen gültigen und eindeutigen Computernamen in Ihrem Netzwerk haben. Viele Überwachungs- und Benachrichtigungssysteme zeigen den Computernamen als Schlüsselbezeichner an, daher ist es wichtig, eine Benennungskonvention für Microsoft Teams Rooms-Bereitstellungen zu entwickeln, die es den Supportmitarbeitern ermöglicht, die Microsoft Teams-Räume, für die eine Aktion erforderlich ist, auf einfache Weise zu finden. Ein Beispiel könnte ein Muster von MTR-*Site* - *Room Name* (MTR-LON-CURIE) sein. 

Im Rahmen der Bereitstellung müssen Sie auch Ihre Strategie zum Verwalten [](/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) und Konfigurieren der lokalen Konten berücksichtigen, die vom Microsoft Teams Rooms-Anwendungsinstallationsprogramm erstellt werden.

Wir bieten Anleitungen zur Verwendung des [Microsoft Azure Monitors](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) zum Überwachen der Bereitstellung von Microsoft Teams Rooms und zum Melden von Verfügbarkeit, Hardware-/Softwarefehlern und Microsoft Teams Rooms-Anwendungsversion. Wenn Sie sich für die Verwendung der Microsoft Operations Management Suite entscheiden, sollten Sie den Operations Management Suite-Agent im Rahmen des Softwareinstallationsprozesses installieren und die Informationen zur Arbeitsbereichsverbindung für Ihren Arbeitsbereich konfigurieren. 

Eine weitere Überlegung ist, ob die Microsoft Teams Rooms der Domäne beigetreten sind. Informationen zu den Vorteilen der Domänenan beitreten finden Sie unter Überlegungen zum Beitreten zu Domänen in [Skype Room System.](domain-joining-considerations.md) 

|    |     |
|-----------|------------|
| ![Entscheidungspunkte für Gerätebenennung](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie die Microsoft Teams Rooms-Gerätebenennungskonvention, die während der Bereitstellung verwendet werden soll.</li><li>Entscheiden Sie, ob Sie Microsoft Teams Rooms-Geräten zu Ihrer Domäne beitreten und wie Lokale Konten verwaltet und konfiguriert werden. </li><li>Entscheiden Sie, ob Sie die Operations Management Suite verwenden, um die Bereitstellung von Microsoft Teams Rooms zu überwachen.</li><li>Entscheiden Sie, welche Methode Sie zur Bereitstellung der Software und der Agents im Microsoft Teams Rooms-System in Vorbereitung auf die Gerätebereitstellung verwenden. </li></ul>| 
| ![Plangerät für die nächsten Schritte](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung Ihres Gerätebereitstellungsansatzes.</li></ul>| 


### <a name="device-deployment"></a>Gerätebereitstellung

Nachdem Sie Ihre Software in den Microsoft Teams Rooms-Einheiten bereitgestellt haben, erstellen Sie Ihren Plan, die Geräte und deren zugewiesenen Peripheriegeräte in Ihre Räume zu versenden, und fahren Sie dann mit der Installation und Konfiguration fort. 


|    |     |
|-----------|------------|
| ![Verwalten der Bereitstellung von Website zu Website](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, wer die Bereitstellung von Website zu Website verwaltet.</li><li> Identifizieren Sie die Ressourcen, die die Microsoft Teams Rooms-Geräte auf der Website installieren, und übernehmen Sie die Konfiguration und tests.</li></ul>| 
| ![Starten von Gerätetests](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Starten Sie den Gerätetest.</li></ul>| 

_Beispielbereitstellungstabelle_

| **Standort**  | **Raumname** | **Raumtyp** | **Microsoft Teams Rooms System**  | **Peripheriegeräte**  | **Microsoft Teams Rooms Computername**  | **Microsoft Teams Rooms-Ressourcenkonto**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| London HQ | Curie         | Mittel        |                                   |                  |                                          |                                             |
| Sydney HQ | Hill          | Groß         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Konfiguration von Microsoft Teams Rooms für Anwendungen und Peripheriegeräte 

Nachdem jedes Microsoft Teams Rooms-System physisch bereitgestellt und die unterstützten Peripheriegeräte verbunden wurden, müssen Sie die Microsoft Teams Rooms-Anwendung so konfigurieren, dass sie das zuvor erstellte Microsoft Teams Rooms-Ressourcenkonto und das Kennwort zuzuordnen, damit sich das Microsoft Teams Rooms-System bei Microsoft Teams oder Skype for Business und Exchange anmelden kann. Es ist wichtig, zertifizierte USB-Audio- und Videoperipheriegeräte zu nutzen, die an anderer Stelle im Dokument verknüpft sind. Wenn Sie dies nicht tun, kann dies zu einem unvorhersehbaren Verhalten führen. 

Sie können jedes Microsoft Teams Rooms-System manuell konfigurieren. Alternativ können Sie eine zentral gespeicherte XML-Konfigurationsdatei pro Microsoft Teams Rooms verwenden, um die Anwendungseinstellungen zu verwalten und ein Start-Up-GPO-Skript zu verwenden, um die von Ihnen bestimmte Konfiguration bei jedem Start des Microsoft Teams Rooms-Systems erneut zu verwenden. 

Weitere Informationen zur Verwendung der XML-Konfigurationsdatei finden Sie unter Verwalten einer Microsoft Teams Rooms-Konsoleneinstellungen remote [mit einer XML-Konfigurationsdatei.](xml-config-file.md) 

Sie können [Remote-PowerShell verwenden,](rooms-operations.md#remote-management-using-powershell) um die Microsoft Teams Rooms-Konfiguration für die Berichterstellungsanforderungen zu verwenden. 

|    |     |
|-----------|------------|
| ![Entscheidungspunkt konfigurieren](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Sie jedes Microsoft Teams Rooms-System manuell konfigurieren oder eine zentrale XML-Datei verwenden (eine pro Microsoft Teams Rooms-Gerät).</li></ul>| 
| ![Remoteansatz für die nächsten Schritte](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Definieren Sie Ihren Remoteverwaltungsansatz.</li></ul>| 

### <a name="testing"></a> Tests

Nachdem das Microsoft Teams Rooms-System bereitgestellt wurde, sollten Sie es testen. Überprüfen Sie, ob die in [der Microsoft Teams Rooms-Hilfe aufgeführten](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) Funktionen auf dem bereitgestellten Gerät funktionieren. Es wird dringend empfohlen, dass das Bereitstellungsteam überprüft, ob sich die Microsoft Teams Rooms bei der Microsoft Operations Management Suite anmelden (sofern verwendet). Es ist auch wichtig, dass Sie eine Reihe von Testanrufen und Besprechungen machen, um die Qualität zu überprüfen. Weitere Informationen finden Sie in dieser [nützlichen Bereitstellungscheckliste.](console.md#microsoft-teams-rooms-deployment-checklist)

Wir empfehlen, im Rahmen des allgemeinen Rollouts von Teams oder Skype for Business das Erstellen von Dateien für das Anrufqualitätsdashboard (CQD) zu konfigurieren, Qualitätstrends zu überwachen und sich am Überprüfungsprozess für die Qualität der Benutzererfahrung zu beteiligen. Weitere Informationen finden Sie unter [Verbessern und Überwachen der Anrufqualität für Teams.](../monitor-call-quality-qos.md) 

### <a name="asset-management"></a>Ressourcenverwaltung

Im Rahmen der Bereitstellung möchten Sie Ihr Ressourcenregister mit dem Raumnamen, dem Microsoft Teams Rooms-Gerätenamen, dem angemeldeten Microsoft Teams Rooms-Ressourcenkonto und den zugewiesenen Peripheriegeräten (und den verwendeten USB-Ports) aktualisieren. 

_Beispielwerttabelle_

| **Standort**  | **Raumname** | **Raumtyp** | **Microsoft Teams Rooms serial no.**  | **Peripheriegeräte/ Serielle Nos./Ports**  | **Microsoft Teams Rooms Computername**  | **Microsoft Teams Rooms-Dienstkonto**  | **Bereitgestelltes Datum** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| London HQ | Curie         | Mittel        |                                          |                                          |                                          |                                            |                   |
| Sydney HQ | Hill          | Groß         |                                          |                                          |                                          |                                            |                   |