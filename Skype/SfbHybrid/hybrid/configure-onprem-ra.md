---
title: Konfigurieren eines Ressourcenkontos in Skype for Business Server 2019
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Richten Sie ein Ressourcenkonto für Skype for Business Server 2019 ein.
ms.openlocfilehash: 1d8294eb717982b5ac68df06a5370059e83a62c5
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919011"
---
# <a name="configure-resource-accounts"></a>Konfigurieren von Ressourcenkonten

Hybridimplementierung von Skype for Business Server 2019 verwendet nur Clouddienste, die vom Telefonsystem für Unified Messaging bereitgestellt werden, und können nicht in Exchange Online integriert werden. In Skype for Business Server 2019 können Sie jetzt die Cloudanrufwarteschleifen und automatischen Telefon attendants verwenden, die in den folgenden Abschnitten beschrieben werden, die Sie mit dem Telefonsystem [in Microsoft 365 oder Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)erhalten.

Um eine automatische Telefonzentrale oder Anrufwarteschleife mit Skype for Business Server 2019 zu verwenden, müssen Sie Ressourcenkonten erstellen, die als Anwendungsendpunkte fungieren und Telefonnummern zugewiesen werden können, und dann das Online Teams Admin Center verwenden, um die Anrufwarteschleife oder automatische Telefonzentrale zu konfigurieren. Dieses Ressourcenkonto kann online verwaltet werden (siehe Verwalten von Ressourcenkonten [in Microsoft Teams,](/MicrosoftTeams/manage-resource-accounts) um online verwaltete Ressourcenkonten zu erstellen) oder lokal, wie in diesem Artikel beschrieben. In der Regel verfügen Sie über mehrere automatische Telefonsystemtelefonie- oder Anrufwarteschleifenknoten, die jeweils einem Ressourcenkonto zugeordnet sind, das online oder in Skype for Business Server 2019 gespeichert werden kann.

Wenn Sie über eine vorhandene automatische Exchange -UM-Telefonzentrale und ein Anrufwarteschleifensystem verfügen, müssen Sie vor dem Wechsel zu Exchange Server 2019 oder Exchange Online die Details wie unten beschrieben manuell aufzeichnen und dann mithilfe des Teams Admin Centers ein komplett neues System implementieren.

## <a name="overview"></a>Übersicht

Wenn Ihre automatische Telefonanlage oder Anrufwarteschleife eine Dienstnummer benötigt, können die verschiedenen Abhängigkeiten in der folgenden Reihenfolge erfüllt werden:

1. Rufen Sie eine Dienstnummer ab.
2. Erhalten Sie eine kostenlose Telefonsystem - [virtuelle Benutzerlizenz](/MicrosoftTeams/teams-add-on-licensing/virtual-user) oder eine kostenpflichtige Telefonsystemlizenz für die Verwendung mit dem Ressourcenkonto.
3. Erstellen Sie das Ressourcenkonto. Eine automatische Telefon attendant oder Anrufwarteschleife ist erforderlich, um ein zugeordnetes Ressourcenkonto zu haben.
4. Warten Sie auf eine Active Directory-Synchronisierung zwischen online und lokal.
5. Weisen Sie dem Ressourcenkonto die Telefonsystemlizenz zu.
6. Weisen Sie dem Ressourcenkonto eine Dienstnummer zu.
7. Erstellen sie eine Telefonsystemanrufwarteschleife oder eine automatische Telefonanlage.
8. Ordnen Sie das Ressourcenkonto einer automatischen Telefon attendant oder Anrufwarteschleife zu: (New-CsApplicationInstanceAssociation).

Wenn die automatische Telefonisten- oder Anrufwarteschleife unter einer automatischen Telefon attendant der obersten Ebene geschachtelt ist, benötigt das zugeordnete Ressourcenkonto nur eine Telefonnummer, wenn Sie mehrere Einstiegspunkte in die Struktur der automatischen Telefonisten und Anrufwarteschleifen wünschen.

Um Anrufe an Personen in Ihrer Organisation umzuleiten,  die online zu hause sind, müssen sie über eine Telefonsystemlizenz verfügen und für Enterprise-VoIP aktiviert sein oder über Microsoft 365- oder Office 365-Anrufpläne verfügen. Weitere Informationen [finden Sie unter Zuweisen von Microsoft Teams-Lizenzen.](/MicrosoftTeams/assign-teams-licenses) Um sie für die Enterprise-VoIP zu aktivieren, können Sie Windows PowerShell. Führen Sie z. B. folgenden Auslauf aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Wenn die automatische Telefonanlage oder Anrufwarteschleife, die Sie erstellen, geschachtelt ist und keine Telefonnummer benötigt, wird der Vorgang wie die

1. Erstellen des Ressourcenkontos  
2. Warten auf eine Active Directory-Synchronisierung zwischen online und lokal
3. Erstellen einer automatischen Telefonanlage oder Anrufwarteschleife für das Telefonsystem
4. Zuordnen des Ressourcenkontos zu einer automatischen Telefonanlage oder Anrufwarteschleife des Telefonsystems

## <a name="create-a-resource-account-with-a-phone-number"></a>Erstellen eines Ressourcenkontos mit einer Telefonnummer

Zum Erstellen eines Ressourcenkontos, das eine Telefonnummer verwendet, müssen die folgenden Aufgaben in der folgenden Reihenfolge ausgeführt werden:

1. Port oder erhalten Sie eine gebührenpflichtige oder gebührenfreie Servicenummer. Die Nummer kann keinem anderen Sprachdienst- oder Ressourcenkonto zugewiesen werden.

   Bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen, müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Servicenummern erhalten oder portieren. Nachdem Sie die gebührenpflichtigen oder gebührenfreien Servicenummern erhalten haben, werden sie in den **Voicetelefonnummern** des Microsoft Teams Admin Centers angezeigt, und der aufgeführte Nummerntyp wird als Service -  >    >   **gebührenfrei aufgeführt.**  Informationen zum Abrufen Ihrer [](/MicrosoftTeams/getting-service-phone-numbers) Servicenummern finden Sie unter "Abrufen von Servicetelefonnummern" oder unter "Übertragen von Telefonnummern zu Teams", wenn Sie eine vorhandene Servicenummer [übertragen möchten.](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)

   Wenn Sie sich außerhalb der VEREINIGTEn Staaten befinden, können Sie das Microsoft Teams Admin Center nicht verwenden, um Servicenummern zu erhalten. Wechseln Sie [stattdessen zu "Verwalten](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) von Telefonnummern für Ihre Organisation", um zu sehen, wie Sie dies von außerhalb der USA tun.

2. Erwerben Sie eine Telefonsystemlizenz. Siehe:  
   - [Telefonsystem– Virtuelle Benutzerlizenz](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1- und E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Erstellen Sie ein lokales Ressourcenkonto, indem Sie das Cmdlet für jede automatische Telefonwarteschleife oder Anrufwarteschleife des Telefonsystems ausführen, und geben Sie jedem einen Namen, eine Sip-Adresse `New-CsHybridApplicationEndpoint` und so weiter.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter ["New-CsHybridApplicationEndpoint".](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

4. (Optional) Nachdem Ihre Ressourcenkonten erstellt wurden, können Sie entweder auf die Synchronisierung von AD zwischen online und lokal warten oder eine Synchronisierung erzwingen und mit der Onlinekonfiguration der automatischen Telefonanlage oder der Anrufwarteschleifen fortfahren. Um eine Synchronisierung zu erzwingen, führen Sie den folgenden Befehl auf dem Computer mit AAD Connect aus (falls noch nicht geschehen, müssen Sie zum Ausführen des Befehls `import-module adsync` laden):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter ["Start-ADSyncSyncCycle".](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)
    
    Hinweis: Zu diesem Zeitpunkt wurde das Konto möglicherweise synchronisiert, aber die Bereitstellung ist möglicherweise nicht abgeschlossen.  Überprüfen Sie die Ausgabe von [Get-CsOnlineApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint).  Wenn der synchronisierte Endpunkt die Bereitstellung noch nicht abgeschlossen hat, wird er hier nicht angezeigt.  Sie können den Status der Bereitstellungsanforderungen im M365-Portal unter [Dem Setupstatus von Teams überprüfen.](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)  Diese Bereitstellungsphase kann bis zu 24 Stunden dauern.

5. Weisen Sie dem Ressourcenkonto die Lizenz "Telefonsystem – Virtueller Benutzer oder Telefonsystem" zu. Weitere [Informationen finden Sie unter Zuweisen von Microsoft Teams-Add-On-Lizenzen](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) und Zuweisen von Lizenzen zu [Benutzern.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

   Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die kostenlose Lizenz "Telefonsystem – Virtueller Benutzer" verwenden. Dadurch werden Telefonsystemfunktionen für Telefonnummern auf Organisationsebene zur Verfügung gestellt, und Sie können Funktionen für automatische Telefonanrufe und Anrufwarteschleifen erstellen.


6. Weisen Sie dem Ressourcenkonto die Dienstnummer zu. Verwenden Sie `Set-CsHybridApplicationEndpoint` den Befehl, um dem Ressourcenkonto eine Telefonnummer (mit der Option -LineURI) zuzuordnen.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter ["Set-CsHybridApplicationEndpoint".](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps)

    Verwenden Sie das folgende Cmdlet, um einem Ressourcenkonto ein direktes Routing oder eine Hybridnummer zuzuordnen:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   Das Ressourcenkonto benötigt eine zugewiesene Telefonnummer, wenn es einer automatischen Telefon attendant oder Anrufwarteschleife der obersten Ebene zugewiesen wird. Telefonnummern von Benutzern (Abonnenten) können keinem Ressourcenkonto zugewiesen werden, es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.

     Sie können Ihrem Ressourcenkonto eine direkte Weiterleitung oder eine Hybridnummer zuweisen. Weitere Informationen finden Sie unter [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) and Plan Cloud auto [attendants](plan-cloud-auto-attendant.md).

     > [!NOTE]
     > Direkte Routingdienstnummern, die Ressourcenkonten für automatische Telefonisten und Anrufwarteschleifen zugewiesen sind, werden nur für Microsoft Teams-Benutzer und -Agents unterstützt.

7. Erstellen Sie die automatische Telefonanlage oder Anrufwarteschleife des Telefonsystems. Sehen Sie sich eines der folgenden Themen an:

   - [Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Erstellen einer Cloudanrufwarteschleife](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Ordnen Sie das Ressourcenkonto der automatischen Telefonanlage oder Anrufwarteschleife zu, die Sie zuvor ausgewählt haben.

## <a name="create-a-resource-account-without-a-phone-number"></a>Erstellen eines Ressourcenkontos ohne Telefonnummer

In diesem Abschnitt wird das Erstellen eines Ressourcenkontos erläutert, das lokal erstellt wird. Das Erstellen eines Ressourcenkontos, das online verwaltet wird, wird unter ["Ressourcenkonten verwalten" in Microsoft Teams erläutert.](/MicrosoftTeams/manage-resource-accounts)

Diese Schritte sind erforderlich, unabhängig davon, ob Sie eine völlig neue automatische Telefonwarteschleife oder Eine Anrufwarteschleifenstruktur erstellen oder die Struktur neu erstellen, die ursprünglich in Exchange UM erstellt wurde.

Melden Sie sich beim Skype for Business-Front-End-Server an, und führen Sie die folgenden PowerShell-Cmdlets aus:

1. Erstellen Sie ein lokales Ressourcenkonto, indem Sie das Cmdlet für jede automatische Telefonwarteschleife oder Anrufwarteschleife des Telefonsystems ausführen, und geben Sie jedem einen Namen, eine Sip-Adresse `New-CsHybridApplicationEndpoint` und so weiter.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter ["New-CsHybridApplicationEndpoint".](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

2. (Optional) Nachdem Ihre Ressourcenkonten erstellt wurden, können Sie entweder auf die Synchronisierung von AD zwischen online und lokal warten oder eine Synchronisierung erzwingen und mit der Onlinekonfiguration der automatischen Telefonanlage oder der Anrufwarteschleifen fortfahren. Um eine Synchronisierung zu erzwingen, führen Sie den folgenden Befehl auf dem Computer mit AAD Connect aus (falls noch nicht geschehen, müssen Sie zum Ausführen des Befehls `import-module adsync` laden):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter ["Start-ADSyncSyncCycle".](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)

3. Erstellen Sie die automatische Telefonanlage oder Anrufwarteschleife des Telefonsystems. Sehen Sie sich eines der folgenden Themen an:
   - [Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Erstellen einer Cloudanrufwarteschleife](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Ordnen Sie das Ressourcenkonto und die automatische Telefonanlage oder Anrufwarteschleife zu, die Sie zuvor ausgewählt haben.

## <a name="test-the-implementation"></a>Testen der Implementierung

Die beste Möglichkeit zum Testen der Implementierung besteht in der Anrufnummer, die für eine automatische Telefonanlage oder Anrufwarteschleife konfiguriert ist, und eine Verbindung mit einem der Agents oder Menüs herzustellen. Sie können auch schnell einen Testanruf mit der Schaltfläche **"Testen"** im Admin Center -Aktionsbereich platzieren. Wenn Sie Änderungen an einer automatischen Telefonanlage oder Anrufwarteschleife vornehmen möchten, wählen Sie sie aus, und klicken Sie dann im Aktionsbereich auf **Bearbeiten**. 

> [!TIP]
> Wenn Ihr Ressourcenkonto Schwierigkeiten beim Enignen einer Anrufwarteschleife oder [](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) automatischen Telefon attendant hat, lesen Sie bekannte Probleme für [Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) und den Abschnitt "Beheben meiner Hybridanwendungsinstanzen" im Microsoft Teams-Blog.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Verschieben einer automatischen Exchange -UM-Telefonanlage oder -Anrufwarteschleife in das Telefonsystem

Für die Migration von Exchange UM zum Telefonsystem muss die Anrufwarteschleife und die Struktur der automatischen Telefon attendant neu aufgebaut werden. Eine direkte Migration von einer zur anderen wird nicht unterstützt. So implementieren Sie eine Reihe von Anrufwarteschleifen und automatischen Telefon attendants erneut:

1. Rufen Sie eine Liste aller automatischen Exchange UM-Telefonzentralen und Anrufwarteschleifen ab, indem Sie den folgenden Befehl auf dem Exchange 2013- oder 2016-System ausführen, während Sie als Administrator angemeldet sind:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Notieren Sie sich für jede aufgelistete Exchange UM-Anrufwarteschleife oder automatische Telefon attendant ihren Platz in der Struktur, einstellungen und rufen Sie Kopien der zugehörigen Sound- oder Text-zu-Sprache-Dateien ab (die GUID in der Ausgabe ist der Name eines Ordners, in dem die Dateien gespeichert sind). Sie können diese Details erhalten, indem Sie den folgenden Befehl ausführen:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter ["Get-UMAutoAttendant".](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) Eine vollständige Liste der Optionen, die Sie möglicherweise erfassen müssen, finden Sie unter ["UMAutoAttendant"-Mitglieder.](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) Die wichtigsten Zu beachtenden Optionen sind jedoch:

    - Geschäftszeiten
    - Zeiten außerhalb der Geschäftszeiten
    - Sprache
    - Feiertagszeitplan

3. Erstellen Sie neue lokale Endpunkte, wie zuvor beschrieben.
   Weisen Sie der automatischen Attendant der obersten Ebene zu Testzwecken eine temporäre Nummer zu.

4. Konfigurieren Sie eine automatische Telefonanlage oder Anrufwarteschleife, die die Endpunkte wie zuvor beschrieben verwendet.

5. Testen Sie die automatische Telefonanlage oder Anrufwarteschleife des Telefonsystems.

6. Die mit der Exchange -UM-Anrufwarteschleife oder der automatischen Telefonanlage verknüpfte Telefonnummer wird der entsprechenden automatischen Telefonsystem- oder Anrufwarteschleife erneut zugewiesen.  

   Wenn Sie zu diesem Zeitpunkt bereits um Voicemail migriert haben, sollten Sie in der Lage sein, zu Exchange Server 2019 zu migrieren.

## <a name="see-also"></a>Siehe auch

[Erstellen einer Cloudanrufwarteschleife](/MicrosoftTeams/create-a-phone-system-call-queue)

[Was sind automatische Cloudtelefonzentralen?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Planen automatischer Cloudtelefonzentralen](plan-cloud-auto-attendant.md)

[Planen von Cloud-Anrufwarteschlangen](plan-call-queue.md)

[Planen des Cloud-Voicemail-Diensts für lokale Benutzer](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Verwalten von Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)  -  \( so erstellen Sie online zu verwaltende Ressourcenkonten\)
