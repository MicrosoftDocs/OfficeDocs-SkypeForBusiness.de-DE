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
ms.openlocfilehash: 312947b379f62686e16718cc40f2be69b9eb6474
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510836"
---
# <a name="configure-resource-accounts"></a>Konfigurieren von Ressourcenkonten

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Server 2019-Hybridimplementierungen verwenden nur Clouddienste, die von Telefonsystem bereitgestellt werden, für Unified Messaging und werden nicht in Exchange Online integriert. In Skype for Business Server 2019 können Sie jetzt die Cloud-Anrufwarteschleifen und automatischen Telefonzentralen verwenden, die in den folgenden [Informationen mit Telefonsystem in Microsoft 365 oder Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)beschrieben werden.

Um eine Telefonsystem automatische Telefonzentrale oder Anrufwarteschleife mit Skype for Business Server 2019 zu verwenden, müssen Sie Ressourcenkonten erstellen, die als Anwendungsendpunkte fungieren und Telefonnummern zugewiesen werden können, und dann das Online Teams Admin Center verwenden, um die Anrufwarteschleife oder automatische Telefonzentrale zu konfigurieren. Dieses Ressourcenkonto kann online (siehe [Verwalten von Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) zum Erstellen von online verwalteten Ressourcenkonten) oder lokal verwaltet werden, wie in diesem Artikel beschrieben. In der Regel verfügen Sie über mehrere Telefonsystem Knoten für die automatische Telefonzentrale oder Anrufwarteschleife, die jeweils einem Ressourcenkonto zugeordnet sind, das online oder in Skype for Business Server 2019 verwaltet werden kann.

Wenn Sie über eine vorhandene Exchange automatische UM-Telefonzentrale und ein Anrufwarteschleifensystem verfügen, müssen Sie vor dem Wechsel zu Exchange Server 2019 oder Exchange online die Details manuell aufzeichnen, wie unten beschrieben, und dann ein völlig neues System mithilfe des Teams Admin Centers implementieren.

## <a name="overview"></a>Übersicht

Wenn Ihre Telefonsystem automatische Telefonzentrale oder Anrufwarteschleife eine Servicenummer benötigt, können die verschiedenen Abhängigkeiten in der folgenden Reihenfolge erfüllt werden:

1. Rufen Sie eine Dienstnummer ab.
2. Erhalten Sie eine kostenlose Telefonsystem – [virtuelle Benutzerlizenz](/MicrosoftTeams/teams-add-on-licensing/virtual-user) oder eine kostenpflichtige Telefonsystem-Lizenz für die Verwendung mit dem Ressourcenkonto.
3. Erstellen Sie das Ressourcenkonto. Eine automatische Telefonzentrale oder Anrufwarteschleife muss über ein zugeordnetes Ressourcenkonto verfügen.
4. Warten Sie, bis eine Active Directory-Synchronisierung zwischen online und lokal erfolgt.
5. Weisen Sie dem Ressourcenkonto die Telefonsystem Lizenz zu.
6. Weisen Sie dem Ressourcenkonto eine Dienstnummer zu.
7. Erstellen Sie eine Telefonsystem Anrufwarteschleife oder automatische Telefonzentrale.
8. Ordnen Sie das Ressourcenkonto einer automatischen Telefonzentrale oder Anrufwarteschleife zu: (New-CsApplicationInstanceAssociation).

Wenn die automatische Telefonzentrale oder Anrufwarteschleife unter einer automatischen Telefonzentrale der obersten Ebene geschachtelt ist, benötigt das zugeordnete Ressourcenkonto nur eine Telefonnummer, wenn Sie mehrere Einstiegspunkte in die Struktur der automatischen Telefonzentralen und Anrufwarteschleifen wünschen.

Um Anrufe an Personen in Ihrer Organisation umzuleiten, die online verwaltet werden, müssen sie über eine **Telefonsystem** Lizenz verfügen und für Enterprise-VoIP aktiviert sein oder über Microsoft 365 oder Office 365 Anrufpläne verfügen. Weitere Informationen finden Sie unter [Zuweisen Microsoft Teams Lizenzen.](/MicrosoftTeams/assign-teams-licenses) Um sie für Enterprise-VoIP zu aktivieren, können Sie Windows PowerShell verwenden. Führen Sie beispielsweise Folgendes aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Wenn die Telefon systemeigene automatische Telefonzentrale oder Anrufwarteschleife, die Sie erstellen, geschachtelt ist und keine Telefonnummer benötigt, sieht der Vorgang wie folgt aus:

1. Erstellen des Ressourcenkontos  
2. Warten Sie auf eine Active Directory-Synchronisierung zwischen Online und lokal
3. Erstellen einer Telefonsystem automatischen Telefonzentrale oder Anrufwarteschleife
4. Zuordnen des Ressourcenkontos zu einer Telefonsystem automatischen Telefonzentrale oder Anrufwarteschleife

## <a name="create-a-resource-account-with-a-phone-number"></a>Erstellen eines Ressourcenkontos mit einer Telefonnummer

Zum Erstellen eines Ressourcenkontos, das eine Telefonnummer verwendet, müssen die folgenden Aufgaben in der folgenden Reihenfolge ausgeführt werden:

1. Porten Oder erhalten Sie eine gebührenpflichtige oder gebührenfreie Servicenummer. Die Nummer kann keinem anderen VoIP-Dienst oder Ressourcenkonto zugewiesen werden.

   Bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen, müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Servicenummern abrufen oder portieren. Nachdem Sie die gebührenpflichtigen oder gebührenfreien Servicenummern erhalten haben, werden diese in **Microsoft Teams Admin Center**  >  **Voice** Telefon  >  **Nummern** angezeigt, und der aufgeführte **Nummerntyp** wird als **Service – gebührenfrei** aufgeführt. Informationen zum Abrufen Ihrer Servicenummern finden Sie unter ["Abrufen von Diensttelefonnummern"](/MicrosoftTeams/getting-service-phone-numbers) oder wenn Sie eine vorhandene Servicenummer übertragen möchten, lesen Sie ["Übertragen von Telefonnummern zu Teams."](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)

   Wenn Sie sich außerhalb der VEREINIGTEn Staaten befinden, können Sie das Microsoft Teams Admin Center nicht verwenden, um Servicenummern abzurufen. Wechseln Sie stattdessen zu ["Telefonnummern für Ihre Organisation verwalten",](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) um zu sehen, wie Sie dies außerhalb der VEREINIGTEn Staaten tun können.

2. Kaufen Sie eine Telefonsystem-Lizenz. Siehe:  
   - [Telefonsystem–Virtuelle Benutzerlizenz](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1- und E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Erstellen Sie ein lokales Ressourcenkonto, indem Sie das `New-CsHybridApplicationEndpoint` Cmdlet für jede Telefonsystem automatische Telefonzentrale oder Anrufwarteschleife ausführen und jedem einen Namen, eine SIP-Adresse usw. geben.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter ["New-CsHybridApplicationEndpoint".](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

4. (Optional) Nachdem Ihre Ressourcenkonten erstellt wurden, können Sie entweder warten, bis AD online und lokal synchronisiert wird, oder eine Synchronisierung erzwingen und mit der Onlinekonfiguration von Telefonsystem automatischen Telefonzentrale oder Anrufwarteschleifen fortfahren. Um eine Synchronisierung zu erzwingen, führen Sie den folgenden Befehl auf dem Computer aus, auf dem AAD Verbinden ausgeführt wird (wenn Sie dies noch nicht getan haben, müssten Sie `import-module adsync` laden, um den Befehl auszuführen):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Start-ADSyncSyncCycle.](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)
    
    Hinweis: An diesem Punkt ist das Konto möglicherweise synchronisiert, aber die Bereitstellung ist möglicherweise nicht abgeschlossen.  Überprüfen Sie die Ausgabe von [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint).  Wenn der synchronisierte Endpunkt die Bereitstellung noch nicht abgeschlossen hat, wird er hier nicht angezeigt.  Sie können den Status der Bereitstellungsanforderungen im M365-Portal unter [Teams Setupstatus](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)überprüfen.  Diese Bereitstellungsphase kann bis zu 24 Stunden dauern.

5. Weisen Sie dem Ressourcenkonto die Lizenz Telefonsystem - Virtueller Benutzer oder Telefonsystem zu. Weitere Informationen finden Sie unter [Zuweisen Microsoft Teams Add-On-Lizenzen](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) und [Zuweisen von Lizenzen zu Benutzern.](/microsoft-365/admin/manage/assign-licenses-to-users)

   Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die kostenlose Telefonsystem - Virtuelle Benutzerlizenz verwenden. Dadurch werden Telefonnummern auf Organisationsebene Telefonsystem Funktionen bereitgestellt, und Sie können Funktionen für automatische Telefonzentralen und Anrufwarteschleifen erstellen.


6. Weisen Sie die Dienstnummer dem Ressourcenkonto zu. Verwenden Sie den `Set-CsHybridApplicationEndpoint` Befehl, um dem Ressourcenkonto eine Telefonnummer (mit der Option -LineURI) zuzuweisen.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter ["Set-CsHybridApplicationEndpoint".](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps)

    Verwenden Sie das folgende Cmdlet, um einem Ressourcenkonto eine Direct Routing- oder Hybridnummer zuzuweisen:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   Das Ressourcenkonto benötigt eine zugewiesene Telefonnummer, wenn es einer automatischen Telefonzentrale oder Anrufwarteschleife auf oberster Ebene zugewiesen wird. Telefonnummern von Benutzern (Abonnenten) können keinem Ressourcenkonto zugewiesen werden, es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.

     Sie können Ihrem Ressourcenkonto eine Direct Routing- oder Hybridnummer zuweisen. Ausführliche Informationen finden Sie unter [Planen von direct Routing](/MicrosoftTeams/direct-routing-plan) und Planen der [automatischen Cloudtelefonzentralen.](plan-cloud-auto-attendant.md)

     > [!NOTE]
     > Direct Routing-Dienstnummern, die Ressourcenkonten für automatische Telefonzentralen und Anrufwarteschleifen zugewiesen sind, werden nur für Microsoft Teams Benutzer und Agents unterstützt.

7. Erstellen Sie die Telefonsystem automatische Telefonzentrale oder Anrufwarteschleife. Sehen Sie sich eines der folgenden Themen an:

   - [Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Erstellen einer Cloudanrufwarteschleife](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Ordnen Sie das Ressourcenkonto der Telefonsystem automatischen Telefonzentrale oder Anrufwarteschleife zu, die Sie zuvor ausgewählt haben.

## <a name="create-a-resource-account-without-a-phone-number"></a>Erstellen eines Ressourcenkontos ohne Telefonnummer

In diesem Abschnitt wird das Erstellen eines Ressourcenkontos erläutert, das lokal verwaltet wird. Das Erstellen eines online verwalteten Ressourcenkontos wird unter [Verwalten von Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)erläutert.

Diese Schritte sind unabhängig davon erforderlich, ob Sie eine völlig neue Telefonsystem automatische Telefonzentrale oder Anrufwarteschleifenstruktur erstellen oder eine Struktur neu erstellen, die ursprünglich in Exchange UM erstellt wurde.

Melden Sie sich beim Skype for Business Front-End-Server an, und führen Sie die folgenden PowerShell-Cmdlets aus:

1. Erstellen Sie ein lokales Ressourcenkonto, indem Sie das `New-CsHybridApplicationEndpoint` Cmdlet für jede Telefonsystem automatische Telefonzentrale oder Anrufwarteschleife ausführen und jedem einen Namen, eine SIP-Adresse usw. geben.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter ["New-CsHybridApplicationEndpoint".](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

2. (Optional) Nachdem Ihre Ressourcenkonten erstellt wurden, können Sie entweder warten, bis AD online und lokal synchronisiert wird, oder eine Synchronisierung erzwingen und mit der Onlinekonfiguration von Telefonsystem automatischen Telefonzentrale oder Anrufwarteschleifen fortfahren. Um eine Synchronisierung zu erzwingen, führen Sie den folgenden Befehl auf dem Computer aus, auf dem AAD Verbinden ausgeführt wird (wenn Sie dies noch nicht getan haben, müssten Sie `import-module adsync` laden, um den Befehl auszuführen):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Start-ADSyncSyncCycle.](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)

3. Erstellen Sie die Telefonsystem automatische Telefonzentrale oder Anrufwarteschleife. Sehen Sie sich eines der folgenden Themen an:
   - [Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Erstellen einer Cloudanrufwarteschleife](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Ordnen Sie das Ressourcenkonto und die Telefonsystem automatische Telefonzentrale oder Anrufwarteschleife zu, die Sie zuvor ausgewählt haben.

## <a name="test-the-implementation"></a>Testen der Implementierung

Die beste Möglichkeit zum Testen der Implementierung besteht darin, die für eine Telefonsystem automatische Telefonzentrale oder Anrufwarteschleife konfigurierte Nummer aufzurufen und eine Verbindung mit einem der Agents oder Menüs herzustellen. Sie können einen Testanruf auch schnell über die **Schaltfläche "Test"** im Admin Center-Aktionsbereich tätigen. Wenn Sie Änderungen an einer Telefonsystem automatischen Telefonzentrale oder Anrufwarteschleife vornehmen möchten, wählen Sie diese aus, und klicken Sie dann im Aktionsbereich auf **Bearbeiten.** 

> [!TIP]
> Wenn Ihr Ressourcenkonto Schwierigkeiten hat, einer Anrufwarteschleife oder automatischen Telefonzentrale zugewiesen zu werden, finden Sie informationen zu [bekannten Problemen für Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) und im Abschnitt ["Beheben meiner Hybridanwendungsinstanzen"](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) im Microsoft Teams Blog.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Verschieben einer automatischen UM-Telefonzentrale oder Anrufwarteschleife Exchange in Telefonsystem

Für die Migration von Exchange UM zu Telefonsystem müssen die Anrufwarteschleife und die automatische Telefonzentralenstruktur neu erstellt werden. Die direkte Migration von einem zum anderen wird nicht unterstützt. So implementieren Sie eine Reihe von Anrufwarteschleifen und automatischen Telefonzentralen neu:

1. Rufen Sie eine Liste aller Exchange automatischen UM-Telefonzentralen und Anrufwarteschleifen ab, indem Sie den folgenden Befehl auf dem system Exchange 2013 oder 2016 ausführen, während Sie als Administrator angemeldet sind:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Notieren Sie sich für jede aufgeführte Exchange UM-Anrufwarteschleife oder automatische Telefonzentrale ihren Platz in der Struktur, den Einstellungen und rufen Sie Kopien der zugehörigen Sound- oder Text-zu-Sprache-Dateien ab (die GUID in der Ausgabe ist der Name eines Ordners, in dem die Dateien gespeichert sind). Sie können diese Details abrufen, indem Sie den folgenden Befehl ausführen:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter ["Get-UMAutoAttendant".](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) Eine vollständige Liste der Optionen, die Sie möglicherweise erfassen müssen, finden Sie unter [UMAutoAttendant-Mitglieder,](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) aber die wichtigsten Optionen, die Sie notieren müssen, sind:

    - Geschäftszeiten
    - Nicht geschäftszeiten
    - Sprache
    - Feiertagszeitplan

3. Erstellen Sie neue lokale Endpunkte wie zuvor beschrieben.
   Weisen Sie der automatischen Telefonzentrale der obersten Ebene zu Testzwecken eine temporäre Nummer zu.

4. Konfigurieren Sie eine Telefonsystem automatische Telefonzentrale oder Anrufwarteschleife, die die Endpunkte wie zuvor beschrieben verwendet.

5. Testen Sie die Telefonsystem automatische Telefonzentrale oder Anrufwarteschleife.

6. Weisen Sie die Telefonnummer, die mit der Exchange UM-Anrufwarteschleife oder automatischen Telefonzentrale verknüpft ist, der entsprechenden Telefonsystem automatischen Telefonzentrale oder Anrufwarteschleife neu zu.  

   Wenn Sie um Voicemail bereits migriert haben, sollten Sie jetzt in der Lage sein, zu Exchange Server 2019 zu migrieren.

## <a name="see-also"></a>Siehe auch

[Erstellen einer Cloudanrufwarteschleife](/MicrosoftTeams/create-a-phone-system-call-queue)

[Was sind automatische Cloudtelefonzentralen?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Planen automatischer Cloudtelefonzentralen](plan-cloud-auto-attendant.md)

[Planen von Cloud-Anrufwarteschlangen](plan-call-queue.md)

[Planen Cloud-Voicemail Diensts für lokale Benutzer](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Verwalten von Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)  -  \( zum Erstellen von online verwalteten Ressourcenkonten\)