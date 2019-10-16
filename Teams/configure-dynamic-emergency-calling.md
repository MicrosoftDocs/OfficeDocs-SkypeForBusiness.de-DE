---
title: Konfigurieren von dynamischen Notrufen
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: Konfigurieren von dynamischen Notrufen
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b166c93bb213fab6e8025a1837ef67baa65c884
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516932"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a>Planen und Konfigurieren von dynamischen Notrufen für Anrufpläne
Dynamische Notrufe für Microsoft-Anrufpläne bieten die Möglichkeit, Notrufe auf der Grundlage des aktuellen Standorts des Teams-Clients zu konfigurieren und zu leiten.  Die Möglichkeit zur automatischen Weiterleitung an den entsprechenden öffentlichen Sicherheits-Anrufbeantworter (PSAP) oder zur Benachrichtigung über das Personal von Sicherheitsmitarbeitern variiert je nach dem Land, in dem der Benutzer des Teams verwendet wird.  

> [!Note] 
> Dynamische Notrufe stehen derzeit nur in den Vereinigten Staaten zur Verfügung. Security Desk-Benachrichtigungen werden jedoch über Ländergrenzen hinweg unterstützt.

**In den Vereinigten Staaten**können Sie das dynamische Notfall Anrufrouting wie folgt konfigurieren:
  
- Wenn sich ein Team-Client an einem vom Mandanten definierten dynamischen Notfall Standort befindet, werden Notrufe von diesem Client automatisch an die PSAP weitergeleitet, die diesem geografischen Standort dienen.  

- Wenn sich ein Teams-Client nicht an einem vom Mandanten definierten dynamischen Notfall Standort befindet, werden Notrufe von diesem Client von einem nationalen Callcenter durchlaufen, um den Standort des Anrufers zu ermitteln, bevor der Anruf an die PSAP, die diesen geografischen Standort bedient, übertragen wird.

Sie können die Benachrichtigung über das Sicherheits Desk wie folgt konfigurieren:

- Wenn sich ein Team-Client auf einer vom Mandanten definierten Netzwerk Website befindet, werden die für diese Website konfigurierten Mitglieder der Sicherheitsgruppe benachrichtigt.

- Wenn sich ein Team-Client nicht auf einer vom Mandanten definierten Netzwerk Website befindet, werden die für den Benutzer konfigurierten Sicherheitsgruppen Mitglieder benachrichtigt.

**Außerhalb der Vereinigten Staaten**werden Notrufe an die PSAP weitergeleitet, die der dem Benutzer zugewiesenen Telefonnummer zugeordnet ist.  Einige Länder, wie Großbritannien und Kanada, übertragen die Anrufe auf nationaler Ebene, bevor Sie den Anrufer an die entsprechende PSAP, während andere Personen direkt an das PSAP weiterleiten, unabhängig davon, wo sich der Benutzer gerade befindet. 

Beachten Sie, dass Sie die Dynamic Security Desk-Benachrichtigung für alle Benutzer des Anruf Plans konfigurieren können.


## <a name="supported-clients"></a>Unterstützte Clients

Die folgenden Clients werden zurzeit unterstützt.  Schauen Sie sich häufig an, um Updates für diese Liste anzuzeigen.

- Teams-Desktop Client für Windows
- Teams-Desktop Client für Mac

## <a name="configure-dynamic-emergency-calling"></a>Konfigurieren von dynamischen Notrufen

Um dynamische Notrufe konfigurieren zu können, müssen Sie die folgenden Aufgaben ausführen:

- [Konfigurieren von Notfalladressen](#configure-emergency-addresses)
- [Konfigurieren von Netzwerkeinstellungen](#configure-network-settings)
- [Konfigurieren des Standort Informationsdiensts](#configure-location-information-service)
- [Konfigurieren von Notfall Richtlinien](#configure-emergency-policies)
- [Aktivieren von Benutzern und Websites](#enable-users-and-sites)
- [Testen von Notrufen](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a>Konfigurieren von Notfalladressen

Zur Unterstützung des automatisierten Routings innerhalb der USA müssen Sie die bürgerliche Adresse, die Teil der Notfall Speicherorte ist, die Netzwerkkennungen zugeordnet sind, vollständig konfigurieren und die zugehörigen Geo-Codes einbeziehen. (Notfalladressen ohne Geo-Codes können nicht den Netzwerk Bezeichnern zugewiesen werden, die für dynamische Speicherorte erforderlich sind.)

- Wenn Sie eine Notfalladresse über das Microsoft Teams Admin Center eingeben, werden die Geo-Codes automatisch einbezogen, wenn eine Übereinstimmung gefunden wird.

- Wenn eine Übereinstimmung nicht automatisch gefunden wird, haben Sie die Möglichkeit, eine Notfalladresse manuell zu erstellen.  

Das bedeutet: Wenn eine vorhandene Notfalladresse für Notrufe konfiguriert ist, muss dieselbe Adresse neu erstellt werden, um die Geo-Codes einzubeziehen.  Wenn Sie zwischen den beiden Adressen unterscheiden möchten, sollten Sie eine andere Beschreibung angeben. Die neue Notfalladresse kann den Benutzern zugewiesen werden, die die alte Adresse besitzen. Nach der vollständigen Migration kann die alte Adresse gelöscht werden. 

Weitere Informationen zum Konfigurieren von Notfalladressen finden Sie unter [Was sind Notfall Standorte, Orte und Anrufweiterleitung?](what-are-emergency-locations-addresses-and-call-routing.md).

### <a name="configure-network-settings"></a>Konfigurieren von Netzwerkeinstellungen

Sie müssen die Netzwerkeinstellungen so konfigurieren, dass dynamisch ein Notfall Standort für das Routing von Notrufen abgerufen und optional eine dynamische Konfiguration von Benachrichtigungen über Sicherheits Desk bereitgestellt wird. Die gewünschte Notruffunktion bestimmt, welche Netzwerkeinstellungen konfiguriert werden müssen. 

Beachten Sie die folgenden Definitionen:

- Vertrauenswürdige IP-Adressen enthalten eine Sammlung der externen Internet-IPS des Unternehmensnetzwerks und werden verwendet, um festzustellen, ob sich der Endpunkt des Benutzers innerhalb des Unternehmensnetzwerks befindet. Dynamische Speicherorte werden nur aktiviert, wenn die externe IP-Adresse des Benutzers einer IP-Adresse in der vertrauenswürdigen IP-Sammlung entspricht.  Eine Übereinstimmung kann entweder für IPv4-oder IPv6-IP-Adressen erfolgen und hängt vom Format des IP-Pakets ab, das an die Netzwerkeinstellungen gesendet wird.

- Eine Netzwerkregion enthält verschiedene Netzwerkstandorte. 

- Eine Netzwerk Website steht für einen Standort, an dem Ihre Organisation über einen physikalischen Wert verfügt, beispielsweise ein Büro, einen Satz von Gebäuden oder einen Campus. Diese Websites sind als eine Sammlung von IP-Subnetzen definiert.

- Ein Netzwerk-Subnetz muss einer bestimmten Netzwerk Website zugeordnet sein. Der Standort eines Clients wird basierend auf dem Netzwerk-Subnetz und der zugehörigen Netzwerk Website bestimmt.  


Für Benutzer von Plan anrufen:

- Wenn die dynamische Konfiguration von Security Desk-Benachrichtigungen erforderlich ist, müssen Sie sowohl vertrauenswürdige IP-Adressen als auch Netzwerk Websites konfigurieren.

- Wenn nur dynamische Speicherorte erforderlich sind, müssen Sie nur vertrauenswürdige IP-Adressen konfigurieren. 

- Wenn keines von beiden erforderlich ist, ist die Konfiguration von Netzwerkeinstellungen nicht erforderlich. 

Weitere Informationen finden Sie unter [Konfigurieren von Netzwerkeinstellungen für standortbasiertes Routing](location-based-routing-configure-network-settings.md), das beschreibt, wie Netzwerkeinstellungen konfiguriert werden. (Die Informationen in diesem Artikel beziehen sich auf Anrufpläne und direktes Routing.)


### <a name="configure-location-information-service"></a>Konfigurieren des Standort Informationsdiensts

Ein Team-Client ruft Notfalladressen von den Notfall Standorten ab, die mit verschiedenen Netzwerkkennungen verbunden sind.  Subnetze und drahtlose Zugriffspunkte werden beide unterstützt. (Unterstützung für Ethernet-Switch/-Port ist ausstehend.)

Verwenden Sie die folgenden Cmdlets, um den standortinformationsdienst (LIS) mit Netzwerkkennungen und Notfall Speicherorten zu konfigurieren:

- Abrufen, einrichten, entfernen-CsOnlineLisPort
- Abrufen, einrichten, entfernen-CsOnlineLisSwitch
- Abrufen, einrichten, entfernen-CsOnlineLisSubnet
- Abrufen, einrichten, entfernen-CsOnlineLisWirelessAccessPoint 

> [!Important] 
> Wenn Subnetze als Teil von Netzwerk Websites verwendet werden, müssen Sie im standortinformationsdienst neu definiert werden, um dynamische Speicherorte zu rendern.


### <a name="configure-emergency-policies"></a>Konfigurieren von Notfall Richtlinien

Notfall Richtlinien legen fest, was geschieht, wenn ein Benutzer in Ihrer Organisation einen Notfall Anruf tätigt.  Sie können feststellen, wer benachrichtigt werden soll und wie Sie benachrichtigt werden, wenn ein Benutzer Notrufdienste anruft. So können Sie beispielsweise Richtlinieneinstellungen so konfigurieren, dass Sie den Security Desk Ihrer Organisation automatisch benachrichtigen und bei Notrufen anhören.

Sie verwalten Notfall Richtlinien mithilfe der Cmdlets für neu-, Satz-und Grant-CsTeamsEmergencyCalling-Richtlinien.  Weitere Informationen finden Sie unter [Verwalten von Notruf Richtlinien in Teams](manage-emergency-calling-policies.md).


### <a name="enable-users-and-sites"></a>Aktivieren von Benutzern und Websites

Während die Benutzer des Anruf Plans automatisch für Notrufe aktiviert sind, müssen Sie die Benutzer für die Benachrichtigung über das Security Desk aktivieren, indem Sie die Notruf Richtlinie konfigurieren, wie im folgenden Beispiel gezeigt:


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Sie können die Notruf Richtlinie auch einer Netzwerk Website zuweisen, wie im folgenden Beispiel gezeigt, das eine Richtlinie namens "Contoso Emergency Calling Policy 1" zu Site 1 zuweist:

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Wenn Sie einer Netzwerk Website und einem Benutzer eine Notruf Richtlinie zugewiesen haben und sich dieser Benutzer an dieser Netzwerk Website befindet, überschreibt die der Netzwerk Website zugewiesene Richtlinie die Richtlinie, die dem Benutzer zugewiesen ist.


### <a name="test-emergency-calling"></a>Testen von Notrufen

Um Notrufe in den Vereinigten Staaten zu testen, verwenden Sie die vordefinierte Test Notfallnummer 933.  Diese Nummer wird an einen bot weitergeleitet, der dann wieder die Rufnummer des Anrufers (Rufnummernanzeige), die Notfalladresse oder den Standort zurückgibt und feststellt, ob der Anruf automatisch an die PSAP weitergeleitet oder zuerst übertragen wird.  