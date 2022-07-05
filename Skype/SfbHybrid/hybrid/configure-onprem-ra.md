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
ms.localizationpriority: medium
ms.collection: ''
description: Richten Sie ein Ressourcenkonto für Skype for Business Server 2019 ein.
ms.openlocfilehash: ebaf79229097df8d3477b4d9b74504c278bfd59c
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615611"
---
# <a name="configure-resource-accounts"></a>Konfigurieren von Ressourcenkonten

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Server 2019-Hybridimplementierungen verwenden nur cloudbasierte Dienste des Telefonsystems für Unified Messaging und können nicht in Exchange Online integriert werden. In Skype for Business Server 2019 können Sie jetzt die cloudbasierten Anrufwarteschleifen und automatischen Telefonzentralen verwenden, die unter ["So erhalten Sie das Telefonsystem in Microsoft 365 oder Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)" beschrieben sind.

Um eine automatische Telefonzentrale oder Anrufwarteschleife mit Skype for Business Server 2019 zu verwenden, müssen Sie Ressourcenkonten erstellen, die als Anwendungsendpunkte fungieren und Telefonnummern zugewiesen werden können. Verwenden Sie dann das Online-Teams Admin Center, um die Anrufwarteschleife oder automatische Telefonzentrale zu konfigurieren. Dieses Ressourcenkonto kann online verwaltet werden (siehe [Verwalten von Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) , um Online verwaltete Ressourcenkonten zu erstellen) oder lokal, wie in diesem Artikel beschrieben. In der Regel verfügen Sie über mehrere Knoten der automatischen Telefonzentrale oder Anrufwarteschleife, die jeweils einem Ressourcenkonto zugeordnet sind, das online oder in Skype for Business Server 2019 verwaltet werden kann.

Wenn Sie über eine vorhandene automatische Exchange UM-Telefonzentrale und ein System für die Anrufwarteschleife verfügen, müssen Sie vor dem Umstieg auf Exchange Server 2019 oder Exchange Online die Details manuell aufzeichnen, wie unten beschrieben, und dann ein völlig neues System mithilfe des Teams Admin Centers implementieren.

## <a name="overview"></a>Übersicht

Wenn Ihre automatische Telefonzentrale oder Anrufwarteschleife eine Dienstnummer benötigt, können die verschiedenen Abhängigkeiten in der folgenden Reihenfolge erfüllt werden:

1. Rufen Sie eine Dienstnummer ab.
2. Rufen Sie eine kostenlose [Microsoft Teams Telefon Resource Account-Lizenz](/MicrosoftTeams/teams-add-on-licensing/virtual-user) oder eine kostenpflichtige Telefonsystemlizenz für die Verwendung mit dem Ressourcenkonto ab.
3. Erstellen Sie das Ressourcenkonto. Eine automatische Telefonzentrale oder Anrufwarteschleife ist erforderlich, um über ein zugeordnetes Ressourcenkonto verfügen zu können.
4. Warten Sie auf eine Active Directory-Synchronisierung zwischen online und lokal.
5. Weisen Sie dem Ressourcenkonto die Telefonsystemlizenz zu.
6. Weisen Sie dem Ressourcenkonto eine Dienstnummer zu.
7. Erstellen Sie eine Telefonsystem-Anrufwarteschleife oder eine automatische Telefonzentrale.
8. Ordnen Sie das Ressourcenkonto einer automatischen Telefonzentrale oder Anrufwarteschleife zu: (New-CsApplicationInstanceAssociation).

Wenn die automatische Telefonzentrale oder Anrufwarteschleife unter einer automatischen Telefonzentrale auf oberster Ebene geschachtelt ist, benötigt das zugeordnete Ressourcenkonto nur eine Telefonnummer, wenn Sie mehrere Einstiegspunkte in die Struktur der automatischen Telefonzentralen und Anrufwarteschleifen benötigen.

Um Anrufe an Personen in Ihrer Organisation umzuleiten, die online verwaltet werden, müssen sie über eine **Telefonsystemlizenz** verfügen und für Enterprise-VoIP aktiviert sein oder über Microsoft 365- oder Office 365-Anrufpläne verfügen. Siehe [Zuweisen von Microsoft Teams-Lizenzen](/MicrosoftTeams/assign-teams-licenses). Um sie für Enterprise-VoIP zu aktivieren, können Sie Windows PowerShell verwenden. Führen Sie beispielsweise Folgendes aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Wenn die automatische Telefonzentrale oder Anrufwarteschleife, die Sie erstellen, geschachtelt ist und keine Telefonnummer benötigt, gehen Sie wie folgt vor:

1. Erstellen des Ressourcenkontos  
2. Warten auf eine Active Directory-Synchronisierung zwischen online und lokal
3. Erstellen einer automatischen Telefonzentrale oder Anrufwarteschleife für das Telefonsystem
4. Zuordnen des Ressourcenkontos zu einer automatischen Telefonzentrale oder Anrufwarteschleife des Telefonsystems

## <a name="create-a-resource-account-with-a-phone-number"></a>Erstellen eines Ressourcenkontos mit einer Telefonnummer

Zum Erstellen eines Ressourcenkontos, das eine Telefonnummer verwendet, müssen die folgenden Aufgaben in der folgenden Reihenfolge ausgeführt werden:

1. Portier oder erhalte eine gebührenpflichtige oder gebührenfreie Servicenummer. Die Nummer kann keinem anderen VoIP-Dienst- oder Ressourcenkonto zugewiesen werden.

   Bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen, müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Servicenummern abrufen oder portieren. Nachdem Sie die gebührenpflichtigen oder gebührenfreien Servicetelefonnummern erhalten haben, werden diese in **Microsoft Teams Admin Center** > **Voice** > **Phone Numbers** angezeigt, und der aufgeführte **Nummerntyp** wird als **Service - Gebührenfrei** aufgeführt. Informationen zum Abrufen Ihrer Servicenummern finden Sie unter ["Abrufen von Servicetelefonnummern](/MicrosoftTeams/getting-service-phone-numbers) ", oder wenn Sie eine vorhandene Servicenummer übertragen möchten, lesen Sie ["Übertragen von Telefonnummern an Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)".

   Wenn Sie sich außerhalb des USA befinden, können Sie das Microsoft Teams Admin Center nicht verwenden, um Servicenummern zu erhalten. Wechseln Sie stattdessen zu ["Telefonnummern für Ihre Organisation verwalten](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)", um zu sehen, wie Sie dies von außerhalb der USA erledigen.

2. Kaufen Sie eine Telefonsystemlizenz. Siehe:  
   - [Microsoft Teams Telefon Resource Account-Lizenz](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1- und E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Erstellen Sie ein lokales Ressourcenkonto, indem Sie das `New-CsHybridApplicationEndpoint` Cmdlet für jede automatische Telefonsystemzentrale oder Anrufwarteschleife ausführen und jedem einen Namen, eine SIP-Adresse usw. zuweisen.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .

4. (Optional) Nachdem Ihre Ressourcenkonten erstellt wurden, können Sie entweder warten, bis AD zwischen online und lokal synchronisiert wird, oder eine Synchronisierung erzwingen und mit der Onlinekonfiguration der automatischen Telefonzentrale des Telefonsystems oder der Anrufwarteschleifen fortfahren. Um eine Synchronisierung zu erzwingen, führen Sie den folgenden Befehl auf dem Computer aus, auf dem AAD Connect ausgeführt wird (wenn Sie dies noch nicht getan haben, müssen Sie den Befehl laden `import-module adsync` , um den Befehl auszuführen):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter ["Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) ".

    Hinweis: Zu diesem Zeitpunkt wurde das Konto möglicherweise synchronisiert, die Bereitstellung ist jedoch möglicherweise nicht abgeschlossen.  Überprüfen Sie die Ausgabe von [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint).  Wenn der synchronisierte Endpunkt die Bereitstellung noch nicht abgeschlossen hat, wird er hier nicht angezeigt.  Sie können den Status der Bereitstellungsanforderungen im M365-Portal unter ["Teams-Setupstatus"](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning) überprüfen.  Diese Bereitstellungsphase kann bis zu 24 Stunden dauern.

5. Weisen Sie dem **Ressourcenkonto die Microsoft Teams Telefon Ressourcenkontolizenz** oder **Teams Telefon Standard** Lizenz zu. Weitere Informationen [finden Sie unter Zuweisen von Microsoft Teams-Add-On-Lizenzen](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) und [Zuweisen von Lizenzen zu Benutzern](/microsoft-365/admin/manage/assign-licenses-to-users).

   Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die lizenzfreie **Microsoft Teams Telefon Ressourcenkonto** verwenden. Dadurch werden Telefonsystemfunktionen für Telefonnummern auf Organisationsebene bereitgestellt, und Sie können funktionen für automatische Telefonzentralen und Anrufwarteschleifen erstellen.

6. Weisen Sie die Dienstnummer dem Ressourcenkonto zu. Verwenden Sie den `Set-CsHybridApplicationEndpoint` Befehl, um dem Ressourcenkonto eine Telefonnummer (mit der Option -LineURI) zuzuweisen.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsHybridApplicationEndpoint](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) .

    Verwenden Sie das folgende Cmdlet, um einem Ressourcenkonto eine Direct Routing- oder Hybridnummer zuzuweisen:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   Das Ressourcenkonto benötigt eine zugewiesene Telefonnummer, wenn es einer automatischen Telefonzentrale oder Anrufwarteschleife auf oberster Ebene zugewiesen wird. Benutzertelefonnummern (Abonnent) können keinem Ressourcenkonto zugewiesen werden, es können nur gebührenpflichtige oder gebührenfreie Telefonnummern des Diensts verwendet werden.

     Sie können Ihrem Ressourcenkonto eine Direct Routing- oder Hybridnummer zuweisen. Ausführliche Informationen finden Sie unter [Planen von Direct Routing](/MicrosoftTeams/direct-routing-plan) und [Planen automatischer Telefonzentralen](plan-cloud-auto-attendant.md) in der Cloud.

     > [!NOTE]
     > Direct Routing-Dienstnummern, die Ressourcenkonten für automatische Telefonzentralen und Anrufwarteschleifen zugewiesen sind, werden nur für Microsoft Teams-Benutzer und -Agents unterstützt.

7. Erstellen Sie die automatische Telefonzentrale oder Anrufwarteschleife des Telefonsystems. Sehen Sie sich eines der folgenden Themen an:

   - [Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Erstellen einer Cloudanrufwarteschleife](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Ordnen Sie das Ressourcenkonto der automatischen Telefonzentrale oder Anrufwarteschleife des Telefonsystems zu, die Sie zuvor ausgewählt haben.

## <a name="create-a-resource-account-without-a-phone-number"></a>Erstellen eines Ressourcenkontos ohne Telefonnummer

In diesem Abschnitt wird das Erstellen eines Ressourcenkontos erläutert, das lokal verwaltet wird. Das Erstellen eines Ressourcenkontos, das online verwaltet wird, wird unter [Verwalten von Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) erläutert.

Diese Schritte sind erforderlich, unabhängig davon, ob Sie eine völlig neue automatische Telefonzentrale oder Anrufwarteschleifenstruktur erstellen oder die ursprünglich in Exchange UM erstellte Struktur neu erstellen.

Melden Sie sich beim Skype for Business Front-End-Server an, und führen Sie die folgenden PowerShell-Cmdlets aus:

1. Erstellen Sie ein lokales Ressourcenkonto, indem Sie das `New-CsHybridApplicationEndpoint` Cmdlet für jede automatische Telefonsystemzentrale oder Anrufwarteschleife ausführen und jedem einen Namen, eine SIP-Adresse usw. zuweisen.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .

2. (Optional) Nachdem Ihre Ressourcenkonten erstellt wurden, können Sie entweder warten, bis AD zwischen online und lokal synchronisiert wird, oder eine Synchronisierung erzwingen und mit der Onlinekonfiguration der automatischen Telefonzentrale des Telefonsystems oder der Anrufwarteschleifen fortfahren. Um eine Synchronisierung zu erzwingen, führen Sie den folgenden Befehl auf dem Computer aus, auf dem AAD Connect ausgeführt wird (wenn Sie dies noch nicht getan haben, müssen Sie den Befehl laden `import-module adsync` , um den Befehl auszuführen):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter ["Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) ".

3. Erstellen Sie die automatische Telefonzentrale oder Anrufwarteschleife des Telefonsystems. Sehen Sie sich eines der folgenden Themen an:
   - [Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Erstellen einer Cloudanrufwarteschleife](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Ordnen Sie das Ressourcenkonto und die automatische Telefonzentrale oder Anrufwarteschleife des Telefonsystems zu, die Sie zuvor ausgewählt haben.

## <a name="test-the-implementation"></a>Testen der Implementierung

Die beste Möglichkeit zum Testen der Implementierung besteht darin, die für eine automatische Telefonzentrale oder Anrufwarteschleife konfigurierte Nummer aufzurufen und eine Verbindung mit einem der Agents oder Menüs herzustellen. Sie können einen Testanruf auch schnell mithilfe der **Schaltfläche "Testen"** im Admin Center-Aktionsbereich tätigen. Wenn Sie Änderungen an einer automatischen Telefonzentrale oder Anrufwarteschleife des Telefonsystems vornehmen möchten, wählen Sie diese aus, und klicken Sie dann im Aktionsbereich auf **"Bearbeiten"**. 

> [!TIP]
> Wenn Ihr Ressourcenkonto Schwierigkeiten mit der Zuweisung zu einer Anrufwarteschleife oder einer automatischen Telefonzentrale hat, lesen Sie [bekannte Probleme für Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) und den Abschnitt ["Beheben meiner Hybridanwendungsinstanzen](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) " im Microsoft Teams-Blog.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Verschieben einer automatischen Exchange UM-Telefonzentrale oder Anrufwarteschleife in das Telefonsystem

Für die Migration von Exchange UM zum Telefonsystem müssen die Anrufwarteschleife und die automatische Telefonzentralenstruktur neu erstellt werden. Eine direkte Migration von einem zum anderen wird nicht unterstützt. So implementieren Sie eine Reihe von Anrufwarteschleifen und automatischen Telefonzentralen erneut:

1. Rufen Sie eine Liste aller automatischen Exchange UM-Telefonzentralen und Anrufwarteschleifen ab, indem Sie den folgenden Befehl auf dem Exchange 2013- oder 2016-System ausführen, während Sie als Administrator angemeldet sind:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Notieren Sie sich für jede aufgelistete Exchange UM-Anrufwarteschleife oder automatische Telefonzentrale ihren Platz in der Struktur, den Einstellungen, und rufen Sie Kopien der zugehörigen Audio- oder Text-zu-Sprache-Dateien ab (die GUID in der Ausgabe ist der Name eines Ordners, in dem die Dateien gespeichert sind). Sie können diese Details abrufen, indem Sie den Befehl ausführen:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) . Eine vollständige Liste der Optionen, die Sie möglicherweise erfassen müssen, finden Sie bei [UMAutoAttendant-Mitgliedern](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) , aber die wichtigsten Optionen, die Sie notieren sollten, sind:

    - Geschäftszeiten
    - Nicht geschäftszeiten
    - Sprache
    - Feiertagszeitplan

3. Erstellen Sie neue lokale Endpunkte wie zuvor beschrieben.
   Weisen Sie der automatischen Telefonzentrale der obersten Ebene zu Testzwecken eine temporäre Nummer zu.

4. Konfigurieren Sie eine automatische Telefonzentrale oder Anrufwarteschleife, die die Endpunkte verwendet, wie zuvor beschrieben.

5. Testen Sie die automatische Telefonzentrale oder Anrufwarteschleife des Telefonsystems.

6. Weisen Sie die Telefonnummer, die mit der Exchange UM-Anrufwarteschleife oder der automatischen Telefonzentrale verknüpft ist, der entsprechenden automatischen Telefonzentrale oder Anrufwarteschleife des Telefonsystems neu zu.  

   Wenn Sie bereits UM Voicemail migriert haben, sollten Sie jetzt in der Lage sein, zu Exchange Server 2019 zu migrieren.

## <a name="see-also"></a>Siehe auch

[Erstellen einer Cloudanrufwarteschleife](/MicrosoftTeams/create-a-phone-system-call-queue)

[Was sind automatische Cloudtelefonzentralen?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Planen automatischer Cloudtelefonzentralen](plan-cloud-auto-attendant.md)

[Planen von Cloud-Anrufwarteschlangen](plan-call-queue.md)

[Planen Cloud-Voicemail Diensts für lokale Benutzer](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Verwalten von Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \( so erstellen Sie Online verwaltete Ressourcenkonten\)