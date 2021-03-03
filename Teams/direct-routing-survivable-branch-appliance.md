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
description: Erfahren Sie mehr über Direct-Routing, z. B. Konfiguration, erforderliche wichtige Bereitstellungsentscheidungen und Überlegungen zum Voice Routing.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fb8812fd025317eb9c6e3c67ce1f5fcea094978
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196489"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>Surrble Branch Appliance (SBA) für Direct Routing


Gelegentlich kann es bei einer Kundenwebsite, die Direct Routing zum Herstellen einer Verbindung mit dem Microsoft Phone System verwendet, zu einem Internetausfall kommt.

Gehen Sie davon aus, dass die Kundenwebsite – eine so genannte Verzweigung – vorübergehend keine Verbindung mit der Microsoft Cloud über Direct Routing herstellen kann. Das Intranet innerhalb der Verzweigung ist jedoch weiterhin voll funktionsfähig, und Die Benutzer können eine Verbindung mit dem Session Border Controller (SBC) herstellen, der die PSTN-Konnektivität bietet.

In diesem Artikel wird beschrieben, wie Sie eine Surble Branch Appliance (SBA) verwenden, damit Microsoft Phone System im Falle eines Ausfalls weiterhin Anrufe im öffentlichen Telefonnetz (PstN) senden und empfangen kann.

## <a name="prerequisites"></a>Voraussetzungen

Das SBA ist verteilbarer Code, der von Microsoft an SBC-Lieferanten bereitgestellt wird, die dann Code in die Firmware einbetten oder separat verteilen, damit SBA auf einer separaten VM oder Hardware ausgeführt wird. 

Wenden Sie sich an Ihren SBC-Anbieter, um die neueste Session Border Controller-Firmware mit der eingebetteten Surble Branch Appliance zu erhalten. Darüber hinaus ist Folgendes erforderlich:

- Der SBC muss für die Medienumgehung konfiguriert werden, um sicherzustellen, dass im Microsoft Teams-Client auf der Verzweigungswebsite Medien direkt mit dem SBC fließen können. 

- TLS1.2 sollte auf dem SBA VM OS aktiviert sein.

## <a name="supported-teams-clients"></a>Unterstützte Kunden in Teams

Das Feature SBA wird auf den folgenden Microsoft Teams-Clients unterstützt: 

- Microsoft Teams Windows Desktop 

- Microsoft Teams macOS Desktop 

## <a name="how-it-works"></a>Funktionsweise

Während eines Internetausfalls sollte der Teamclient automatisch auf SBA umschalten, und laufende Anrufe sollten ohne Unterbrechungen fortgesetzt werden. Vom Benutzer ist keine Aktion erforderlich. Sobald der Teams-Client erkennt, dass das Internet verfügbar ist und alle ausgehenden Anrufe abgeschlossen sind, wechselt der Client zurück in den normalen Betriebsmodus und verbindet sich mit anderen Teams-Diensten. Das SBA hochgeladen gesammelte Anrufdatensätze in die Cloud, und die Anrufhistorie wird aktualisiert, damit diese Informationen vom Mandantenadministrator überprüft werden können. 

Wenn sich der Microsoft Teams-Client im Offlinemodus befindet, steht die folgende anrufbezogene Funktionalität zur Verfügung: 

- PstN-Anrufe über lokales SBA/SBC mit Medien, die den SBC durchfließen.

- Empfangen von PSTN-Anrufen über lokales SBA/SBC mit Medien, die über den SBC fließen 

- Halten und Fortsetzen von Festnetzanrufen

## <a name="configuration"></a>Konfiguration

Damit das SBA-Feature funktioniert, muss der Teamclient wissen, welche SBAs auf jeder Zweigstellenwebsite verfügbar sind und welche SBAs den Benutzern auf dieser Website zugewiesen sind. Die Konfigurationsschritte sind wie folgt:

1. Erstellen Sie die SBAs.
2. Erstellen Sie die Ersatzrichtlinie für die Teams-Verzweigung.
3. Weisen Sie die Richtlinie Benutzern zu.
4. Registrieren Sie eine Anwendung für SBA bei Azure Active Directory.

Die Konfiguration erfolgt über Skype for Business Online-PowerShell-Cmdlets. (Das Teams Admin Center unterstützt das Direct Routing-SBA-Feature noch nicht.) 

(Informationen zum Konfigurieren des SBC mit Links zur Dokumentation zu Lieferanten von SBC finden Sie unter "Session Border Controller"-Konfiguration am Ende dieses Artikels.)

### <a name="create-the-sbas"></a>Erstellen der SBAs

Zum Erstellen der SBAs verwenden Sie das New-CsTeamsSurvivableBranchAppliance Cmdlet. Dieses Cmdlet hat die folgenden Parameter:

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

### <a name="create-the-teams-branch-survivability-policy"></a>Erstellen der Richtlinie für Teams Branch Sur über die Richtlinien 

Zum Erstellen einer Richtlinie verwenden Sie das New-CsTeamsSurvivableBranchAppliancePolicy Cmdlet. Dieses Cmdlet hat die folgenden Parameter. Beachten Sie, dass die Richtlinie mindestens eine SBA enthalten kann.

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

Sie können SBAs zu einer Richtlinie hinzufügen oder aus ihr entfernen, indem Sie das cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy hinzufügen. Beispiel: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Zuweisen einer Richtlinie zu einem Benutzer

Um die Richtlinie einzelnen Benutzern zuzuordnen, verwenden Sie das Grant-CsTeamsSurvivableBranchAppliancePolicy Cmdlet. Dieses Cmdlet hat die folgenden Parameter:

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

Damit verschiedene INNERHALB Ihres Mandanten verwendete SBAs erforderliche Daten aus Microsoft 365 lesen können, müssen Sie eine Anwendung für SBA bei Azure Active Directory registrieren. 

Weitere Informationen zur Anwendungsregistrierung finden Sie in den folgenden Themen:

- [Entwickeln von Business-Line-of-Business-Apps für Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Registrieren Sie eine Anwendung bei der Microsoft-Identitätsplattform.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)  

Sie müssen nur eine Anwendung für die Verwendung durch alle SBAs in Ihrem Mandanten registrieren. 

Für die SBA-Registrierung benötigen Sie die folgenden Durch die Registrierung erstellten Werte: 

- Anwendungs-ID (Client-ID) 
- Geheimer Client 

Beachten Sie bei der SBA-Anwendung Folgendes: 

- Der Name kann alles sein, was Sie entscheiden.  
- Unterstützte Kontotypen = Konto nur in diesem Organisationsverzeichnis. 
- Der Web Redirect-URI = https://login.microsoftonline.com/common/oauth2/nativeclient .
- Implizite Granttoken = Zugriffstoken und ID-Token. 
- API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.
- Geheimer Client: Sie können eine Beschreibung und einen Ablauf verwenden. 
- Denken Sie daran, den geheimen Clientgeheimnis unmittelbar nach seiner Erstellung zu kopieren. 
- Die Anwendungs-ID (Client-ID) wird auf der Registerkarte "Übersicht" angezeigt.

Führen Sie dann die folgenden Schritte aus:

1. Registrieren Sie die Anwendung.
2. Legen Sie die impliziten Grant-Token festgelegt.
3. Legen Sie die API-Berechtigungen bereit.
4. Erstellen Sie den geheimen Clientgeheimnis.


## <a name="session-border-controller-configuration"></a>Session Border Controller configuration 

Eine schritt-für-Schritt-Anleitung zum Konfigurieren des Session Border Controllers mit der eingebetteten Surble Branch Appliance finden Sie in der Dokumentation Ihres SBC-Anbieters: 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Menüband](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Melden von Problemen

Melden Sie Probleme an die Supportorganisation Ihres SBC-Anbieters. Wenn Sie das Problem melden, geben Sie an, dass Sie über eine konfigurierte Surleble Branch Appliance verfügen.

## <a name="known-issues"></a>Bekannte Probleme

- Wenn Sie neue Surble Branch Appliances hinzufügen, kann es eine Weile dauern, bis Sie sie in Richtlinien für Surble Branch Appliance verwenden können.

- Wenn Sie einem Benutzer eine Richtlinie für surble Branch Appliance zuweisen, kann es eine Weile dauern, bis SBA in der Ausgabe von "Get-CsOnlineUser" angezeigt wird. 

- Eine umgekehrte Nummern-Suche für Azure AD-Kontakte wird nicht ausgeführt. 

- Die SBA unterstützt keine Anruf weiterleitungseinstellungen. 

- Das Anrufen einer für dynamische Notrufe konfigurierten Notrufnummer (E911) wird nicht unterstützt.

- Die Ausgabe des Get-CsOnlineUser zeigt "TeamsBranchSur übersingpolicy".
