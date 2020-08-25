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
description: Einrichten eines Ressourcenkontos für Skype for Business Server 2019.
ms.openlocfilehash: f3a9166f6e1bb9659a7fb43b9e7c35dba673f176
ms.sourcegitcommit: 32023931b607542cffadef74383e3ecd47db4ab6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868684"
---
# <a name="configure-resource-accounts"></a>Konfigurieren von Ressourcenkonten

In Skype for Business Server 2019-Hybrid Implementierungen werden nur Cloud-Dienste verwendet, die vom Telefon System für Unified Messaging bereitgestellt werden und nicht in Exchange Online integriert werden können. In Skype for Business Server 2019 können Sie nun die Cloud-Anrufwarteschlangen und die hier beschriebenen automatischen Telefonzentralen verwenden, [was Sie mit dem Telefon System in Microsoft 365 oder Office 365 erhalten](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

Um eine automatische Telefonzentrale oder eine Anrufwarteschlange mit Skype for Business Server 2019 zu verwenden, müssen Sie Ressourcenkonten erstellen, die als Anwendungsendpunkte fungieren und Telefonnummern zugewiesen werden können, und dann mithilfe des Online Teams Admin Center die Anrufwarteschlange oder die automatische Telefonzentrale konfigurieren. Dieses Ressourcenkonto kann online verwaltet werden (Weitere Informationen finden Sie unter [Verwalten von Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) zum Erstellen von Online verwalteten Ressourcenkonten) oder lokal wie in diesem Artikel beschrieben. Normalerweise verfügen Sie über mehrere Telefon System-automatische Telefonzentralen oder Anrufwarteschlangen-Knoten, die jeweils einem Ressourcenkonto zugeordnet sind, das Online oder in Skype for Business Server 2019 verwaltet werden kann.

Wenn Sie über eine Exchange um automatische Telefonzentrale und ein Anruf Warteschlangensystem verfügen, müssen Sie vor dem Wechsel zu Exchange Server 2019 oder Exchange Online die Details wie unten beschrieben manuell aufzeichnen und dann mithilfe des Teams Admin Center ein vollständig neues System implementieren.

## <a name="overview"></a>Übersicht

Wenn für die automatische Telefonzentrale oder die Anrufwarteschlange eine Dienstnummer erforderlich ist, können die verschiedenen Abhängigkeiten in der folgenden Reihenfolge erfüllt werden:

1. Rufen Sie eine Dienstnummer ab.
2. Erhalten Sie eine ﻿kostenlose Telefonsystem- [virtuelle Benutzerlizenz](/MicrosoftTeams/teams-add-on-licensing/virtual-user) oder eine gebührenpflichtige Telefonsystem Lizenz, die mit dem Ressourcenkonto verwendet werden soll.
3. Erstellen Sie das Ressourcenkonto. Für eine automatische Telefonzentrale oder Anrufwarteschlange ist ein zugeordnetes Ressourcenkonto erforderlich.
4. Warten Sie, bis eine Active Directory-Synchronisierung zwischen Online und lokal durchsteht.
5. Weisen Sie dem Ressourcenkonto die Telefon System Lizenz zu.
6. Weisen Sie dem Ressourcenkonto eine Dienstnummer zu.
7. Dient zum Erstellen einer Telefon System-Anrufwarteschlange oder einer automatischen Telefonzentrale.
8. Ordnen Sie das Ressourcenkonto einer automatischen Telefonzentrale oder Anrufwarteschlange zu: (New-CsApplicationInstanceAssociation).

Wenn die automatische Telefonzentrale oder die Anrufwarteschlange unter einer automatischen Telefonzentrale auf oberster Ebene geschachtelt ist, benötigt das zugehörige Ressourcenkonto nur eine Telefonnummer, wenn Sie mehrere Einstiegspunkte in die Struktur von automatischen Telefonzentralen und Anrufwarteschlangen erhalten möchten.

Um Anrufe an Personen in Ihrer Organisation umzuleiten, die Online verwaltet werden, müssen Sie über eine **Telefon System** Lizenz verfügen und für Enterprise-VoIP aktiviert sein oder Microsoft 365 oder Office 365 Anrufpläne haben. Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Lizenzen](/MicrosoftTeams/assign-teams-licenses). Um Sie für Enterprise-VoIP zu aktivieren, können Sie Windows PowerShell verwenden. Führen Sie beispielsweise Folgendes aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Wenn die automatische Telefonzentrale oder die Anrufwarteschlange, die Sie erstellen, geschachtelt ist und keine Telefonnummer benötigt, lautet der Vorgang wie folgt:

1. Erstellen des Ressourcenkontos  
2. Warten auf eine Active Directory-Synchronisierung zwischen Online und lokal
3. Erstellen einer automatischen Telefonzentrale oder Anrufwarteschlange
4. Zuordnen des Ressourcenkontos zu einer automatischen Telefonzentrale oder Anrufwarteschlange

## <a name="create-a-resource-account-with-a-phone-number"></a>Erstellen eines Ressourcenkontos mit einer Telefonnummer

Zum Erstellen eines Ressourcenkontos, das eine Telefonnummer verwendet, müssen die folgenden Aufgaben in der folgenden Reihenfolge ausgeführt werden:

1. Port oder erhalten Sie eine gebührenpflichtige oder gebührenfreie Servicenummer. Die Nummer kann keinem anderen VoIP-Dienst oder Ressourcenkonto zugewiesen werden.

   Bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen, müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Servicenummern abrufen oder portieren. Nachdem Sie die gebührenpflichtigen oder gebührenfreien Service-Telefonnummern erhalten haben, werden Sie in **Microsoft Teams Admin Center**  >  **-VoIP**-  >  **Telefonnummern**angezeigt, und der aufgeführte **Nummerntyp** wird als **Dienst gebührenfrei**aufgeführt. Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Dienst Rufnummern](/MicrosoftTeams/getting-service-phone-numbers) oder wenn Sie eine vorhandene Dienstnummer übertragen möchten, unter [übertragen von Telefonnummern zu Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).

   Wenn Sie sich außerhalb der USA befinden, können Sie das Microsoft Teams Admin Center nicht zum Abrufen von Dienstnummern verwenden. Wechseln Sie zu [Verwalten von Telefonnummern für Ihre Organisation](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) , anstatt zu sehen, wie es von außerhalb der Vereinigten Staaten zu tun.

2. Kaufen Sie eine Telefon System Lizenz. Siehe:  
   - [Telefon System – virtuelle Benutzerlizenz](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1- und E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5-Business-Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Erstellen Sie ein lokales Ressourcenkonto, indem Sie das `New-CsHybridApplicationEndpoint` Cmdlet für jede automatische Telefonzentrale oder Anrufwarteschlange ausführen und jedem einen Namen, eine SIP-Adresse usw. geben.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .

4. Optional Sobald Ihre Ressourcenkonten erstellt wurden, können Sie entweder warten, bis AD zwischen Online und lokal synchronisiert wird, oder eine Synchronisierung erzwingen und mit der automatischen Telefonzentrale oder Anrufwarteschlangen in Online Konfiguration fortfahren. Um eine Synchronisierung zu erzwingen, führen Sie den folgenden Befehl auf dem Computer aus, auf dem AAD Connect ausgeführt wird (wenn Sie nicht bereits fertig sind, müssen Sie `import-module adsync` zum Ausführen des Befehls laden):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .
    
    Hinweis: zu diesem Zeitpunkt ist das Konto möglicherweise synchronisiert, aber die Einrichtung ist möglicherweise nicht abgeschlossen.  Überprüfen Sie die Ausgabe von [Get-CsOnlineApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint).  Wenn der synchronisierte Endpunkt noch nicht abgeschlossen wurde, wird er hier nicht angezeigt.  Sie können den Status der Anforderungs Anforderungen im M365-Portal unter [Teams-Setup Status](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)überprüfen.  Diese Vorbereitungsphase kann bis zu 24 Stunden dauern.

5. Weisen Sie dem Ressourcenkonto die Lizenz für das Telefonsystem-Virtual User oder Phone System zu. Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Add-on-Lizenzen](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) und [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

   Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie nun die ﻿kostenlose Telefon System-virtuelle Benutzerlizenz verwenden. Dadurch werden Telefon System Funktionen für Telefonnummern auf Organisationsebene bereitgestellt, und Sie können eine automatische Telefonzentrale und Funktionen für die Anrufwarteschlange erstellen.


6. Weisen Sie die Dienstnummer dem Ressourcenkonto zu. Verwenden Sie den `Set-CsHybridApplicationEndpoint` Befehl, um dem Ressourcenkonto eine Telefonnummer zuzuweisen (mit der Option-LineURI).

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Festlegen von CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) .

    Verwenden Sie das folgende Cmdlet, um einem Ressourcenkonto eine direkte Weiterleitung oder eine Hybrid Nummer zuzuweisen:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   Das Ressourcenkonto benötigt eine zugewiesene Telefonnummer, wenn es einer automatischen Telefonzentrale oder einer Anrufwarteschlange zugewiesen wird. Benutzer (Teilnehmer-) Telefonnummern können keinem Ressourcenkonto zugewiesen werden, es dürfen nur Dienst gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.

     Sie können Ihrem Ressourcenkonto eine direkte Routing-oder Hybrid Nummer zuweisen. Ausführliche Informationen finden Sie unter [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) und [Plan Cloud Auto Attendants](plan-cloud-auto-attendant.md).

     > [!NOTE]
     > Direkte Routing-Dienstnummern, die Ressourcenkonten für die automatische Telefonzentrale und Anrufwarteschlangen zugewiesen werden, werden nur für Microsoft Teams-Benutzer und-Agents unterstützt.

7. Erstellen Sie die automatische Telefonzentrale oder die Anrufwarteschlange. Sehen Sie sich eines der folgenden Themen an:

   - [Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Erstellen einer Cloudanrufwarteschleife](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Ordnen Sie das Ressourcenkonto der automatischen Telefonzentrale oder der Anrufwarteschlange zu, die Sie zuvor ausgewählt haben.

Ein Beispiel für eine Small Business-Implementierung ist im  [Small Business-Beispiel verfügbar: Einrichten einer automatischen Telefonzentrale](/microsoftteams/tutorial-org-aa) und eines [Beispiels für kleine Unternehmen – Einrichten einer Anrufwarteschlange](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq).

## <a name="create-a-resource-account-without-a-phone-number"></a>Erstellen eines Ressourcenkontos ohne Telefonnummer

In diesem Abschnitt wird das Erstellen eines Ressourcenkontos erläutert, das lokal verwaltet wird. Das Erstellen eines Online verwalteten Ressourcenkontos wird unter Verwalten von [Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)erläutert.

Diese Schritte sind erforderlich, unabhängig davon, ob Sie eine neue automatische Telefonzentrale oder eine Anruf Warteschlangen Struktur erstellen oder die ursprünglich in Exchange um erstellte Struktur neu erstellen.

Melden Sie sich am Skype for Business Front-End-Server an, und führen Sie die folgenden PowerShell-Cmdlets aus:

1. Erstellen Sie ein lokales Ressourcenkonto, indem Sie das `New-CsHybridApplicationEndpoint` Cmdlet für jede automatische Telefonzentrale oder Anrufwarteschlange ausführen und jedem einen Namen, eine SIP-Adresse usw. geben.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .

2. Optional Sobald Ihre Ressourcenkonten erstellt wurden, können Sie entweder warten, bis AD zwischen Online und lokal synchronisiert wird, oder eine Synchronisierung erzwingen und mit der automatischen Telefonzentrale oder Anrufwarteschlangen in Online Konfiguration fortfahren. Um eine Synchronisierung zu erzwingen, führen Sie den folgenden Befehl auf dem Computer aus, auf dem AAD Connect ausgeführt wird (wenn Sie nicht bereits fertig sind, müssen Sie `import-module adsync` zum Ausführen des Befehls laden):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .

3. Erstellen Sie die automatische Telefonzentrale oder die Anrufwarteschlange. Sehen Sie sich eines der folgenden Themen an:
   - [Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Erstellen einer Cloudanrufwarteschleife](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Ordnen Sie das Ressourcenkonto und die automatische Telefonzentrale oder Anrufwarteschlange, die Sie zuvor ausgewählt haben, zu.

Ein Beispiel für eine Small Business-Implementierung ist im  [Small Business-Beispiel verfügbar: Einrichten einer automatischen Telefonzentrale](/microsoftteams/tutorial-org-aa) und eines [Beispiels für kleine Unternehmen – Einrichten einer Anrufwarteschlange](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq).

## <a name="test-the-implementation"></a>Testen der Implementierung

Die beste Möglichkeit zum Testen der Implementierung besteht darin, die für eine automatische Telefonzentrale oder Anrufwarteschlange konfigurierte Nummer aufzurufen und eine Verbindung mit einem der Agents oder Menüs herzustellen. Sie können auch schnell einen Test Anruf tätigen, indem Sie die **Schaltfläche Test** im Aktionsbereich Admin Center verwenden. Wenn Sie Änderungen an einer automatischen Telefonzentrale oder einer Anrufwarteschlange vornehmen möchten, wählen Sie Sie aus, und klicken Sie dann im Aktionsbereich auf **Bearbeiten**. 

> [!TIP]
> Wenn Ihr Ressourcenkonto Schwierigkeiten mit dem Zuweisen einer Anrufwarteschlange oder einer automatischen Telefonzentrale hat, lesen Sie [bekannte Probleme für Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) und den Abschnitt [How to Fix My Hybrid Application Instances](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) im Microsoft Teams-Blog.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Verschieben einer Exchange um automatischen Telefonzentrale oder Anrufwarteschlange in das Telefon System

Bei der Migration von Exchange um zu Telefon System müssen die Struktur der Anrufwarteschlange und der automatischen Telefonzentrale neu erstellt werden, und die direkte Migration von der einen zur anderen wird nicht unterstützt. So implementieren Sie eine Reihe von Anrufwarteschlangen und automatischen Telefonzentralen erneut:

1. Rufen Sie eine Liste aller Exchange um automatischen Telefonzentralen und Anrufwarteschlangen ab, indem Sie den folgenden Befehl auf dem Exchange 2013-oder 2016-System ausführen, während Sie als Administrator angemeldet sind:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Notieren Sie für jede aufgeführte Exchange um Anrufwarteschlange oder automatische Telefonzentrale ihre Position in der Struktur, den Einstellungen und Abrufen von Kopien zugeordneter Sound-oder Text-zu-Sprache-Dateien (die GUID in der Ausgabe ist der Name eines Ordners, in dem die Dateien gespeichert sind). Sie können diese Details abrufen, indem Sie den folgenden Befehl ausführen:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) . Eine vollständige Liste der Optionen, die Sie möglicherweise erfassen müssen, finden Sie unter [UMAutoAttendant-Mitglieder](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) , aber die wichtigsten Optionen, die Sie beachten sollten, sind:

    - Geschäftszeiten
    - Außerhalb der Geschäftszeiten
    - Sprache
    - Feiertagszeitplan

3. Erstellen Sie wie oben beschrieben neue lokale Endpunkte.
   Zuweisen der automatischen Telefonzentrale der obersten Ebene zu Testzwecken zu einer temporären Nummer

4. Konfigurieren Sie eine automatische Telefonzentrale oder Anrufwarteschlange, die die Endpunkte verwendet, wie zuvor beschrieben.

   Möglicherweise ist es hilfreich, die Übungen im Tutorial mit dem Titel [Small Business Beispiel-Einrichten einer automatischen Telefonzentrale](/microsoftteams/tutorial-org-aa) zum Erstellen einer logischen Zuordnung der Hierarchien in Ihrem alten Exchange um System zu verwenden.
5. Testen Sie die automatische Telefonzentrale oder die Anrufwarteschlange.
6. Weisen Sie die Telefonnummer, die mit der Exchange um Anrufwarteschlange oder der automatischen Telefonzentrale verknüpft ist, der entsprechenden automatischen Telefonzentrale oder Anrufwarteschlange des Telefonsystems neu zu.  

   Wenn Sie zu diesem Zeitpunkt bereits um-Voicemail migriert haben, sollten Sie in der Lage sein, zu Exchange Server 2019 zu migrieren.

## <a name="see-also"></a>Siehe auch

[Erstellen einer Cloudanrufwarteschleife](/MicrosoftTeams/create-a-phone-system-call-queue)

[Was sind automatische Cloudtelefonzentralen?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Planen automatischer Cloudtelefonzentralen](plan-cloud-auto-attendant.md)

[Planen von Cloud-Anrufwarteschlangen](plan-call-queue.md)

[Planen des Cloud-Voicemail-Diensts für lokale Benutzer](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Verwalten von Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)  -  \( So erstellen Sie online verwaltete Ressourcenkonten\)
