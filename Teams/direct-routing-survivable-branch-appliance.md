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
description: Hier finden Sie weitere Informationen zu Direct Routing, z. B. Konfiguration, erforderlichen Grundlegenden Bereitstellungsentscheidungen und Überlegungen zum Sprachrouting.
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
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>Survivable Branch Appliance (SBA) für direct Routing


Gelegentlich kann es bei einer Kundenwebsite, die Direct Routing verwendet, um eine Verbindung mit Microsoft Phone System herzustellen, zu einem Internetausfall kommt.

Gehen Sie davon aus, dass die Kundenwebsite – die so genannte Verzweigung – vorübergehend keine Verbindung mit der Microsoft-Cloud über Direct Routing herstellen kann. Das Intranet innerhalb der Verzweigung ist jedoch weiterhin voll funktionsfähig, und Benutzer können eine Verbindung mit dem Session Border Controller (SBC) herstellen, der eine PSTN-Verbindung bietet.

In diesem Artikel wird beschrieben, wie Sie eine Survivable Branch Appliance (SBA) verwenden, um microsoft Phone System im Falle eines Ausfalls weiterhin Anrufe im öffentlichen Telefonnetz (Public Switched Telephone Network, PSTN) zu senden und zu empfangen.

## <a name="prerequisites"></a>Voraussetzungen

Der SBA ist von Microsoft bereitgestellter Code für SBC-Anbieter, die dann Code in ihre Firmware einbetten oder separat verteilen, damit SBA auf einer separaten VM oder Hardware ausgeführt wird. 

Wenden Sie sich an Ihren SBC-Anbieter, um die neueste Session Border Controller-Firmware mit der eingebetteten Survivable Branch Appliance zu erhalten. Darüber hinaus ist Folgendes erforderlich:

- Der SBC muss für die Medienumgehung konfiguriert werden, um sicherzustellen, dass der Microsoft Teams-Client auf der Verzweigungswebsite Medien direkt mit dem SBC fließen kann. 

- TLS1.2 sollte auf dem SBA VM OS aktiviert sein.

## <a name="supported-teams-clients"></a>Unterstützte Teams-Clients

Das SBA-Feature wird auf den folgenden Microsoft Teams-Clients unterstützt: 

- Microsoft Teams Windows Desktop 

- Microsoft Teams macOS Desktop 

## <a name="how-it-works"></a>Funktionsweise

Während eines Internetausfalls sollte der Teams-Client automatisch zum SBA wechseln, und laufende Anrufe sollten ohne Unterbrechungen fortgesetzt werden. Vom Benutzer ist keine Aktion erforderlich. Sobald der Teams-Client erkennt, dass das Internet verfügbar ist und alle ausgehenden Anrufe beendet sind, wechselt der Client wieder zum normalen Betriebsmodus und verbindet sich mit anderen Teams-Diensten. Der SBA hochgeladen gesammelte Anrufdatensätze in die Cloud, und der Anrufverlauf wird aktualisiert, sodass diese Informationen vom Mandantenadministrator zur Überprüfung zur Verfügung stehen. 

Wenn sich der Microsoft Teams-Client im Offlinemodus befindet, ist die folgende anrufbezogene Funktionalität verfügbar: 

- PstN-Anrufe über lokale SBA/SBC mit Medien, die über den SBC fließen.

- Empfangen von PSTN-Anrufen über lokale SBA/SBC mit Medien, die über den SBC fließen. 

- Halten und Fortsetzen von PSTN-Anrufen.

## <a name="configuration"></a>Konfiguration

Damit das SBA-Feature funktioniert, muss der Teams-Client wissen, welche SBAs auf jeder Zweigstellenwebsite verfügbar sind und welche SBAs den Benutzern auf dieser Website zugewiesen sind. Die Konfigurationsschritte sind wie folgt:

1. Erstellen Sie die SBAs.
2. Erstellen Sie die Richtlinie für die Überlebensfähigkeit von Teams-Zweigen.
3. Weisen Sie die Richtlinie Benutzern zu.
4. Registrieren Sie eine Anwendung für den SBA bei Azure Active Directory.

Die konfiguration erfolgt über Skype for Business Online PowerShell-Cmdlets. (Das Teams Admin Center unterstützt das Direct Routing SBA-Feature noch nicht.) 

(Informationen zum Konfigurieren des SBC mit Links zur Dokumentation zu SBC-Lieferanten finden Sie unter Session Border Controller-Konfiguration am Ende dieses Artikels.)

### <a name="create-the-sbas"></a>Erstellen der SBAs

Zum Erstellen der SBAs verwenden Sie das New-CsTeamsSurvivableBranchAppliance Cmdlet. Dieses Cmdlet verfügt über die folgenden Parameter:

| Parameter| Beschreibung |
| :------------|:-------|
| Identity  | Die Identität des SBA  |
| FQDN | Der FQDN des SBA |
| Standort | Die TenantNetworkSite, auf der sich der SBA befindet |
| Beschreibung | Text im kostenlosen Format |
|||

Beispiel:

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Erstellen der Teams Branch Survivabilitätsrichtlinie 

Zum Erstellen einer Richtlinie verwenden Sie das New-CsTeamsSurvivableBranchAppliancePolicy Cmdlet. Dieses Cmdlet verfügt über die folgenden Parameter. Beachten Sie, dass die Richtlinie mindestens eine SBAs enthalten kann.

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

Sie können SBAs mithilfe des cmdlets Set-CsTeamsSurvivableBranchAppliancePolicy hinzufügen oder aus einer Richtlinie entfernen. Beispiel: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Zuweisen einer Richtlinie zu einem Benutzer

Um die Richtlinie einzelnen Benutzern zuzuordnen, verwenden Sie das Grant-CsTeamsSurvivableBranchAppliancePolicy Cmdlet. Dieses Cmdlet verfügt über die folgenden Parameter:

| Parameter| Beschreibung |
| :------------|:-------|
| Identity | Die Identität des Benutzers |
| PolicyName | Die Identität der Richtlinie |
||

Beispiel:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

Sie können eine Richtlinie von einem Benutzer entfernen, indem Sie $Null richtlinie erteilen, wie im nächsten Beispiel gezeigt:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Registrieren einer Anwendung für den SBA bei Azure Active Directory

Damit verschiedene innerhalb Ihres Mandanten verwendete SBAs erforderliche Daten aus Microsoft 365 lesen können, müssen Sie eine Anwendung für den SBA bei Azure Active Directory registrieren. 

Weitere Informationen zur Anwendungsregistrierung finden Sie in den folgenden Themen:

- [Entwickeln von "Line-of-Business"-Apps für Azure Active Directory](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Registrieren Sie eine Anwendung bei der Microsoft-Identitätsplattform.](/azure/active-directory/develop/quickstart-register-app)  

Sie müssen nur eine Anwendung für die Verwendung durch alle SBAs in Ihrem Mandanten registrieren. 

Für die SBA-Registrierung benötigen Sie die folgenden Werte, die durch die Registrierung erstellt wurden: 

- Anwendungs-(Client-)ID 
- Geheimer Client 

Beachten Sie bei der SBA-Anwendung Folgendes: 

- Der Name kann unabhängig von Ihrer Entscheidung sein.  
- Unterstützte Kontotypen = Konto nur in diesem Organisationsverzeichnis. 
- Der Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient .
- Implizite Grant-Token = Access-Token und ID-Token. 
- API-Berechtigungen = Skype und Teams Tenant Admin Access - > Anwendungsberechtigungen - > application_access_custom_sba_appliance.
- Geheimer Client: Sie können eine beliebige Beschreibung und einen Ablauf verwenden. 
- Denken Sie daran, den Geheimschutz des Clients unmittelbar nach dem Erstellen zu kopieren. 
- Die Anwendungs-ID (Client-ID) wird auf der Registerkarte Übersicht angezeigt.

Führen Sie dann die folgenden Schritte aus:

1. Registrieren Sie die Anwendung.
2. Legen Sie die impliziten Grant-Token ein.
3. Legen Sie die API-Berechtigungen ein.
4. Erstellen Sie den Geheimtipp des Clients.


## <a name="session-border-controller-configuration"></a>Konfiguration des Session Border Controllers 

Schrittweise Anleitungen zum Konfigurieren des Session Border Controllers mit der eingebetteten Survivable Branch Appliance finden Sie in der Dokumentation ihres SBC-Anbieters: 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Menüband](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Melden von Problemen

Melden Sie alle Probleme an die Supportorganisation Ihres SBC-Anbieters. Geben Sie beim Melden des Problems an, dass Sie über eine konfigurierte Survivable Branch Appliance verfügen.

## <a name="known-issues"></a>Bekannte Probleme

- Wenn Sie neue Survivable Branch Appliances hinzufügen, kann es einige Zeit dauern, bis Sie sie in Survivable Branch Appliance-Richtlinien verwenden können.

- Wenn Sie einem Benutzer eine Survivable Branch Appliance-Richtlinie zuweisen, kann es einige Zeit dauern, bis der SBA in der Ausgabe von Get-CsOnlineUser angezeigt wird. 

- Die Umgekehrte Nummern-Suche für Azure AD-Kontakte wird nicht ausgeführt. 

- Die SBA unterstützt keine Anruf weiterleitungseinstellungen. 

- Das Anrufen eines Notrufs bei einer Für dynamische Notrufe konfigurierten Notrufnummer (E911) wird nicht unterstützt.

- Die Ausgabe von Get-CsOnlineUser zeigt TeamsBranchSurvivabilityPolicy.