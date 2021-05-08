---
title: Direct Routing SBA
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
description: Erfahren Sie mehr über Direct-Routing, z. B. Konfiguration, erforderliche Entscheidungen zur zentralen Bereitstellung und Überlegungen zum Voice Routing.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: edf2c2a97bec2b167f1218d983d3c9f7fa4bd667
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096425"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>Surrouble Branch Appliance (SBA) für direktes Routing


Gelegentlich kann es bei einer Kundenwebsite, auf der Direct Routing zum Herstellen Microsoft-Telefon zu einem Internetausfall kommt.

Gehen Sie davon aus, dass die Kundenwebsite – als Verzweigung bezeichnet – vorübergehend keine Verbindung mit der Microsoft-Cloud über Direct-Routing herstellen kann. Das Intranet innerhalb der Verzweigung ist jedoch weiterhin voll funktionsfähig, und Die Benutzer können eine Verbindung mit dem Session Border Controller (SBC) herstellen, der PSTN-Konnektivität bietet.

In diesem Artikel wird beschrieben, wie Sie mithilfe eines Surble Branch Appliance (SBA) Microsoft-Telefon System für den Fall eines Ausfalls weiterhin Anrufe im öffentlichen Telefonnetz (Public Switched Telephone Network, PSTN) herstellen und empfangen können.

## <a name="prerequisites"></a>Voraussetzungen

SBA ist verteilbarer Code, der von Microsoft an SBC-Lieferanten bereitgestellt wird, die dann Code in ihre Firmware einbetten oder separat verteilen, damit SBA auf einer separaten VM oder Hardware ausgeführt wird. 

Wenden Sie sich an Ihren SBC-Anbieter, um die neueste Session Border Controller-Firmware mit dem eingebetteten Sur behaltet Branch Appliance zu erhalten. Darüber hinaus ist Folgendes erforderlich:

- Der SBC muss für die Medienumgehung konfiguriert werden, um sicherzustellen, dass der Microsoft Teams-Client auf der Verzweigungswebsite Medien direkt mit dem SBC fließen kann. 

- TLS1.2 sollte auf dem SBA VM-Betriebssystem aktiviert sein.

## <a name="supported-teams-clients"></a>Unterstützte Teams-Clients

Das SBA-Feature wird auf den folgenden Microsoft Teams unterstützt: 

- Microsoft Teams Windows Desktop 

- Microsoft Teams macOS Desktop 

## <a name="how-it-works"></a>Funktionsweise

Während eines Internetausfalls sollte der Teams-Client automatisch auf SBA umschalten, und laufende Anrufe sollten ohne Unterbrechungen fortgesetzt werden. Es ist keine Aktion des Benutzers erforderlich. Sobald der Teams-Client erkennt, dass das Internet verfügbar ist und alle ausgehenden Anrufe abgeschlossen sind, wechselt der Client wieder in den normalen Betriebsmodus und verbindet sich mit anderen Teams Diensten. Das SBA hochgeladen die gesammelten Anrufdatensätze in die Cloud, und der Anrufverlauf wird aktualisiert, damit diese Informationen vom Mandantenadministrator überprüft werden können. 

Wenn sich Microsoft Teams-Client im Offlinemodus befindet, ist die folgende Anruffunktion verfügbar: 

- PstN-Anrufe über lokales SBA/SBC mit Medien, die den SBC-Code durchfließen

- Empfangen von PSTN-Anrufen über lokales SBA/SBC mit Medien, die den SBC durchfließen 

- Halten und Fortsetzen von PSTN-Anrufen

## <a name="configuration"></a>Konfiguration

Damit das SBA-Feature funktioniert, muss der Teams-Client wissen, welche SBAs an den einzelnen Verzweigungsstandorten verfügbar sind und welche SBAs den Benutzern auf dieser Website zugewiesen sind. Die Konfigurationsschritte sind wie folgt:

1. Erstellen Sie die SBAs.
2. Erstellen Sie die Teams-Richtlinie für verzweigte Verzweigung.
3. Weisen Sie die Richtlinie Benutzern zu.
4. Registrieren Sie eine Anwendung für SBA mit Azure Active Directory.

Die Konfiguration erfolgt über Skype for Business Online-PowerShell-Cmdlets. (Das Teams Admin Center unterstützt das Direct Routing SBA-Feature noch nicht.) 

(Informationen zum Konfigurieren des SBC mit Links zur Dokumentation von SBC-Lieferanten finden Sie unter Session Border Controller-Konfiguration am Ende dieses Artikels.)

### <a name="create-the-sbas"></a>Erstellen der SBAs

Zum Erstellen der SBAs verwenden Sie das cmdlet New-CsTeamsSurvivableBranchAppliance. Dieses Cmdlet hat die folgenden Parameter:

| Parameter| Beschreibung |
| :------------|:-------|
| Identity  | Die Identität des SBA  |
| FQDN | Der FQDN der SBA |
| Standort | Die TenantNetworkSite, auf der sich SBA befindet |
| Beschreibung | Text kostenlos formatieren |
|||

Beispiel:

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Erstellen der Teams-Richtlinie für Zweigniederlassung 

Zum Erstellen einer Richtlinie verwenden Sie das cmdlet New-CsTeamsSurvivableBranchAppliancePolicy Richtlinie. Dieses Cmdlet hat die folgenden Parameter. Beachten Sie, dass die Richtlinie mindestens eine SBAs enthalten kann.

| Parameter| Beschreibung |
| :------------|:-------|
| Identity | Die Identität der Richtlinie |
| BranchApplianceFqdns  | Der FQDN der SBA(s) auf der Website |
||

Beispiel:

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

Sie können SBAs einer Richtlinie mithilfe des cmdlets Set-CsTeamsSurvivableBranchAppliancePolicy hinzufügen oder aus dieser entfernen. Beispiel: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Zuweisen einer Richtlinie zu einem Benutzer

Zum Zuweisen der Richtlinie zu einzelnen Benutzern verwenden Sie das cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy Richtlinie. Dieses Cmdlet hat die folgenden Parameter:

| Parameter| Beschreibung |
| :------------|:-------|
| Identity | Die Identität des Benutzers |
| PolicyName | Die Identität der Richtlinie |
||

Beispiel:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

Sie können eine Richtlinie von einem Benutzer entfernen, indem Sie $Null Richtlinie erteilen, wie im nächsten Beispiel gezeigt:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Registrieren einer Anwendung für SBA bei Azure Active Directory

Damit verschiedene SBAs, die innerhalb Ihres Mandanten verwendet werden, erforderliche Daten von Microsoft 365 lesen können, müssen Sie eine Anwendung für das SBA bei Azure Active Directory. 

Weitere Informationen zur Anwendungsregistrierung finden Sie in folgenden Themen:

- [Entwickeln von Business-Apps für Azure Active Directory](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Registrieren Sie eine Anwendung beim -Microsoft Identity Platform.](/azure/active-directory/develop/quickstart-register-app)  

Sie müssen nur eine Anwendung für die Verwendung durch alle SBAs in Ihrem Mandanten registrieren. 

Für die SBA-Registrierung benötigen Sie die folgenden Werte, die von der Registrierung erstellt werden: 

- Anwendungs-ID (Client-ID) 
- Geheimer Client-Schlüssel 

Beachten Sie bei der SBA-Anwendung Folgendes: 

- Der Name kann alles sein, was Sie entscheiden.  
- Unterstützte Kontotypen = Konto nur in diesem Organisationsverzeichnis. 
- Der Web Redirect-URI = https://login.microsoftonline.com/common/oauth2/nativeclient .
- Implizite Zugriffstoken = Zugriffstoken und ID-Token. 
- API-Berechtigungen = Skype und Teams Mandantenadministratorzugriff -> Anwendungsberechtigungen -> application_access_custom_sba_appliance.
- Geheimer Clientgeheimnis: Sie können eine beliebige Beschreibung und einen Ablauf verwenden. 
- Denken Sie daran, den geheimen Client-Schlüssel unmittelbar nach der Erstellung zu kopieren. 
- Die Anwendungs-ID (Client-ID) wird auf der Registerkarte Übersicht angezeigt.

Führen Sie dann die folgenden Schritte aus:

1. Registrieren Sie die Anwendung.
2. Legen Sie die impliziten Zugriffstoken festgelegt.
3. Legen Sie die API-Berechtigungen bereit.
4. Erstellen Sie den geheimen Client-Schlüssel.


## <a name="session-border-controller-configuration"></a>Session Border Controller configuration 

Eine Schritt-für-Schritt-Anleitung zum Konfigurieren Ihres Session Border Controllers mit dem eingebetteten Sur tief verzweigten Gerät finden Sie in der Dokumentation Ihres SBC-Anbieters: 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Menüband](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Melden von Problemen

Melden Sie alle Probleme an die Supportorganisation Ihres SBC-Anbieters. Wenn Sie das Problem melden, geben Sie an, dass Sie über ein konfiguriertes Sur verzweigungsgerät verfügen.

## <a name="known-issues"></a>Bekannte Probleme

- Wenn Sie neue Surung Branch Appliances hinzufügen, kann es eine Weile dauern, bis Sie sie in Richtlinien für Surble Branch Appliance verwenden können.

- Wenn Sie einem Benutzer eine Sur unleerble Branch Appliance-Richtlinie zuweisen, kann es eine Weile dauern, bis SBA in der Ausgabe von Get-CsOnlineUser angezeigt wird. 

- Eine umgekehrte Nummern-Suche für Azure AD-Kontakte wird nicht ausgeführt. 

- Die SBA unterstützt keine Einstellungen für die Anruf weiterleitung. 

- Das Anrufen einer für dynamische Notrufe konfigurierten Notrufnummer (E911) wird nicht unterstützt.

- Die Ausgabe des Get-CsOnlineUser Zeigt "TeamsBranchSur ver wiederkeligPolicy" an.