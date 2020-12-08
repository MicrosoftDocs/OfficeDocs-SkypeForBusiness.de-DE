---
title: Direct Routing SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
description: Erfahren Sie mehr über das direkte Routing, beispielsweise die Konfiguration, die erforderlichen zentralen Bereitstellungsentscheidungen und Überlegungen zu VoIP-Routing.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9e64dc908bafdd63b17e22716e76c4f04df1409
ms.sourcegitcommit: f122c078b6458754500f3cc68086d6ccfa62d183
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588599"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a>Überlebensfähige Branch Appliance (SBA) für direktes Routing – öffentliche Vorschau


> [!NOTE]
> Hierbei handelt es sich um eine öffentliche Preview-Version.

Gelegentlich kann es vorkommen, dass eine Kunden Website, die Direktes Routing zum Herstellen einer Verbindung mit dem Microsoft Phone System verwendet, einen internetausfall hat.

Davon ausgehen, dass die Kunden Website – so genannte Verzweigung – vorübergehend keine Verbindung mit der Microsoft-Cloud über direktes Routing herstellen kann. Das Intranet innerhalb der Verzweigung ist jedoch weiterhin voll funktionsfähig, und Benutzer können eine Verbindung mit dem Session Border Controller (SBC) herstellen, der PSTN-Konnektivität bereitstellt.

In diesem Artikel wird beschrieben, wie Sie eine Survivable Branch Appliance (SBA) verwenden, damit Microsoft Phone System im Fall eines Ausfalls weiterhin PSTN-Anrufe (Public Switched Telephone Network) durchführen und empfangen kann.

## <a name="prerequisites"></a>Voraussetzungen

Die SBA ist ein Verteilungs Code, der von Microsoft an SBC-Anbieter bereitgestellt wird, die den Code dann in die Firmware Ihres SBCS einbetten. 

Wenden Sie sich an Ihren SBC-Anbieter, um die neueste Session Border Controller-Firmware mit der eingebetteten Survivable Branch-Appliance zu erhalten. Darüber hinaus ist Folgendes erforderlich:

- Der SBC muss für die medienumgehung konfiguriert werden, um sicherzustellen, dass der Microsoft Teams-Client auf der Verzweigungs Website Medien direkt mit dem SBC fließen lassen kann. 

- TLS 1.2 sollte auf dem SBA VM-Betriebssystem aktiviert sein.

## <a name="supported-teams-clients"></a>Unterstützte Teams-Clients

Das SBA-Feature wird für die folgenden Microsoft Teams-Clients unterstützt: 

- Microsoft Teams Windows-Desktop 

- Microsoft Teams macOS Desktop 

## <a name="how-it-works"></a>Funktionsweise

Bei einem internetausfall sollte der Team-Client automatisch zur SBA wechseln, und die laufenden Anrufe sollten ohne Unterbrechungen fortgesetzt werden. Vom Benutzer ist keine Aktion erforderlich. Sobald der Team-Client feststellt, dass das Internet aktiviert ist und alle ausgehenden Anrufe ablaufen, wird der Client wieder in den normalen Betriebsmodus versetzt und mit anderen Teams-Diensten verbunden. Die SBA wird gesammelte anrufdatensätze in die Cloud hochladen, und der ANRUFVERLAUF wird aktualisiert, damit diese Informationen vom mandantenadministrator zur Überprüfung zur Verfügung stehen. 

Wenn sich der Microsoft Teams-Client im Offlinemodus befindet, stehen die folgenden anrufbezogenen Funktionen zur Verfügung: 

- Durchführen von PSTN-anrufen über lokales SBA/SBC mit Medien, die über den SBC fließen.

- Empfangen von PSTN-anrufen über lokales SBA/SBC mit Medien, die über den SBC fließen. 

- Anhalten und Fortsetzen von PSTN-anrufen.

## <a name="configuration"></a>Konfiguration

Damit die SBA-Funktion funktioniert, muss der Team-Client wissen, welche SBAS in jeder Verzweigungs Website verfügbar sind und welche SBAS den Benutzern auf dieser Website zugewiesen sind. Die Konfigurationsschritte lauten wie folgt:

1. Erstellen Sie den SBAS.
2. Erstellen Sie die Survival-Richtlinie für Teams.
3. Weisen Sie die Richtlinie Benutzern zu.
4. Registrieren Sie eine Anwendung für die SBA mit Azure Active Directory.

Die gesamte Konfiguration erfolgt mithilfe der PowerShell-Cmdlets von Skype for Business Online. (Das Team Admin Center unterstützt noch nicht das Direct Routing SBA-Feature.) 

(Informationen zum Konfigurieren des SBC mit Links zur SBC-Lieferantendokumentation finden Sie unter Konfiguration des Sitzungs Grenz Controllers am Ende dieses Artikels.)

### <a name="create-the-sbas"></a>Erstellen der SBAS

Zum Erstellen des SBAS verwenden Sie das New-CsTeamsSurvivableBranchAppliance-Cmdlet. Dieses Cmdlet verfügt über die folgenden Parameter:

| Parameter| Beschreibung |
| :------------|:-------|
| Identity  | Der FQDN des SBA  |
| FQDN | Der FQDN des SBA |
| Standort | Der TenantNetworkSite, in dem sich die SBA befindet |
| Beschreibung | Kostenloses Formatieren von Text |
|||

Beispiel:

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.dk -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Erstellen der Survivable-Richtlinie für Teams 

Zum Erstellen einer Richtlinie verwenden Sie das New-CsTeamsSurvivableBranchAppliancePolicy-Cmdlet. Dieses Cmdlet verfügt über die folgenden Parameter. Beachten Sie, dass die Richtlinie mindestens eine SBAS enthalten kann.

| Parameter| Beschreibung |
| :------------|:-------|
| Identity | Die Identität der Richtlinie |
| BranchApplianceFqdns  | Der FQDN der SBA (s) auf der Website |
||

Beispiel:

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.dk, sba2.contoso.com} 
```

Mithilfe des Set-CsTeamsSurvivableBranchAppliancePolicy-Cmdlets können Sie einer Richtlinie SBAS hinzufügen oder daraus entfernen. Beispiel: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Zuweisen einer Richtlinie zu einem Benutzer

Wenn Sie die Richtlinie einzelnen Benutzern zuweisen möchten, verwenden Sie das Cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy. Dieses Cmdlet verfügt über die folgenden Parameter:

| Parameter| Beschreibung |
| :------------|:-------|
| Identity | Die Identität des Benutzers |
| PolicyName | Die Identität der Richtlinie |
||

Beispiel:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

Sie können eine Richtlinie von einem Benutzer entfernen, indem Sie die $NULL Richtlinie zuweisen, wie im nächsten Beispiel gezeigt:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Registrieren einer Anwendung für die SBA mit Azure Active Directory

Damit andere SBAS, die in Ihrem Mandanten verwendet werden, erforderliche Daten von Microsoft 365 lesen können, müssen Sie eine Anwendung für die SBA mit Azure Active Directory registrieren. 

Weitere Informationen zur Anwendungsregistrierung finden Sie unter den folgenden Themen:

- [Entwickeln von Branchen-Apps für Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Registrieren Sie eine Anwendung mit der Microsoft Identity-Plattform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).  

Sie müssen nur eine Anwendung für die Verwendung durch alle SBAS in Ihrem Mandanten registrieren. 

Für die Registrierung von SBA benötigen Sie die folgenden Werte, die durch die Registrierung erstellt werden: 

- Anwendungs-ID (Client) 
- Kundengeheimnis 

Beachten Sie bei der SBA-Anwendung Folgendes: 

- Der Name kann sein, was auch immer Sie sich entscheiden.  
- Unterstützte Kontotypen = Konto nur in diesem Organisations Verzeichnis. 
- Das Web Redirect URI = https://login.microsoftonline.com/common/oauth2/nativeclient .
- Implizite Grant-Tokens = Zugriffstoken und ID-Token. 
- API-Berechtigungen = Skype und Teams mandantenadministrator Zugriff – > Anwendungsberechtigungen – > application_access_custom_sba_appliance.
- Client-Secret: Sie können jede Beschreibung und Ablaufzeit verwenden. 
- Vergessen Sie nicht, den Client-Schlüssel unmittelbar nach dem erstellen zu kopieren. 
- Die Anwendungs-ID (Client) wird auf der Registerkarte Übersicht angezeigt.

Führen Sie dann die folgenden Schritte aus:

1. Registrieren Sie die Anwendung.
2. Setzen Sie die impliziten Grant-Token.
3. Setzen Sie die API-Berechtigungen.
4. Erstellen Sie den geheimen Client.


## <a name="session-border-controller-configuration"></a>Session Border Controller-Konfiguration 

Eine Schritt-für-Schritt-Anleitung zum Konfigurieren Ihres Session Border Controllers mit der eingebetteten Survivable Branch-Appliance finden Sie in der Dokumentation Ihres SBC-Anbieters: 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Multifunktionsleiste](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Melden von Problemen

Melden Sie alle Probleme an die Support Organisation Ihres SBC-Anbieters. Wenn Sie das Problem melden, geben Sie an, dass Sie über eine konfigurierte Survivable Branch-Appliance verfügen.

## <a name="known-issues"></a>Bekannte Probleme

- Wenn Sie neue überlebensfähige Branch Appliances hinzufügen, kann es einige Zeit dauern, bis Sie Sie in Survivable Branch Appliance-Richtlinien verwenden können.

- Wenn Sie einem Benutzer eine Survivable Branch Appliance-Richtlinie zuweisen, kann es einige Zeit dauern, bis die SBA in der Ausgabe von Get-CsOnlineUser angezeigt wird. 

- Umgekehrte Nummernsuche mit Azure AD-Kontakten wird nicht durchgeführt. 

- Die SBA unterstützt keine Einstellungen für die Anrufweiterleitung. 

- Das tätigen eines Notrufs an eine Notrufnummer, die für Dynamic Emergency Calling (E911) konfiguriert ist, wird nicht unterstützt.

- Die Ausgabe von Get-CsOnlineUser zeigt TeamsBranchSurvivabilityPolicy.
