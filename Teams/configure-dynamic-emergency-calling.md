---
title: Konfigurieren dynamischer Notrufe
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: roykuntz
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie die Dynamische Notruffunktion "Microsoft-Anrufpläne und Direct Routing für Telefonsysteme" konfigurieren.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc7fb0ae87cda84dfbf7b164d38b709b7ef2eef9
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2022
ms.locfileid: "67023696"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Planen und Konfigurieren dynamischer Notrufe 

Dynamische Notrufe für Microsoft-Anrufpläne, Telefonieanbieter und Direct Routing bieten die Möglichkeit, Notrufe zu konfigurieren und weiterzuleiten und Sicherheitspersonal basierend auf dem aktuellen Standort des Teams-Clients zu benachrichtigen.  

Basierend auf der Vom Mandantenadministrator definierten Netzwerktopologie (Netzwerkelemente, die Notfalladressen zugeordnet sind) stellt der Teams-Client Informationen zur Netzwerkkonnektivität in einer Anforderung an den Standortinformationsdienst (LIS) bereit. Wenn eine Übereinstimmung vorliegt, gibt lis einen Speicherort an den Client zurück.

Der Teams-Client enthält Standortdaten als Teil eines Notrufs. Diese Daten werden dann vom Notdienstanbieter verwendet, um den entsprechenden Public Safety Answering Point (PSAP) zu ermitteln und den Anruf an diesen PSAP weiterzuleiten, wodurch der PSAP-Verteiler den Standort des Anrufers abrufen kann.  

Bei dynamischen Notrufen muss Folgendes auftreten:

1. Der Netzwerkadministrator konfiguriert Netzwerkeinstellungen und die LIS, um eine Netzwerk-/Notfall-Standortzuordnung zu erstellen.

2. Während des Starts und in regelmäßigen Abständen danach oder wenn eine Netzwerkverbindung geändert wird, sendet der Teams-Client eine Standortanforderung, die die Netzwerkverbindungsinformationen enthält, an die Netzwerkeinstellungen und den LIS.

   - Wenn eine Übereinstimmung mit dem Standort für Netzwerkeinstellungen vorliegt, werden Richtlinien für Notrufe von diesem Standort an den Teams-Client zurückgegeben. (Weitere Informationen zu Richtlinien finden [Sie unter Konfigurieren von Notfallrichtlinien](#configure-emergency-policies)).

   - Wenn eine LIS-Übereinstimmung vorliegt– ein Notfallstandort aus dem Netzwerkelement, mit dem der Teams-Client verbunden ist, wird an den Teams-Client zurückgegeben. Die Übereinstimmung wird in der folgenden Reihenfolge ausgeführt, wobei das erste übereinstimmende Ergebnis zurückgegeben wird:
       - WAP
       - Ethernet-Switch/-Port
       - Ethernet-Switch
       - Subnetz

3. Wenn der Teams-Client einen Notruf abnimmt, wird der Notfallstandort an das PSTN-Netzwerk weitergeleitet.

Die Möglichkeit, automatisches Routing an den entsprechenden Public Safety Answering Point (PSAP) durchzuführen, hängt vom Nutzungsland des Teams-Benutzers ab.

Microsoft-Anrufpläne und Operator Connect-Partner umfassen dynamische Notfallroutingdienste für Benutzer in den USA und Kanada.

Für Direct Routing ist jedoch eine zusätzliche Konfiguration für das Routing von Notrufen und möglicherweise für die Partnerkonnektivität erforderlich. Der Administrator muss sicherstellen, dass das PSTN-Gateway, das den Notruf routingt, so konfiguriert wurde, dass standortinformationen zur ausgehenden EINLADUNG hinzugefügt werden (indem der Parameter "PidfloSupported" für das PSTN-Onlinegatewayobjekt auf "True" festgelegt wird. Darüber hinaus muss der Administrator die Verbindung mit einem ERS-Anbieter (Emergency Routing Service) (USA und Kanada) konfigurieren **oder** den Session Border Controller (SBC) für eine ELIN-Anwendung (Emergency Location Identification Number) konfigurieren. Informationen zu ERS-Anbietern finden Sie unter [Session Border Controller, die für Direct Routing zertifiziert sind](direct-routing-border-controllers.md).

Dieser Artikel enthält die folgenden Abschnitte.

- [Zuweisen von Notfalladressen](#assign-emergency-addresses)
- [Konfigurieren von Netzwerkeinstellungen](#configure-network-settings)
- [Konfigurieren des Standortinformationsdiensts](#configure-location-information-service)
- [Konfigurieren von Notfallrichtlinien](#configure-emergency-policies)
- [Aktivieren von Benutzern und Websites](#enable-users-and-sites)
- [Testen von Notrufen](#test-emergency-calling)

Weitere Informationen zu Notrufen, einschließlich Informationen zu Notfalladressen und Notrufweiterleitung, länderspezifischen Informationen sowie Informationen zu Netzwerkeinstellungen und Netzwerktopologie finden Sie in den folgenden Themen:

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Verwalten von Netzwerkeinstellungen für Cloud Voice-Features](cloud-voice-network-settings.md)
- [Verwalten Ihrer Netzwerktopologie für Cloud Voice-Features](manage-your-network-topology.md)

Weitere Informationen dazu, welche Features in den Government Clouds verfügbar sind, finden Sie im [Government-Support](#government-support) am Ende dieses Artikels.


## <a name="supported-clients"></a>Unterstützte Clients

Die folgenden Clients werden derzeit unterstützt.  Überprüfen Sie häufig, um Updates für diese Liste anzuzeigen.

- Teams-Desktopclient für Microsoft Windows
- Teams-Desktopclient für Apple macOS
- Mobiler Microsoft Teams-Client für Apple iOS-Client, Version 1.0.92.2019121004 und App Store Version 1.0.92 und höher
- Mobiler Microsoft Teams-Client für Android-Client und Google Play Store Version 1416/1.0.0.2019121201 und höher
- Teams-Telefonversion 1449/1.0.94.2019110802 und höher
- Teams-Räume Version 4.4.25.0 und höher

> [!NOTE]
> Subnetz- und WLAN-basierte Standorte werden auf allen unterstützten Teams-Clients unterstützt. <br><br>
> Ethernet/Switch (LLDP) wird unterstützt für:
> - Windows-Versionen 10.0 und höher zu diesem Zeitpunkt.<br>
> - Mac OS, für das [LLDP-Aktivierungssoftware erforderlich ist](https://www.microsoft.com/download/details.aspx?id=103383).<br>
> - Teams phone with Teams app version 1449/1.0.94.2021110101 and later.

> [!NOTE]
> Dynamische Notrufe, einschließlich Benachrichtigungen am Security Desk, werden auf dem Teams-Webclient nicht unterstützt. Um zu verhindern, dass Benutzer den Teams-Webclient zum Aufrufen von PSTN-Nummern verwenden, können Sie eine Teams-Anrufrichtlinie festlegen und die Einstellung " **Web-PSTN-Anrufe zulassen** " deaktivieren. Weitere Informationen finden Sie [unter Anrufrichtlinien in Teams](teams-calling-policy.md) und [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). 

> [!NOTE]
> 3PIP-Telefone unterstützen keine dynamischen Notrufe. 



## <a name="assign-emergency-addresses"></a>Zuweisen von Notfalladressen

Sie können Notfalladressen wie folgt zuweisen:

- An Anrufplanbenutzer.

- To Operator Connect users&mdash;depending on the capabilities assigned to the number when the carrier uploads them into a customer's inventory.

- Zu den Netzwerkbezeichnern, die zum dynamischen Abrufen eines Standorts erforderlich sind. 

Um das automatisierte Routing von Notrufen innerhalb der USA zu unterstützen, müssen Sie sicherstellen, dass die Notfallstandorte, die Netzwerk-IDs zugewiesen sind, die zugehörigen Geocodes enthalten. (Notfalladressen ohne Geocodes können den Netzwerkbezeichnern, die für dynamische Standorte erforderlich sind, nicht zugewiesen werden.)

Azure Maps wird für standortbasierte Dienste verwendet. Wenn Sie eine Notfalladresse über das Microsoft Teams Admin Center eingeben, überprüft Teams Azure Maps auf die Adresse:

- Wenn eine Übereinstimmung gefunden wird, werden die Geocodes automatisch eingeschlossen.

- Wenn keine Übereinstimmung gefunden wird, haben Sie die Möglichkeit, manuell eine Notfalladresse zu erstellen. Dazu können Sie die PIN-Ablagefunktion verwenden. 

> [!NOTE]
> Notfalladressen, die älter als ein paar Jahre sind, können netzwerkidentifikatoren nicht zugewiesen werden. Sie müssen ältere Adressen neu erstellen.

Sie fügen Notfalladressen im Microsoft Teams Admin Center oder mithilfe von PowerShell hinzu und weisen sie zu. Weitere Informationen finden Sie unter [Hinzufügen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md) und [Zuweisen eines Notfallstandorts für einen Benutzer](assign-change-emergency-location-user.md).

## <a name="configure-network-settings"></a>Konfigurieren von Netzwerkeinstellungen

Netzwerkeinstellungen werden verwendet, um den Standort eines Teams-Clients zu ermitteln und dynamisch Notrufrichtlinien und einen Notfallstandort abzurufen. Sie können Netzwerkeinstellungen entsprechend der Funktionsweise von Notrufen in Ihrer Organisation konfigurieren.

Netzwerkeinstellungen umfassen Standorte, die eine Sammlung von Subnetzen enthalten, und diese werden ausschließlich für die dynamische Richtlinienzuweisung an Benutzer verwendet. Beispielsweise können eine Notrufrichtlinie und eine Richtlinie für die Notrufweiterleitung dem Standort "Redmond" zugewiesen werden, sodass jeder Benutzer, der von zu Hause oder von einem anderen Microsoft-Standort aus roamingt, mit Notrufnummern, Routing und Sicherheitsdesk speziell für Redmond konfiguriert wird.  

Vertrauenswürdige IP-Adressen enthalten eine Sammlung der externen INTERNET-IP-Adressen des Unternehmensnetzwerks und werden verwendet, um festzustellen, ob sich der Endpunkt des Benutzers innerhalb des Unternehmensnetzwerks befindet. Es wird nur versucht, eine dynamische Richtlinie oder einen dynamischen Speicherort abzurufen, wenn die externe IP-Adresse des Benutzers mit einer IP-Adresse in der vertrauenswürdigen IP-Adresse übereinstimmt.

Weitere Informationen zu IP-Adressen, Netzwerkregionen, Standorten und Subnetzadressen finden Sie unter [Netzwerkeinstellungen für Cloud-VoIP-Funktionen](cloud-voice-network-settings.md).

Sie konfigurieren Netzwerkeinstellungen im Microsoft Teams Admin Center oder mithilfe von PowerShell. Weitere Informationen finden [Sie unter Verwalten Ihrer Netzwerktopologie für Cloud-VoIP-Features](manage-your-network-topology.md).

Beachten Sie, dass es einige Zeit (bis zu ein paar Stunden) dauern kann, bis einige Änderungen an den Netzwerkeinstellungen (z. B. eine neue Adresse, Netzwerk-ID usw.) weitergegeben wurden und für Teams-Clients verfügbar sind.  

> [!Note]
> Subnetze können auch in LIS definiert und einem Notfallstandort zugeordnet werden.  LIS-Subnetze müssen durch die Netzwerk-ID definiert werden, die dem Subnetz-IP-Bereich entspricht, der Clients zugewiesen ist. Die Netzwerk-ID für eine Client-IP/-Maske von 10.10.10.150/25 lautet beispielsweise 10.10.10.128. Weitere Informationen finden Sie unter [Grundlegendes zu TCP/IP-Adressierung und Subnetzierung](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting).

> [!Important]
> Netzwerkkonfigurationseinstellungssuchen werden bei Bereitstellungen von Cloudproxydiensten, die die Quell-IP-Adressen von Teams-Clients ändern, nicht unterstützt.



**Für Anrufplan- und Telefonieanbieterbenutzer:**

- Wenn eine dynamische Konfiguration der Security Desk-Benachrichtigung erforderlich ist, müssen Sie sowohl vertrauenswürdige IP-Adressen als auch Netzwerkstandorte konfigurieren.

- Wenn nur dynamische Speicherorte erforderlich sind, müssen Sie nur vertrauenswürdige IP-Adressen konfigurieren. Das Konfigurieren von Netzwerkeinstellungen ist nicht erforderlich.

- Wenn keines der Beiden erforderlich ist, ist das Konfigurieren von Netzwerkeinstellungen nicht erforderlich. 

**Für Direct Routing-Benutzer:**

- Wenn die dynamische Aktivierung von Notrufen oder die dynamische Konfiguration von Security Desk-Benachrichtigungen erforderlich ist, müssen Sie sowohl vertrauenswürdige IP-Adressen als auch Netzwerkstandorte konfigurieren.

- Wenn nur dynamische Speicherorte erforderlich sind, müssen Sie nur vertrauenswürdige IP-Adressen konfigurieren. Das Konfigurieren von Netzwerkeinstellungen ist nicht erforderlich.

- Wenn keines der Beiden erforderlich ist, ist das Konfigurieren von Netzwerkeinstellungen nicht erforderlich.


## <a name="configure-location-information-service"></a>Konfigurieren des Standortinformationsdiensts

Ein Teams-Client ruft Notfalladressen von den Standorten ab, die verschiedenen Netzwerk-IDs zugeordnet sind. 

Damit ein Client einen Standort abrufen kann, müssen Sie den LIS mit Netzwerk-IDs (Subnetze, WAPs, Switches, Ports) und Notfallstandorten auffüllen. Sie können dies im Microsoft Teams Admin Center oder mithilfe von PowerShell tun.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Navigieren Sie im linken Navigationsbereich zu **Speicherortnetzwerken** > **& Speicherorten**.
2. Klicken Sie auf die Registerkarte, die den Netzwerkbezeichner darstellt, den Sie hinzufügen möchten. Klicken Sie beispielsweise auf **Subnetze**, **WLAN-Zugriffspunkte**, **Switches** oder **Ports**. Klicken Sie dann auf **"Hinzufügen"**.
3. Füllen Sie die Felder aus, fügen Sie einen Notfallstandort hinzu, und klicken Sie dann auf **Übernehmen**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie die folgenden Cmdlets, um Dem LIS Ports, Switches, Subnetze und WAPs hinzuzufügen.

- [Abrufen](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Festlegen](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Entfernen](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Abrufen](/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Festlegen](/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Entfernen](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Abrufen](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Festlegen](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Entfernen](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Abrufen](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Festlegen](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Entfernen](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>Wenn Subnetze als Teil von Netzwerkstandorten verwendet werden, müssen sie im Standortinformationsdienst neu definiert werden, um dynamische Standorte zu rendern.

## <a name="configure-emergency-policies"></a>Konfigurieren von Notfallrichtlinien

Verwenden Sie die folgenden Richtlinien, um Notrufe zu konfigurieren. Sie können diese Richtlinien im Microsoft Teams Admin Center oder mithilfe von PowerShell verwalten.

- **Richtlinie für die Notrufweiterleitung – Gilt nur für Direct Routing**. Diese Richtlinie konfiguriert die Notrufnummern, ggf. Masken pro Nummer und die PSTN-Route pro Nummer. Sie können diese Richtlinie Benutzern, Netzwerkstandorten oder beiden zuweisen. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für die Notrufweiterleitung für Direct Routing](manage-emergency-call-routing-policies.md).  

   (Anrufplan- und Telefonieanbieter-Benutzer werden automatisch für Notrufe mit den Notrufnummern aus dem Land basierend auf ihrem Microsoft 365- oder Office 365-Verwendungsstandort aktiviert.)

- **Richtlinie für Notrufe – Gilt für Anrufpläne, Telefonieanbieter und Direct Routing.** Diese Richtlinie konfiguriert die Benachrichtigungsfunktion des Sicherheitsdesks, wenn ein Notruf getätigt wird. Sie können festlegen, wer benachrichtigt werden soll und wie sie benachrichtigt werden. Beispielsweise, um den Security Desk Ihrer Organisation automatisch zu benachrichtigen und sie bei Notrufen abhören zu lassen.  Diese Richtlinie kann entweder Benutzern oder Netzwerkstandorten oder beiden zugewiesen werden. Weitere Informationen finden [Sie unter Verwalten von Notrufrichtlinien in Teams](manage-emergency-calling-policies.md).

## <a name="enable-users-and-sites"></a>Aktivieren von Benutzern und Websites

Sie können Benutzern und Standorten Richtlinien für das Weiterleiten von Notrufen und Notrufe zuweisen. Denken Sie daran, dass Richtlinien für die Notrufweiterleitung nur für Direct Routing gelten. (Obwohl es möglich ist, diese Richtlinie einem Anrufplan- oder Operator Connect-Benutzer zuzuweisen, hat die Richtlinie keine Auswirkung.)

Sie weisen Richtlinien im Microsoft Teams Admin Center oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter:

- [Verwalten von Notruf-Routing-Richtlinien für Direct Routing](manage-emergency-call-routing-policies.md)
- [Verwalten von Notrufrichtlinien in Teams](manage-emergency-calling-policies.md)

Nachfolgend sind PowerShell-Beispiele aufgeführt:

Verwenden Sie den folgenden Befehl, um einen bestimmten Benutzer für Benachrichtigungen am Security Desk zu aktivieren:

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Verwenden Sie den folgenden Befehl, um Standort 1 eine Richtlinie namens "Contoso Emergency Calling Policy 1" zuzuweisen:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Verwenden Sie den folgenden Befehl, um einen bestimmten Direct Routing-Benutzer für Notrufe zu aktivieren:

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Verwenden Sie den folgenden Befehl, um Standort 1 eine Richtlinie namens "Contoso New York Emergency Call Routing" zuzuweisen:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Wenn Sie eine Richtlinie für Notrufe einem Netzwerkstandort und einem Benutzer zugewiesen haben und sich dieser Benutzer an diesem Netzwerkstandort befindet, überschreibt die Richtlinie, die dem Netzwerkstandort zugewiesen ist, die Richtlinie, die dem Benutzer zugewiesen ist.

## <a name="test-emergency-calling"></a>Testen von Notrufen

Einige Notfallroutingdienstanbieter (EMERGENCY Routing Service Providers, ERSPs) in der USA bieten einen Test-Bot für Notrufe an.

- **Anrufplan- und Operator Connect-Benutzer in der USA oder Kanada** können die vordefinierte Testnotrufnummer 933 verwenden, um ihre Notrufkonfiguration zu überprüfen. Diese Nummer wird an einen Bot weitergeleitet, der dann die Rufnummer des Anrufers (Anrufleitungs-ID), die Notfalladresse oder den Standort zurückgibt und ob der Anruf automatisch an den Anrufer weitergeleitet oder zuerst überprüft wird.

- **Direct Routing-Kunden im USA** sollten sich mit ihrem ERSP für einen Testdienst koordinieren.

## <a name="government-support"></a>Staatliche Unterstützung

Die folgende Tabelle zeigt die Unterstützung für dynamische Notrufe in den Government Clouds:

| Cloud | Verfügbarkeit |
| :------------|:-------|
| World Wide Multi Tenant | Verfügbar für alle Teams-Clients |
| GCC | Verfügbar für alle Teams-Clients |
| GCCH | -Verfügbar auf Teams-Desktop <br> –Verfügbar auf mobilen Teams-Clients <br> -Verfügbar auf Teams-Smartphones, App-Version: 1449/1.0.94.2022061702 |
| Dod | Ausstehend |

 ## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Verwalten von Notruf-Richtlinien](manage-emergency-calling-policies.md)
- [Verwalten von Richtlinien für die Notrufweiterleitung ](manage-emergency-call-routing-policies.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Zuweisen oder Ändern eines Notfallstandorts für Den Benutzer](assign-change-emergency-location-user.md)
- [Netzwerkeinstellungen für Cloud Voice-Features](cloud-voice-network-settings.md)
- [Verwalten Ihrer Netzwerktopologie für Cloud Voice-Features](manage-your-network-topology.md)
