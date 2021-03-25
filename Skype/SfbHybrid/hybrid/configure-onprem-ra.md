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
ms.openlocfilehash: eb8f82a9551c3607068b0d62cc04518d58d09987
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118934"
---
# <a name="configure-resource-accounts"></a>Konfigurieren von Ressourcenkonten

Skype for Business Server 2019-Hybridimplementierung verwendet nur Clouddienste, die von Phone System für Unified Messaging bereitgestellt werden, und können nicht in Exchange Online integriert werden. In Skype for Business Server 2019 können Sie jetzt die Cloudanrufwarteschlangen und automatischen Telefonwarteschlangen verwenden, die unter Hier ist beschrieben, was Sie mit dem Telefonsystem [in Microsoft 365 oder Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)erhalten.

Um eine automatische Telefonzentrale oder Anrufwarteschlange mit Skype for Business Server 2019 zu verwenden, müssen Sie Ressourcenkonten erstellen, die als Anwendungsendpunkte fungieren und Telefonnummern zugewiesen werden können, und dann das Online Teams Admin Center verwenden, um die Anrufwarteschlange oder automatische Telefonzentrale zu konfigurieren. Dieses Ressourcenkonto kann online verwaltet werden (siehe Verwalten von Ressourcenkonten [in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) zum Erstellen online verwalteter Ressourcenkonten) oder lokal, wie in diesem Artikel beschrieben. In der Regel verfügen Sie über mehrere automatische Telefonsystemtelefonie- oder Anrufwarteschlangenknoten, die jeweils einem Ressourcenkonto zugeordnet sind, das online oder in Skype for Business Server 2019 homed werden kann.

Wenn Sie über eine automatische Exchange UM-Telefonzentrale und ein Anrufwarteschlangensystem verfügen, müssen Sie die Details manuell aufzeichnen, bevor Sie zu Exchange Server 2019 oder Exchange online wechseln, wie unten beschrieben, und dann ein komplett neues System mithilfe des Teams Admin Centers implementieren.

## <a name="overview"></a>Übersicht

Wenn Ihre automatische Telefonanlage oder Anrufwarteschlange eine Dienstnummer benötigt, können die verschiedenen Abhängigkeiten in der folgenden Reihenfolge erfüllt werden:

1. Rufen Sie eine Dienstnummer ab.
2. Rufen Sie eine kostenlose Telefonsystem - [Virtuelle Benutzerlizenz](/MicrosoftTeams/teams-add-on-licensing/virtual-user) oder eine kostenpflichtige Telefonsystemlizenz ab, die mit dem Ressourcenkonto verwendet werden soll.
3. Erstellen Sie das Ressourcenkonto. Eine automatische Telefonwarteschlange oder Anrufwarteschlange muss über ein zugeordnetes Ressourcenkonto verfügen.
4. Warten Sie auf eine Active Directory-Synchronisierung zwischen online und lokal.
5. Weisen Sie dem Ressourcenkonto die Telefonsystemlizenz zu.
6. Weisen Sie dem Ressourcenkonto eine Dienstnummer zu.
7. Erstellen Sie eine Anrufwarteschlange oder automatische Telefonwarteschlange des Telefonsystems.
8. Ordnen Sie das Ressourcenkonto einer automatischen Telefonkonferenz oder Anrufwarteschlange zu: (New-CsApplicationInstanceAssociation).

Wenn die automatische Telefonanruf- oder Anrufwarteschlange unter einer automatischen Telefonwarteschlange der obersten Ebene geschachtelt ist, benötigt das zugeordnete Ressourcenkonto nur eine Telefonnummer, wenn Sie mehrere Einstiegspunkte in die Struktur der automatischen Telefonanten und Anrufwarteschlangen haben möchten.

Um Anrufe an Personen in Ihrer Organisation umzuleiten,  die online homed sind, müssen sie über eine Telefonsystemlizenz verfügen und für Enterprise-VoIP aktiviert sein oder über Microsoft 365- oder Office 365-Anrufpläne verfügen. Weitere [Informationen finden Sie unter Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses). Um sie für Enterprise-VoIP zu aktivieren, können Sie Windows PowerShell. Führen Sie beispielsweise folgende Ausführung aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Wenn die automatische Telefonanlage oder Anrufwarteschlange, die Sie erstellen, geschachtelt ist und keine Telefonnummer benötigt, wird der Vorgang wie die

1. Erstellen des Ressourcenkontos  
2. Warten auf eine Active Directory-Synchronisierung zwischen online und lokal
3. Erstellen einer automatischen Telefonanlage oder Anrufwarteschlange
4. Zuordnen des Ressourcenkontos zu einer automatischen Telefonanlage oder Anrufwarteschlange

## <a name="create-a-resource-account-with-a-phone-number"></a>Erstellen eines Ressourcenkontos mit einer Telefonnummer

Für das Erstellen eines Ressourcenkontos, das eine Telefonnummer verwendet, müssen die folgenden Aufgaben in der folgenden Reihenfolge ausgeführt werden:

1. Port oder eine gebührenpflichtige oder gebührenfreie Servicenummer. Die Nummer kann keinem anderen Sprachdienst oder Ressourcenkonto zugewiesen werden.

   Bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen, müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Dienstnummern erhalten oder portieren. Nachdem Sie die gebührenpflichtigen oder gebührenfreien Diensttelefonnummern erhalten haben, werden sie in **Microsoft Teams Admin Center** Voice Phone numbers angezeigt, und der aufgeführte Nummerntyp wird als Service -  >    >   **Toll-Free aufgeführt.**  Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen](/MicrosoftTeams/getting-service-phone-numbers) von Diensttelefonnummern oder wenn Sie eine vorhandene Dienstnummer übertragen möchten, unter Übertragen von Telefonnummern [an Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).

   Wenn Sie sich außerhalb der Vereinigten Staaten befinden, können Sie das Microsoft Teams Admin Center nicht verwenden, um Dienstnummern zu erhalten. Wechseln Sie [zu Verwalten von Telefonnummern für Ihre Organisation,](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) um zu sehen, wie Sie dies von außerhalb der USA aus tun.

2. Kaufen Sie eine Telefonsystemlizenz. Siehe:  
   - [Lizenz für telefonsystem–virtuelle Benutzer](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1- und E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Erstellen Sie ein lokales Ressourcenkonto, indem Sie das Cmdlet für jede automatische Telefonwarteschlange oder Anrufwarteschlange des Telefonsystems ausführen und jedem benutzer einen Namen, eine Sipadresse `New-CsHybridApplicationEndpoint` und so weiter geben.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [New-CsHybridApplicationEndpoint.](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

4. (Optional) Nachdem Ihre Ressourcenkonten erstellt wurden, können Sie entweder auf die Synchronisierung von AD zwischen online und lokal warten oder eine Synchronisierung erzwingen und mit der Onlinekonfiguration der automatischen Telefonwarteschlange oder der Anrufwarteschlangen fortfahren. Um eine Synchronisierung zu erzwingen, führen Sie den folgenden Befehl auf dem Computer mit AAD Connect aus (wenn Sie dies noch nicht getan haben, müssen Sie zum Ausführen des Befehls `import-module adsync` laden):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Start-ADSyncSyncCycle.](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)
    
    Hinweis: Zu diesem Zeitpunkt wurde das Konto möglicherweise synchronisiert, die Bereitstellung ist jedoch möglicherweise nicht abgeschlossen.  Überprüfen Sie die Ausgabe von [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint).  Wenn der synchronisierte Endpunkt die Bereitstellung noch nicht abgeschlossen hat, wird er hier nicht angezeigt.  Sie können den Status der Bereitstellungsanforderungen im M365-Portal unter [Teams Setup Status überprüfen.](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)  Diese Bereitstellungsphase kann bis zu 24 Stunden dauern.

5. Weisen Sie dem Ressourcenkonto die Lizenz "Telefonsystem – Virtuelles Benutzer- oder Telefonsystem" zu. Weitere [Informationen finden Sie unter Zuweisen von Microsoft Teams-Add-On-Lizenzen und](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) Zuweisen von Lizenzen zu [Benutzern.](/microsoft-365/admin/manage/assign-licenses-to-users)

   Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die kostenlose Lizenz Phone System - Virtual User verwenden. Dies bietet Telefonsystemfunktionen für Telefonnummern auf Organisatorischer Ebene und ermöglicht ihnen das Erstellen automatischer Telefonwarteschlangen- und Anrufwarteschlangenfunktionen.


6. Weisen Sie die Dienstnummer dem Ressourcenkonto zu. Verwenden Sie `Set-CsHybridApplicationEndpoint` den Befehl, um dem Ressourcenkonto eine Telefonnummer (mit der Option -LineURI) zuzuordnen.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsHybridApplicationEndpoint.](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps)

    Verwenden Sie das folgende Cmdlet, um einem Ressourcenkonto ein direktes Routing oder eine Hybridnummer zuzuordnen:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   Das Ressourcenkonto benötigt eine zugewiesene Telefonnummer, wenn es einer automatischen Telefonwarteschlange oder Anrufwarteschlange der obersten Ebene zugewiesen wird. Benutzertelefonnummern (Teilnehmer) können keinem Ressourcenkonto zugewiesen werden, sondern nur gebührenpflichtige oder gebührenfreie Telefonnummern können verwendet werden.

     Sie können Ihrem Ressourcenkonto ein Direktes Routing oder eine Hybridnummer zuweisen. Weitere Informationen finden Sie unter [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) and Plan Cloud auto [attendants](plan-cloud-auto-attendant.md).

     > [!NOTE]
     > Direkte Routingdienstnummern, die Ressourcenkonten für automatische Telefonwarteschlangen und Anrufwarteschlangen zugewiesen sind, werden nur für Microsoft Teams-Benutzer und -Agents unterstützt.

7. Erstellen Sie die automatische Telefonwarteschlange oder Anrufwarteschlange des Telefonsystems. Sehen Sie sich eines der folgenden Themen an:

   - [Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Erstellen einer Cloudanrufwarteschleife](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Ordnen Sie das Ressourcenkonto der automatischen Telefonanlage oder Anrufwarteschlange zu, die Sie zuvor ausgewählt haben.

## <a name="create-a-resource-account-without-a-phone-number"></a>Erstellen eines Ressourcenkontos ohne Telefonnummer

In diesem Abschnitt wird das Erstellen eines Ressourcenkontos erläutert, das lokal erstellt wird. Das Erstellen eines Ressourcenkontos, das online verwaltet wird, wird unter [Verwalten von Ressourcenkonten in Microsoft Teams erläutert.](/MicrosoftTeams/manage-resource-accounts)

Diese Schritte sind erforderlich, unabhängig davon, ob Sie eine neue automatische Telefonwarteschlange oder Eine Anrufwarteschlange erstellen oder die strukturieren, die ursprünglich in Exchange UM erstellt wurde.

Melden Sie sich beim Skype for Business-Front-End-Server an, und führen Sie die folgenden PowerShell-Cmdlets aus:

1. Erstellen Sie ein lokales Ressourcenkonto, indem Sie das Cmdlet für jede automatische Telefonwarteschlange oder Anrufwarteschlange des Telefonsystems ausführen und jedem benutzer einen Namen, eine Sipadresse `New-CsHybridApplicationEndpoint` und so weiter geben.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [New-CsHybridApplicationEndpoint.](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

2. (Optional) Nachdem Ihre Ressourcenkonten erstellt wurden, können Sie entweder auf die Synchronisierung von AD zwischen online und lokal warten oder eine Synchronisierung erzwingen und mit der Onlinekonfiguration der automatischen Telefonwarteschlange oder der Anrufwarteschlangen fortfahren. Um eine Synchronisierung zu erzwingen, führen Sie den folgenden Befehl auf dem Computer mit AAD Connect aus (wenn Sie dies noch nicht getan haben, müssen Sie zum Ausführen des Befehls `import-module adsync` laden):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Start-ADSyncSyncCycle.](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)

3. Erstellen Sie die automatische Telefonwarteschlange oder Anrufwarteschlange des Telefonsystems. Sehen Sie sich eines der folgenden Themen an:
   - [Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Erstellen einer Cloudanrufwarteschleife](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Ordnen Sie das Ressourcenkonto und die automatische Telefonanlage oder Anrufwarteschlange zu, die Sie zuvor ausgewählt haben.

## <a name="test-the-implementation"></a>Testen der Implementierung

Die beste Möglichkeit zum Testen der Implementierung besteht in der Anrufnummer, die für eine automatische Telefonwarteschlange oder Anrufwarteschlange konfiguriert ist, und eine Verbindung mit einem der Agents oder Menüs. Sie können auch schnell einen Testaufruf über die Schaltfläche **Test** im Admin Center-Aktionsbereich platzieren. Wenn Sie Änderungen an einer automatischen Telefonanlage oder Anrufwarteschlange vornehmen möchten, wählen Sie sie aus, und klicken Sie dann im Aktionsbereich auf **Bearbeiten**. 

> [!TIP]
> Wenn Ihr Ressourcenkonto Schwierigkeiten hat, einer Anrufwarteschlange oder automatischen Telefonwarteschlange zugewiesen zu werden, finden Sie weitere Informationen unter Bekannte Probleme für [Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) und im Abschnitt Beheben meiner Hybridanwendungsinstanzen im Microsoft Teams-Blog. [](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Verschieben einer automatischen Exchange UM-Telefonanlage oder Anrufwarteschlange in das Telefonsystem

Für die Migration von Exchange UM zum Telefonsystem müssen die Anrufwarteschlange und die Struktur der automatischen Telefonanlage neu aufgebaut werden, die direkte Migration von einer zur anderen wird nicht unterstützt. So implementieren Sie eine Reihe von Anrufwarteschlangen und automatischen Telefonkonferenzen neu:

1. Rufen Sie eine Liste aller automatischen Exchange UM-Telefonzentralen und Anrufwarteschlangen ab, indem Sie den folgenden Befehl auf dem Exchange 2013- oder 2016-System ausführen, während Sie als Administrator angemeldet sind:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Notieren Sie sich für jede aufgelistete Exchange UM-Anrufwarteschlange oder automatische Telefonanrufwarteschleife ihren Platz in der Struktur, den Einstellungen und erhalten Sie Kopien der zugeordneten Sound- oder Text-zu-Sprache-Dateien (die Guid in der Ausgabe ist der Name eines Ordners, in dem die Dateien gespeichert sind). Sie können diese Details durch Ausführen des Befehls erhalten:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Get-UMAutoAttendant.](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) Eine vollständige Liste der Optionen, die Sie möglicherweise erfassen müssen, finden Sie unter [UMAutoAttendant-Mitglieder,](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) die wichtigsten Optionen sind jedoch:

    - Geschäftszeiten
    - Außerhalb der Geschäftszeiten
    - Sprache
    - Feiertagszeitplan

3. Erstellen Sie neue lokale Endpunkte, wie zuvor beschrieben.
   Weisen Sie der automatischen Attendant auf oberster Ebene eine temporäre Nummer zu Testzwecken zu.

4. Konfigurieren Sie eine automatische Telefonanlage oder Anrufwarteschlange, die die Endpunkte verwendet, wie zuvor beschrieben.

5. Testen Sie die automatische Telefonanlage oder Anrufwarteschlange des Telefonsystems.

6. Zuweisen der Telefonnummer, die mit der Exchange UM-Anrufwarteschlange oder der automatischen Telefonwarteschlange verknüpft ist, der entsprechenden automatischen Telefonanlage oder Anrufwarteschlange.  

   Wenn Sie an dieser Stelle bereits UM Voicemail migriert haben, sollten Sie in der Lage sein, zu Exchange Server 2019 zu migrieren.

## <a name="see-also"></a>Siehe auch

[Erstellen einer Cloudanrufwarteschleife](/MicrosoftTeams/create-a-phone-system-call-queue)

[Was sind automatische Cloudtelefonzentralen?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Planen automatischer Cloudtelefonzentralen](plan-cloud-auto-attendant.md)

[Planen von Cloud-Anrufwarteschlangen](plan-call-queue.md)

[Planen des Cloud-Voicemaildiensts für lokale Benutzer](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Verwalten von Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)  -  \( So erstellen Sie Online-Ressourcenkonten\)