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
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie die Microsoft-Anrufpläne und die dynamische Notruffunktion für das direkte Routing des Telefonsystems konfigurieren.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06153eccd343ef8731af38ff4e3b45cea334fcb2
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031011"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Planen und Konfigurieren dynamischer Notrufe 

Dynamische Notrufe für Microsoft-Anrufpläne und Telefon System Direktes Routing bietet die Möglichkeit, Notrufe zu konfigurieren und zu leiten sowie Sicherheitspersonal entsprechend dem aktuellen Standort des Teams-Clients zu benachrichtigen.  

Basierend auf der Netzwerktopologie, die der mandantenadministrator definiert, bietet der Team-Clientnetzwerk Verbindungsinformationen in einer Anforderung an den Location Information Service (LIS). Wenn eine Übereinstimmung vorhanden ist, gibt der LIS eine Position an den Client zurück. Diese Standortdaten werden an den Client zurückgesendet.  

Der Team-Client umfasst Standortdaten im Rahmen eines Notrufs. Diese Daten werden dann vom Notrufdienst Anbieter verwendet, um den entsprechenden öffentlichen Sicherheits Beantwortungs Punkt (PSAP) zu ermitteln und den Anruf an diesen PSAP weiterzuleiten, wodurch der PSAP-Verteiler den Standort des Anrufers abrufen kann.  

Für dynamische Notrufe müssen folgende Schritte ausgeführt werden:

1. Der Netzwerkadministrator konfiguriert Netzwerkeinstellungen und den LIS, um eine Netzwerk/Notfall-Standort Karte zu erstellen.

   Für das direkte Routing ist eine zusätzliche Konfiguration für das Routing von Notrufen und möglicherweise für die Partner Konnektivität erforderlich. Der Administrator muss die Verbindung zu einem Notfall-Routing Dienst (ERS)-Anbieter (USA) konfigurieren **oder** den Session Border Controller (SBC) für eine Emergency Location Identification Number (Elin)-Anwendung konfigurieren.

2. Während des Starts und in regelmäßigen Abständen, oder wenn eine Netzwerkverbindung geändert wird, sendet der Client für Teams eine Standortanfrage, die seine Netzwerk Verbindungsinformationen enthält, an die Netzwerkeinstellungen und den LIS.

   - Wenn es eine Website Übereinstimmung mit Netzwerkeinstellungen gibt, werden die Richtlinien für Notrufe von dieser Website an den Team-Client zurückgegeben. (Weitere Informationen zu Richtlinien finden Sie unter [Konfigurieren von Notfall Richtlinien](#configure-emergency-policies)).

   - Wenn es eine LIS-Übereinstimmung gibt – ein Notfall Standort aus dem Netzwerkelement, mit dem der Team-Client verbunden ist, wird an den Team-Client zurückgegeben. Die Übereinstimmung wird in der folgenden Reihenfolge durchgeführt, wobei das erste übereinstimmende Ergebnis zurückgegeben wird:
       - WAP
       - Ethernet-Switch/-Port
       - Ethernet-Switch
       - Subnetz

3. Wenn der Teams-Client einen Notruf tätigt, wird der Notfall Standort an das PSTN-Netzwerk weitergeleitet.

   Für die direkte Weiterleitung muss der Administrator den SBC so konfigurieren, dass er Notrufe an den ERS-Anbieter sendet oder die SBC Elin-Anwendung konfiguriert.

Dieser Artikel enthält die folgenden Abschnitte.

- [Konfigurieren von Notfalladressen](#assign-emergency-addresses)
- [Konfigurieren von Netzwerkeinstellungen](#configure-network-settings)
- [Konfigurieren des Standort Informationsdiensts](#configure-location-information-service)
- [Konfigurieren von Notfall Richtlinien](#configure-emergency-policies)
- [Aktivieren von Benutzern und Websites](#enable-users-and-sites)
- [Testen von Notrufen](#test-emergency-calling)

Die Möglichkeit zur automatischen Weiterleitung an den entsprechenden öffentlichen Sicherheits Beantwortungs Punkt (PSAP) variiert je nach dem Land, in dem der Benutzer des Teams verwendet wird.

Weitere Informationen zu Notrufen, einschließlich Informationen zu Notfalladressen und Routing für Notrufe, Informationen zu Ländern sowie Informationen zu Netzwerkeinstellungen und Netzwerktopologie finden Sie unter den folgenden Themen:

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Verwalten von Netzwerkeinstellungen für Cloud-Sprachfeatures](cloud-voice-network-settings.md)
- [Verwalten Ihrer Netzwerktopologie für Cloud Voice-Features](manage-your-network-topology.md)

## <a name="supported-clients"></a>Unterstützte Clients

Die folgenden Clients werden zurzeit unterstützt.  Schauen Sie sich häufig an, um Updates für diese Liste anzuzeigen.

- Teams-Desktop Client für Microsoft Windows
- Teams-Desktop Client für Apple macOS
- Teams Mobile Client für Apple IOS Client Version 1.0.92.2019121004 und App Store Version 1.0.92 und höher
- Teams Mobile Client für Android-Client und Google Play Store, Version 1416/1.0.0.2019121201 und höher
- Teams Phone Version 1449/1.0.94.2019110802 und höher
- Teams rooms Version 4.4.25.0 und höher

> [!NOTE]
> Dynamische Notrufe, einschließlich Benachrichtigungen über den Security Desk, werden im Team-WebClient nicht unterstützt. Um zu verhindern, dass Benutzer den Microsoft Teams-WebClient zum Anrufen von PSTN-Nummern verwenden, können Sie eine Anrufrichtlinie für Teams festlegen und die Einstellung **webpstn-Anruf zulassen** deaktivieren. Weitere Informationen finden Sie unter [Aufrufen von Richtlinien in Teams](teams-calling-policy.md) und [CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).

## <a name="assign-emergency-addresses"></a>Notfalladressen zuweisen

Sie können Notfalladressen sowohl für Benutzer des Anruf Plans als auch für die Netzwerkkennungen zuweisen, die für die dynamische Beschaffung eines Standorts erforderlich sind. (Subnetz und WLAN-AP werden unterstützt. Ethernet-Switch/-Port wird in Windows 8,1 und höher zurzeit unterstützt).

Zur Unterstützung der automatisierten Weiterleitung von Notrufen in den USA müssen Sie sicherstellen, dass die den Netzwerk Bezeichnern zugewiesenen Notfall Speicherorte die zugehörigen Geo-Codes enthalten. (Notfalladressen ohne Geo-Codes können nicht den Netzwerk Bezeichnern zugewiesen werden, die für dynamische Speicherorte erforderlich sind.)

Azure Maps wird für standortbasierte Dienste verwendet.  Wenn Sie eine Notfalladresse mithilfe des Microsoft Teams admin Centers eingeben, überprüft Teams Azure Maps auf die Adresse:

- Wenn eine Übereinstimmung gefunden wird, werden die Geo-Codes automatisch berücksichtigt.

- Wenn keine Übereinstimmung gefunden wird, haben Sie die Möglichkeit, eine Notfalladresse manuell zu erstellen. Sie können dazu das Feature "Pin-Ablage" verwenden. 

Wenn ein vorhandener Notfall Standort, der für die Zuweisung zu einem Anruf Plan Benutzer erstellt wurde, für einen dynamischen Standort vorgesehen ist, muss dieselbe Adresse neu erstellt werden, um die Geo-Codes einzubeziehen. Wenn Sie zwischen den beiden Speicherorten unterscheiden möchten, sollten Sie eine andere Beschreibung hinzufügen. Der neue Notfall Standort kann den Benutzern zugewiesen werden, die den alten Standort besitzen. Nach der vollständigen Migration kann der alte Speicherort gelöscht werden.

Sie können Notfalladressen im Microsoft Teams Admin Center oder mithilfe von PowerShell hinzufügen und zuweisen. Weitere Informationen finden Sie unter [Hinzufügen eines Notfall Standorts für Ihre Organisation](add-change-remove-emergency-location-organization.md) und [Zuweisen eines Notfall Standorts für einen Benutzer](assign-change-emergency-location-user.md).

## <a name="configure-network-settings"></a>Konfigurieren von Netzwerkeinstellungen

Netzwerkeinstellungen werden verwendet, um den Standort eines Teams-Clients zu ermitteln und dynamisch Notruf Richtlinien und einen Notfall Standort abzurufen. Sie können die Netzwerkeinstellungen so konfigurieren, wie Ihre Organisation Notrufe tätigen möchte.

Zu den Netzwerkeinstellungen gehören Websites, die eine Sammlung von Subnetzen enthalten, und diese werden ausschließlich zur dynamischen Richtlinienzuweisung für Benutzer verwendet. So kann beispielsweise eine Notruf Richtlinie und eine Notfall-Anruf Weiterleitungs Richtlinie dem "Redmond-Standort" zugewiesen werden, damit jeder Benutzer, der von zu Hause oder einem anderen Microsoft-Standort wandert, mit Notrufnummern, Routing und Security Desk für Redmond konfiguriert ist.  

>[!Note]
>Subnets können auch in Lis definiert werden und können einem Notfall Standort zugeordnet werden.  

Beachten Sie die folgenden Definitionen. Weitere Informationen finden Sie unter [Netzwerkeinstellungen für Cloud-Sprachfeatures](cloud-voice-network-settings.md).

- Vertrauenswürdige IP-Adressen enthalten eine Sammlung der Internet externen IP-Adressen des Unternehmensnetzwerks und werden verwendet, um festzustellen, ob sich der Endpunkt des Benutzers innerhalb des Unternehmensnetzwerks befindet. Der Versuch, eine dynamische Richtlinie oder einen Speicherort zu erhalten, wird nur ausgeführt, wenn die externe IP-Adresse des Benutzers mit einer IP-Adresse in der vertrauenswürdigen IP-Adresse übereinstimmt. Eine Übereinstimmung kann entweder für IPv4-oder IPv6-IP-Adressen erfolgen und hängt vom Format des IP-Pakets ab, das an die Netzwerkeinstellungen gesendet wird.  (Wenn eine öffentliche IP-Adresse sowohl IPv4 als auch IPv6 hat, müssen Sie beide als vertrauenswürdige IP-Adressen hinzufügen.)

- Eine Netzwerkregion enthält verschiedene Netzwerkstandorte. 

- Eine Netzwerk Website steht für einen Standort, an dem Ihre Organisation über einen physikalischen Wert verfügt, beispielsweise ein Büro, einen Satz von Gebäuden oder einen Campus. Diese Websites sind als eine Sammlung von IP-Subnetzen definiert.

- Ein Netzwerk-Subnetz muss einer bestimmten Netzwerk Website zugeordnet sein. Der Standort eines Clients wird basierend auf dem Netzwerk-Subnetz und der zugehörigen Netzwerk Website bestimmt.  

Sie können Netzwerkeinstellungen im Microsoft Teams Admin Center oder mithilfe von PowerShell konfigurieren. Weitere Informationen finden Sie unter [Verwalten Ihrer Netzwerktopologie für Cloud-Sprachfeatures](manage-your-network-topology.md).

Beachten Sie, dass es einige Zeit dauern kann (bis zu ein paar Stunden), bis einige Änderungen an den Netzwerkeinstellungen (wie einer neuen Adresse, einer Netzwerkkennung usw.) durchgestellt werden und für Teams-Clients verfügbar sind.  

**Für Benutzer von Plan anrufen:**

- Wenn die dynamische Konfiguration von Security Desk-Benachrichtigungen erforderlich ist, müssen Sie vertrauenswürdige IP-Adressen und Netzwerk Websites konfigurieren.

- Wenn nur dynamische Speicherorte erforderlich sind, müssen Sie nur vertrauenswürdige IP-Adressen konfigurieren.

- Wenn keines dieser beiden Anforderungen erforderlich ist, ist die Konfiguration von Netzwerkeinstellungen nicht erforderlich. 

**Für Direct Routing-Benutzer:**

- Wenn die dynamische Aktivierung von Notrufen oder die dynamische Konfiguration einer Security Desk-Benachrichtigung erforderlich ist, müssen Sie vertrauenswürdige IP-Adressen und Netzwerk Websites konfigurieren.

- Wenn nur dynamische Speicherorte erforderlich sind, müssen Sie nur vertrauenswürdige IP-Adressen konfigurieren.

- Wenn keines dieser beiden Anforderungen erforderlich ist, ist die Konfiguration von Netzwerkeinstellungen nicht erforderlich.


## <a name="configure-location-information-service"></a>Konfigurieren des Standort Informationsdiensts

Ein Team-Client ruft Notfalladressen von den Speicherorten ab, die verschiedenen Netzwerk-IDs zugeordnet sind. Sowohl Subnetze als auch Drahtloszugriffspunkte (WAPs) werden unterstützt. Ethernet-Switch/-Port wird in Windows 8,1 und höher unterstützt.

Damit ein Client einen Standort erhält, müssen Sie den LIS mit Netzwerkkennungen (Subnets, WAPs, Switches, Ports) und Notfall Speicherorten füllen. Sie können dies im Microsoft Teams Admin Center oder mithilfe von PowerShell tun.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie in der linken Navigationsleiste zu **Standorte**  >  **Netzwerke & Standorte**.
2. Klicken Sie auf die Registerkarte, die die Netzwerk-ID darstellt, die Sie hinzufügen möchten. Klicken Sie beispielsweise auf **Subnets** , **Wi-Fi-Zugriffspunkte** , **Switches** oder **Ports**. Klicken Sie dann auf **Hinzufügen**.
3. Füllen Sie die Felder aus, fügen Sie einen Notfall Standort hinzu, und klicken Sie dann auf über **nehmen**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie die folgenden Cmdlets, um dem LIS Ports, Switches, Subnetze und WAPs hinzuzufügen.

- [Abrufen](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Einrichten](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Entfernen](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Abrufen](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Einrichten](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Entfernen](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Abrufen](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Einrichten](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Entfernen](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Abrufen](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Einrichten](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Entfernen](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>Wenn Subnetze als Teil von Netzwerk Websites verwendet werden, müssen Sie im standortinformationsdienst neu definiert werden, um dynamische Speicherorte zu rendern.

## <a name="configure-emergency-policies"></a>Konfigurieren von Notfall Richtlinien

Verwenden Sie die folgenden Richtlinien, um Notrufe zu konfigurieren. Sie können diese Richtlinien im Microsoft Teams Admin Center oder mithilfe von PowerShell verwalten.

- **Routing Richtlinie für Notrufe** – gilt nur für die direkte Weiterleitung. Diese Richtlinie konfiguriert die Notfallnummern, die Masken pro Nummer, falls gewünscht, und die PSTN-Route pro Nummer.  Sie können diese Richtlinie Benutzern, Netzwerk Websites oder beiden zuweisen. (Anrufpläne Teams-Clients werden automatisch für Notrufe mit den Notrufnummern aus dem Land aktiviert, die auf Ihrem Microsoft 365-oder Office 365-Verwendungsstandort basieren.)  Weitere Informationen finden Sie unter [Verwalten von Notfall Anruf-Routing Richtlinien für die direkte Weiterleitung](manage-emergency-call-routing-policies.md).

- **Notfall Anrufrichtlinie** – gilt für Anrufpläne und direktes Routing. Mit dieser Richtlinie wird die Benachrichtigungsfunktionalität des Security Desk konfiguriert, wenn ein Notfall Anruf durchgeführt wird. Sie können die Personen, die benachrichtigt werden sollen, und deren Benachrichtigung einstellen. So können Sie beispielsweise den Security Desk Ihrer Organisation automatisch benachrichtigen und bei Notrufen abhören.  Diese Richtlinie kann entweder Benutzern oder Netzwerk Websites oder beiden zugewiesen werden. Weitere Informationen finden Sie unter [Verwalten von Notruf Richtlinien in Teams](manage-emergency-calling-policies.md).

## <a name="enable-users-and-sites"></a>Aktivieren von Benutzern und Websites

Sie können den Benutzern und Websites Notfall Anruf-Routing Richtlinien und Notruf Richtlinien zuweisen. Beachten Sie, dass die Routing Richtlinien für Notfälle nur für die direkte Weiterleitung gelten. (Obwohl es möglich ist, diese Richtlinie einem Anruf Plan Benutzer zuzuweisen, hat die Richtlinie keine Auswirkung.)

Sie weisen Richtlinien im Microsoft Teams Admin Center oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter:

- [Verwalten von Notfall Anruf Weiterleitungsrichtlinien für die direkte Weiterleitung](manage-emergency-call-routing-policies.md)
- [Verwalten von Notruf Richtlinien in Teams](manage-emergency-calling-policies.md)

Hier finden Sie einige Beispiele für PowerShell.

Verwenden Sie den folgenden Befehl, um einen bestimmten Benutzer für die Benachrichtigung über das Security Desk zu aktivieren:

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Verwenden Sie den folgenden Befehl, um eine Richtlinie namens "Contoso Emergency Calling Policy 1" zu Site 1 zuzuweisen:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Verwenden Sie den folgenden Befehl, um einen bestimmten direkten Routing Benutzer für Notrufe zu aktivieren:

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Verwenden Sie den folgenden Befehl, um eine Richtlinie namens "Contoso New York Emergency Call Routing" zu Site 1 zuzuweisen:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Wenn Sie einer Netzwerk Website und einem Benutzer eine Notruf Richtlinie zugewiesen haben und sich dieser Benutzer an dieser Netzwerk Website befindet, überschreibt die der Netzwerk Website zugewiesene Richtlinie die Richtlinie, die dem Benutzer zugewiesen ist.

## <a name="test-emergency-calling"></a>Testen von Notrufen

Einige Notverwaltungsdienste (Emergency Routing Service Providers, ERSPs) in den USA bieten einen Test-bot für Notrufe.

- **Benutzer des Anruf Plans in den Vereinigten Staaten** können mithilfe der vordefinierten Test Notfallnummer 933 ihre Notruf Konfiguration überprüfen. Diese Nummer wird an einen bot weitergeleitet, der dann wieder die Rufnummer des Anrufers (Rufnummernanzeige), die Notfalladresse oder den Standort zurückgibt und feststellt, ob der Anruf automatisch an die PSAP weitergeleitet oder zuerst übertragen wird.

- **Direct Routing-Kunden in den Vereinigten Staaten sollten sich** mit ihren ERSP für einen Testdienst koordinieren.

 ## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Verwalten von Notruf-Richtlinien](manage-emergency-calling-policies.md)
- [Verwalten von Notfall Anrufrouting Richtlinien ](manage-emergency-call-routing-policies.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Zuweisen oder Ändern eines Notfall Standorts für Ihren Benutzer](assign-change-emergency-location-user.md)
- [Netzwerkeinstellungen für Cloud Voice-Features](cloud-voice-network-settings.md)
- [Verwalten Ihrer Netzwerktopologie für Cloud Voice-Features](manage-your-network-topology.md)
