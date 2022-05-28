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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: In diesem Artikel erfahren Sie, wie Sie Microsoft Teams-Räume bereitstellen, einschließlich der Bereitstellungsphasen.
ms.openlocfilehash: 0111e8723d70b753c2d8de64350387252db8f8f7
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760917"
---
# <a name="deployment-overview"></a>Übersicht über die Bereitstellung

Die Bereitstellung von Microsoft Teams-Räume gliedert sich im Wesentlichen in Phasen:

- Bestätigen, dass Ihre Bereitstellungsspeicherorte (Leerzeichen) den Bereitstellungsabhängigkeiten entsprechen
- Erstellen Microsoft Teams oder Skype for Business und Exchange Konten und Zuweisen zu Teams-Räume (siehe [Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md))
- (Optional) Einrichten von Azure Monitor für Ihre Systeme (siehe [Bereitstellen Microsoft Teams-Räume-Verwaltung mit Azure Monitor](azure-monitor-deploy.md)
- Einrichten Teams-Räume in Besprechungsräumen und Verbinden der benötigten Peripheriegeräte (siehe OEM-Dokumentation für Ihre Gerätegruppe)

## <a name="site-readiness"></a>Websitebereitschaft 

Während die bestellten Geräte an Ihre Organisation geliefert werden, arbeiten Sie mit Ihren Netzwerken, Einrichtungen und AV-Teams zusammen, um sicherzustellen, dass die Bereitstellungsabhängigkeiten erfüllt sind und jeder Standort und jeder Speicherplatz in Bezug auf Leistung, Netzwerk und Anzeige bereit ist. Stellen Sie außerdem sicher, dass die physischen Installationsanforderungen erfüllt sind. Für Überlegungen zur physischen Installation wenden Sie sich an Ihren Hersteller und nutzen Sie die Erfahrung Ihres AV-Teams bei der Installation und Montage von Bildschirmen und beim Ausführen von Verkabelungen.

Weitere Informationen zu diesen Abhängigkeiten finden Sie unter den folgenden Planungsleitfadenlinks:

-   [Überprüfen der Netzwerkverfügbarkeit](rooms-prep.md#check-network-availability)
-   [Zertifikate](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Pro Tipp**: Wenn Sie Proxyserver verwenden müssen, um Zugriff auf Teams zu ermöglichen, lesen Sie zuerst [diesen Artikel](../proxy-servers-for-skype-for-business-online.md). Wenn es um Microsoft Teams Echtzeitmediendatenverkehr über Proxyserver geht, empfehlen wir, Proxyserver vollständig zu umgehen. Microsoft Teams Datenverkehr ist bereits verschlüsselt, sodass Proxyserver ihn nicht sicherer machen und latenzen den Echtzeitdatenverkehr erhöhen. Im Rahmen Ihrer breiteren Bereitstellung empfehlen wir Ihnen, die Anleitungen unter ["Vorbereiten Ihres Netzwerks für Teams](../prepare-network.md) für die Bandbreitenplanung und die Bewertung der Eignung Ihres Netzwerks für Echtzeitdatenverkehr" zu befolgen.

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![Websites bestätigen.](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Vergewissern Sie sich, dass Ihre Websites die wichtigsten Anforderungen für Microsoft Teams-Räume erfüllen.</li><li>Vergewissern Sie sich, dass Sie für jeden Standort ausreichende Bandbreite bereitgestellt haben.</li></ul>| 
| ![Planen der Gerätebereitstellung.](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung der Gerätebereitstellung und -konfiguration.</li></ul>| 

## <a name="service-readiness"></a>Bereitschaft für den Dienst

Führen Sie die folgenden wichtigen zentralen Aufgaben aus, um sich auf ihre Microsoft Teams-Räume Bereitstellung vorzubereiten:

-   Definieren sie Microsoft Teams-Räume Ressourcenkonten.
-   Wenn Sie Teams-Räume Azure Active Directory beitreten, bereiten Sie eine Azure AD-Gruppe mit dynamischer Mitgliedschaft vor, um alle Teams-Räume Ressourcenkonten zu speichern. Dadurch wird die zukünftige Verwaltung vereinfacht, z. B. das Anwenden von Richtlinien für bedingten Zugriff. Um dynamische Azure AD-Gruppen am einfachsten zu nutzen, bestimmen Sie eine Benennungskonvention, die Ihre Teams-Räume Ressourcenkonten eindeutig identifiziert.
-   Wenn Sie Teams-Räume mit Active Directory verbinden, bereiten Sie eine Organisationseinheit und Eine Active Directory-Gruppe so vor, dass sie Ihre Microsoft Teams-Räume Computer- und Ressourcenkonten enthalten, und bereiten Sie optional Gruppenrichtlinie Objekte (GPOs) vor, um PowerShell-Remoting zu aktivieren.

### <a name="define-microsoft-teams-rooms-resource-account-features"></a>Definieren Microsoft Teams-Räume Ressourcenkontofeatures 

Abhängig von den Szenarien für die Zusammenarbeit, die Sie mit Ihrer Microsoft Teams-Räume-Bereitstellung aktiviert haben, müssen Sie die Features und Funktionen ermitteln, die Sie den einzelnen Microsoft Teams-Räume zuweisen, die Sie aktivieren.

| **Szenario** | **Beschreibung** | **Microsoft Teams-Räume-Dienstkontofeature** |
|---------- |------------- | --- |
| Interaktive Besprechungen            | Verwenden von Sprach-, Video- und Bildschirmfreigabe; Das Microsoft Teams-Räume zu einer buchbaren Ressource machen                     | Aktiviert für Microsoft Teams oder Skype for Business; aktiviert für Exchange (Ressourcenpostfach) |
| Einwahlkonferenzen            | Haben Sie eine Audiokonferenztelefonnummer, wenn Sie auf der Konsole auf "Neue Besprechung" tippen | Aktiviert für Audiokonferenz                                          |
| Ausgehende/eingehende PSTN-Anrufe | Aktivieren der Microsoft Teams-Räume Konsole zum Tätigen und Empfangen von PSTN-Anrufen                                         | Aktiviert für Telefonsystem                                                |

Weitere Informationen zu Microsoft Teams-Räume-Konten finden [Sie unter Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md).


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![Szenariounterstützung.](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, welche Szenarien Unterstützt werden, und ermitteln Sie die Lizenzierungsanforderungen für Ihre Microsoft Teams-Räume Ressourcenkonten.</li></ul>| 
| ![Vorbereiten des Hostcomputers.](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Vorbereiten des Hostens von Computer- und Ressourcenkonten.</li></ul>| 


_Beispieltabelle für Microsoft Teams-Räume Ressourcenkontoplanung_

| **Standort**  | **Raumname** | **Raumtyp** | **Zukünftige Raumfunktionen**                                                 | **Microsoft Teams-Räume Kontofeatures**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| London HQ | Curie         | Mittel        | 1 Bildschirm, Audio und Video plus Präsentation <br>Zugriff auf Einwahlkonferenzen<br> PSTN-Zugriff  | Aktiviert für Exchange (Ressourcenpostfach) <br>Aktiviert für Audiokonferenz <br>Aktiviert für Telefonsystem |
| Sydney HQ | Hill          | Groß         | 2 Bildschirme, Audio und Video plus Präsentation<br>Zugriff auf Einwahlkonferenzen<br> PSTN-Zugriff  | Aktiviert für Skype for Business <br>Aktiviert für Exchange (Ressourcenpostfach)<br> Aktiviert für Audiokonferenz <br>Aktiviert für Telefonsystem |


### <a name="prepare-to-host-microsoft-teams-rooms-and-resource-accounts-optional"></a>Vorbereiten des Hostens von Microsoft Teams-Räume- und Ressourcenkonten (optional)

Damit Sie Ihre Microsoft Teams-Räume- und Ressourcenkonten verwalten und melden können, bereiten Sie Ihre lokales Active Directory oder Azure Active Directory (Azure AD) vor. 

Definieren Sie eine lokales Active Directory oder Azure Active Directory Gruppe, der alle Microsoft Teams-Räume Ressourcenkonten hinzugefügt werden sollen. Wenn Sie Azure Active Directory verwenden, erwägen Sie die Verwendung einer dynamischen Gruppe, um ressourcenkonten automatisch der Gruppe hinzuzufügen und daraus zu entfernen.

Definieren Sie eine Organisationseinheit in Ihrer lokales Active Directory Hierarchie, um alle Microsoft Teams-Räume Computerkonten (wenn sie der Domäne beigetreten sind) und eine Organisationseinheit für alle Microsoft Teams-Räume Benutzerkonten zu speichern. Deaktivieren Sie Gruppenrichtlinie Vererbung, um sicherzustellen, dass Sie nur die Richtlinien anwenden, die Sie auf die in die Domäne eingebundene Microsoft Teams-Räume anwenden möchten.

Erstellen Sie ein Gruppenrichtlinie Objekt, das der Organisationseinheit zugewiesen ist, die Ihre Microsoft Teams-Räume Computerkonten enthält. Verwenden Sie dies für Folgendes: 

-   [Legen Sie Einstellungen für das Netz und das lokale Konto fest](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms).
-   Aktivieren Sie Windows Update.
-   Aktivieren Sie PowerShell-Remoting. Sie können ein Startskript so konfigurieren, dass ein Skript ausgeführt wird: Enable-PSRemoting -Force

Sie können PowerShell verwenden, um mehrere Remoteverwaltungsaktivitäten auszuführen, einschließlich Abrufen und Festlegen von Konfigurationsinformationen. PowerShell-Remoting muss aktiviert sein, *bevor* eine PowerShell-Remoteverwaltung stattfinden kann, und sollte als Teil Ihrer Bereitstellungsprozesse betrachtet oder über Gruppenrichtlinie konfiguriert werden. Weitere Informationen zu diesen Funktionen und deren Aktivierung finden Sie unter [Wartung und Betrieb](rooms-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Konfiguration und Bereitstellung 

Die Planung der Konfiguration und Bereitstellung umfasst die folgenden Schlüsselbereiche:

-   Ressourcenkontobereitstellung
-   Installation von Gerätesoftware
-   Gerätebereitstellung
-   Microsoft Teams-Räume Der Anwendungs- und Peripheriegerätekonfiguration
-    Tests
-   Ressourcenverwaltung

### <a name="resource-account-provisioning"></a>Ressourcenkontobereitstellung 

Jedes Microsoft Teams-Räume Gerät erfordert ein dediziertes und eindeutiges Ressourcenkonto, das sowohl für Microsoft Teams als auch für Skype for Business und Exchange aktiviert werden muss. Dieses Konto muss über ein Raumpostfach verfügen, das auf Exchange gehostet wird. Die Kalenderverarbeitung muss so konfiguriert werden, dass das Gerät eingehende Besprechungsanfragen automatisch annehmen kann. Weitere Informationen zum Erstellen dieser Konten finden Sie unter [Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md). 

**Pro Tipp** : Jede Microsoft Teams-Räume muss einen gültigen und eindeutigen Computernamen in Ihrem Netzwerk haben. Viele Überwachungs- und Benachrichtigungssysteme zeigen den Computernamen als Schlüsselbezeichner an. Daher ist es wichtig, eine Benennungskonvention für Microsoft Teams-Räume Bereitstellungen zu entwickeln, die es Supportmitarbeitern ermöglicht, die Microsoft Teams-Räume, die als aktionsbedürftig gekennzeichnet wurden, leicht zu finden. Ein Beispiel kann die Verwendung eines Musters von *MTR-Site*-*Room Name* (MTR-LON-CURIE) sein. 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![die Benennungskonvention zu bestimmen.](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Legen Sie die Benennungskonvention für Ihre Microsoft Teams-Räume-Ressourcenkonten fest.</li><li>Entscheiden Sie, ob Sie einzelne Konten erstellen oder Massenbereitstellungsskripts verwenden möchten.</li></ul>| 
| ![Nächste Schritte.](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung der Gerätebereitstellung.</li></ul>| 


### <a name="device-software-installation"></a>Installation von Gerätesoftware 

Teams-Räume wird vom Originalgerätehersteller (OEM) vorinstalliert.

Wir bieten Anleitungen zur Verwendung [von Microsoft Azure Monitor](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor), um die Microsoft Teams-Räume Bereitstellung zu überwachen und über Verfügbarkeit, Hardware-/Softwarefehler und Microsoft Teams-Räume Anwendungsversion zu berichten. Wenn Sie sich für die Verwendung von Microsoft Operations Management Suite entscheiden, sollten Sie den Operations Management Suite-Agent im Rahmen des Softwareinstallationsprozesses installieren und die Arbeitsbereichverbindungsinformationen für Ihren Arbeitsbereich konfigurieren. 

Eine weitere Überlegung ist, ob die Microsoft Teams-Räume in die Domäne eingebunden wird. Informationen zu den Vorteilen des Domänenbeitritts finden Sie unter [Configuring Gruppenrichtlinie for Microsoft Teams-Räume](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms). 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![Decision Points Gerätebenennung.](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Legen Sie die Benennungskonvention für Microsoft Teams-Räume Ressourcenkonto fest, die während der Bereitstellung verwendet werden soll.</li><li>Entscheiden Sie, ob Sie Microsoft Teams-Räume Geräten mit Ihrer Domäne verknüpfen möchten. </li><li>Entscheiden Sie, ob Sie Azure Monitor verwenden, um die Microsoft Teams-Räume Bereitstellung zu überwachen.</li> 
| ![Nächste Schritte: Gerät planen.](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung Ihres Gerätebereitstellungsansatzes.</li></ul>| 


### <a name="device-deployment"></a>Gerätebereitstellung

Nachdem Sie sich entschieden haben, wie Sie Ihre Microsoft Teams-Räume-Ressourcenkonten erstellen und verwalten, erstellen Sie Ihren Plan zum Versenden der Geräte und ihrer zugewiesenen Peripheriegeräte an Ihre Räume, und fahren Sie dann mit der Installation und Konfiguration fort.


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![Die Bereitstellung von Standort zu Standort verwalten.](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, wer die Bereitstellung von Standort zu Standort verwaltet.</li><li> Identifizieren Sie die Ressourcen, die Microsoft Teams-Räume vor Ort installieren, und führen Sie die Konfiguration und die Tests durch.</li></ul>| 
| ![Starten Sie Gerätetests.](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Starten Sie Gerätetests.</li></ul>| 

_Beispiel für eine Bereitstellungstabelle_

| **Standort**  | **Raumname** | **Raumtyp** | **Microsoft Teams-Räume System**  | **Peripheriegeräte**  | **Microsoft Teams-Räume Computername**  | **Microsoft Teams-Räume Ressourcenkonto**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| London HQ | Curie         | Mittel        |                                   |                  |                                          |                                             |
| Sydney HQ | Hill          | Groß         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams-Räume Der Anwendungs- und Peripheriegerätekonfiguration 

Nachdem jedes Microsoft Teams-Räume System physisch bereitgestellt und die unterstützten Peripheriegeräte verbunden wurden, müssen Sie die Microsoft Teams-Räume Anwendung so konfigurieren, dass das Microsoft Teams-Räume Ressourcenkonto und das Kennwort zugewiesen werden, um Teams-Räume, um sich bei Microsoft Teams oder Skype for Business anzumelden, und Exchange.

Sie können jedes Microsoft Teams-Räume System manuell konfigurieren. Alternativ können Sie eine zentral gespeicherte XML-Konfigurationsdatei pro Teams-Räume verwenden, um die Anwendungseinstellungen zu verwalten.

Weitere Informationen zur Verwendung der XML-Konfigurationsdatei finden [Sie unter "Remoteverwaltung einer Microsoft Teams-Räume Konsoleneinstellungen mit einer XML-Konfigurationsdatei.For more information about how to use the XML configuration file, see Manage a Microsoft Teams-Räume console settings remotely with an XML configuration file](xml-config-file.md). 

Sie können [Remote-PowerShell](rooms-operations.md#remote-management-using-powershell) verwenden, um die Microsoft Teams-Räume-Konfiguration für Berichtsanforderungen abzuziehen. 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![Decision Point Configure.](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Sie jedes Microsoft Teams-Räume System manuell konfigurieren oder eine zentrale XML-Datei (eine pro Microsoft Teams-Räume Gerät) verwenden möchten.</li></ul>| 
| ![Nächste Schritte: Remote-Ansatz.](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Definieren Sie Ihren Remoteverwaltungsansatz.</li></ul>| 

### <a name="testing"></a> Tests

Nachdem Teams-Räume bereitgestellt wurde, sollten Sie es testen. Überprüfen Sie, ob die in [Microsoft Teams-Räume Hilfe](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2?ui=en-us&rs=en-us&ad=us) aufgeführten Funktionen auf dem bereitgestellten Gerät funktionieren. Es wird dringend empfohlen, dass das Bereitstellungsteam überprüft, ob Microsoft Teams-Räume im Teams Admin Center angezeigt wird. Es ist auch wichtig, dass Sie eine Reihe von Testanrufen und Besprechungen durchführen, um die Qualität zu überprüfen. Weitere Informationen finden Sie in dieser [nützlichen Bereitstellungscheckliste](console.md#microsoft-teams-rooms-deployment-checklist).

Es wird empfohlen, im Rahmen des allgemeinen Teams oder Skype for Business Rollouts die Erstellung von Dateien für das Anrufqualitätsdashboard (Call Quality Dashboard, CQD) zu konfigurieren, Qualitätstrends zu überwachen und sich an der Überprüfung der Qualität der Erfahrung zu beteiligen. Weitere Informationen finden Sie unter [Verbessern und Überwachen der Anrufqualität für Teams](../monitor-call-quality-qos.md). 

### <a name="asset-management"></a>Ressourcenverwaltung

Im Rahmen der Bereitstellung sollten Sie Ihr Ressourcenregister mit dem Raumnamen, Microsoft Teams-Räume Namen, Microsoft Teams-Räume Ressourcenkonto und zugewiesenen Peripheriegeräten aktualisieren. 

_Beispielobjekttabelle_

| **Standort**  | **Raumname** | **Raumtyp** | **Microsoft Teams-Räume seriennummernnr.**  | **Peripheriegeräte/Seriennummern./Ports**  | **Microsoft Teams-Räume Computername**  | **Microsoft Teams-Räume-Dienstkonto**  | **Bereitstellungsdatum** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| London HQ | Curie         | Mittel        |                                          |                                          |                                          |                                            |                   |
| Sydney HQ | Hill          | Groß         |                                          |                                          |                                          |                                            |                   |
