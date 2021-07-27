---
title: SBA für Direct Routing
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Erfahren Sie mehr über Direct Routing, z. B. über die Konfiguration, notwendige grundlegende Entscheidungen zur Bereitstellung und Überlegungen zum VoIP-Routing.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d6342f41b3cd4bfad690794c0b6474ca45e78c8
ms.sourcegitcommit: bdd9901db1fc741aaec9c7ddcf5ee1caaca4d777
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52589239"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>Survivable Branch Appliance (SBA) für Direct Routing


Gelegentlich kann es an einem Kundenstandort, an dem Direct Routing zum Herstellen einer Verbindung mit dem Microsoft-Telefonsystem verwendet wird, zu einem Internetausfall kommen.

Angenommen, am Kundenstandort (dieser wird als "Branch" bezeichnet) kann vorübergehend keine Verbindung mit der Microsoft-Cloud über Direct Routing hergestellt werden. Das Intranet innerhalb des Branchs ist jedoch weiterhin voll funktionsfähig, und die Benutzer können eine Verbindung mit dem Session Border Controller (SBC) herstellen, der PSTN-Konnektivität bereitstellt.

In diesem Artikel wird beschrieben, wie Sie eine Survivable Branch Appliance (SBA) verwenden können, damit im Falle eines Ausfalls weiterhin das Tätigen und Empfangen von Festnetzanrufen (Public Switched Telephone Network, PSTN) über das Microsoft-Telefonsystem möglich ist.

## <a name="prerequisites"></a>Voraussetzungen

Bei einer SBA handelt es sich um verteilbaren Code, der von Microsoft für SBC-Anbieter bereitgestellt wird, die dann Code in ihre Firmware einbetten oder separat verteilen, damit die SBA auf einem separaten virtuellen Computer oder separater Hardware ausgeführt wird. 

Wenden Sie sich an Ihren SBC-Anbieter, um die neueste SBC-Firmware mit eingebetteter Survivable Branch Appliance zu erhalten. Darüber hinaus ist Folgendes erforderlich:

- Der SBC muss für die Medienumgehung konfiguriert werden, damit der Microsoft Teams-Client am Branch-Standort Medien direkt über den SBC übertragen kann. 

- Auf dem Betriebssystem des virtuellen SBA-Computers muss TLS1.2 aktiviert sein.

## <a name="supported-teams-clients"></a>Unterstützte Microsoft Teams-Clients

Das SBA-Feature wird auf den folgenden Microsoft Teams-Clients unterstützt: 

- Microsoft Teams Windows-Desktop 

- Microsoft Teams macOS-Desktop 

## <a name="how-it-works"></a>So funktioniert es

Während eines Internetausfalls sollte der Microsoft Teams-Client automatisch zur SBA wechseln, und laufende Anrufe sollten ohne Unterbrechungen fortgesetzt werden können. Es ist keine Aktion seitens der Benutzer erforderlich. Sobald der Microsoft Teams-Client erkennt, dass das Internet wieder verfügbar ist und alle ausgehenden Anrufe abgeschlossen sind, wird er zum normalen Betriebsmodus zurückkehren und eine Verbindung mit anderen Microsoft Teams-Diensten herstellen. Die SBA lädt erfasste Anrufdatensätze in die Cloud hoch und der Anrufverlauf wird aktualisiert, sodass diese Informationen vom Mandantenadministrator überprüft werden können. 

Wenn sich der Microsoft Teams-Client im Offlinemodus befindet, sind die folgenden Anruffunktionen verfügbar: 

- Tätigen von Festnetzanrufen über lokale SBA/SBC, Medien werden dabei über SBC übertragen.

- Empfangen von Festnetzanrufen über lokale SBA/SBC, Medien werden dabei über SBC übertragen. 

- Halten und Fortsetzen von Festnetzanrufen.

## <a name="configuration"></a>Konfiguration

Damit das SBA-Feature funktioniert, muss der Microsoft Teams-Client wissen, welche SBAs an jedem Branch-Standort verfügbar sind und welche SBAs den Benutzern an diesem Standort zugewiesen sind. Dies sind die erforderlichen Bereitstellungsschritte:

1. Erstellen der SBAs
2. Erstellen der Branch-Survivability-Richtlinie für Microsoft Teams
3. Benutzern die Richtlinie zuweisen
4. Registrieren einer Anwendung für die SBA bei Azure Active Directory

Die gesamte Konfiguration erfolgt mithilfe von Skype for Business Online PowerShell-Cmdlets. (Das Direct Routing-SBA-Feature wird im Microsoft Teams Admin Center noch nicht unterstützt.) 

(Informationen zum Konfigurieren des SBC und Links zu den Dokumentationen der SBC-Anbieter finden Sie unter "Konfiguration des Session Border Controllers" am Ende dieses Artikels.)

### <a name="create-the-sbas"></a>Erstellen der SBAs

Zum Erstellen der SBAs wird das Cmdlet "New-CsTeamsSurvivableBranchAppliance" verwendet. In diesem Cmdlet gibt es die folgenden Parameter:

| Parameter| Beschreibung |
| :------------|:-------|
| Identity  | Identität der Datenbank  |
| Fqdn | FQDN der SBA |
| Site | Die TenantNetworkSite, an dem sich der SBA befindet |
| Description | Frei formatierbarer Text |
|||

Zum Beispiel:

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Erstellen der Branch-Survivability-Richtlinie für Microsoft Teams 

Zum Erstellen einer Richtlinie wird das Cmdlet "New-CsTeamsSurvivableBranchAppliancePolicy" verwendet. In diesem Cmdlet gibt es die nachstehenden Parameter. Beachten Sie, dass die Richtlinie eine oder mehrere SBAs umfassen kann.

| Parameter| Beschreibung |
| :------------|:-------|
| Identity | Die Identität der Richtlinie |
| BranchApplianceFqdns  | Der FQDN der SBA(s) am Standort |
||

Zum Beispiel:

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

Sie können SBAs mithilfe des Cmdlets "Set-CsTeamsSurvivableBranchAppliancePolicy" zu einer Richtlinie hinzufügen oder daraus entfernen. Zum Beispiel: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Einem Benutzer eine Richtlinie zuweisen

Um die Richtlinie einzelnen Benutzern zuzuweisen, wird das Cmdlet "Grant-CsTeamsSurvivableBranchAppliancePolicy" verwendet. In diesem Cmdlet gibt es die folgenden Parameter:

| Parameter| Beschreibung |
| :------------|:-------|
| Identity | Die Identität des Benutzers |
| PolicyName | Die Identität der Richtlinie |
||

Zum Beispiel:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

Sie können eine Richtlinie von einem Benutzer entfernen, indem Sie die "$Null"-Richtlinie zuordnen, wie im nächsten Beispiel gezeigt:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Registrieren einer Anwendung für die SBA bei Azure Active Directory

Damit verschiedene in Ihrem Mandanten verwendete SBAs die notwendigen Daten aus Microsoft 365 auslesen können, müssen Sie eine Anwendung für die SBA bei Azure Active Directory registrieren. 

Weitere Informationen zur Registrierung von Anwendungen finden Sie in den folgenden Beiträgen:

- [Entwickeln branchenspezifischer Apps für Azure Active Directory](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Registrieren einer Anwendung bei der Microsoft Identity Platform](/azure/active-directory/develop/quickstart-register-app)  

Sie müssen nur eine Anwendung für die Verwendung durch alle SBAs in Ihrem Mandanten registrieren. 

Für die SBA-Registrierung benötigen Sie die folgenden Werte, die bei der Registrierung erstellt werden: 

- Anwendungs-ID (Client-ID) 
- Geheimer Clientschlüssel 

Beachten Sie im Hinblick auf die SBA-Anwendung Folgendes: 

- Sie können einen beliebigen Namen auswählen.  
- Unterstützte Kontotypen: Nur Konten in diesem Organisationsverzeichnis 
- Web-Umleitungs-URI: https://login.microsoftonline.com/common/oauth2/nativeclient
- Implizite Gewährung, Token: Zugriffstoken und ID-Token 
- API-Berechtigungen = Skype- und Microsoft Teams-Mandantenadministratorzugriff -> Anwendungsberechtigungen -> application_access_custom_sba_appliance.
- Geheimer Clientschlüssel: Sie können eine beliebige Beschreibung und einen beliebigen Ablaufzeitpunkt angeben. 
- Denken Sie daran, den geheimen Clientschlüssel sofort nach der Erstellung zu kopieren. 
- Die Anwendungs-ID (Client-ID) wird auf der Registerkarte "Übersicht" angezeigt.

Gehen Sie dann wie folgt vor:

1. Registrieren Sie die Anwendung.
2. Legen Sie die Token für implizite Gewährung fest.
3. Richten Sie die API-Berechtigungen ein.
4. Erstellen Sie den geheimen Clientschlüssel.


## <a name="session-border-controller-configuration"></a>Konfiguration des Session Border Controllers 

Eine schrittweise Anleitung zum Konfigurieren des Session Border Controllers mit eingebetteter Survivable Branch Appliance finden Sie in der Dokumentation Ihres SBC-Anbieters: 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Ribbon](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-SYSTEMS](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Probleme melden

Melden Sie alle Probleme der Supportorganisation Ihres SBC-Anbieters. Geben Sie dabei an, dass Sie über eine konfigurierte Survivable Branch Appliance verfügen.

## <a name="known-issues"></a>Bekannte Probleme

- Wenn Sie neue Survivable Branch Appliances hinzufügen, kann es einige Zeit dauern, bis Sie sie in den Survivable Branch Appliance-Richtlinien verwenden können.

- Wenn Sie einem Benutzer eine Survivable Branch Appliance-Richtlinie zuweisen, kann es einige Zeit dauern, bis die SBA in der Ausgabe von "Get-CsOnlineUser" erscheint. 

- Die Nummern-Rückwärtssuche wird für Azure AD Kontakte nicht ausgeführt. 

- Die SBA unterstützt keine Einstellungen zur Anrufweiterleitung. 

- Das Tätigen eines Notrufs an eine für die dynamische Notruffunktion (E911) eingerichtete Notrufnummer wird nicht unterstützt.
