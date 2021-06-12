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
description: Erfahren Sie, wie Sie die Microsoft-Anrufpläne konfigurieren Telefonsystem dynamische Notruffunktion Direct Routing verwenden.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ee730c737d105572c9c34c6f329b04de4f8f8472
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2021
ms.locfileid: "52910047"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Planen und Konfigurieren dynamischer Notrufe 

Dynamische Notrufe für Microsoft-Anrufpläne und Telefonsystem Direct Routing bieten die Möglichkeit, Notrufe zu konfigurieren und zu weiterleiten sowie Sicherheitsmitarbeiter basierend auf dem aktuellen Standort des Teams-Clients zu benachrichtigen.  

Basierend auf der vom Mandantenadministrator definierten Netzwerktopologie stellt der Teams-Client In einer Anforderung an den Location Information Service (LIS) Netzwerkverbindungsinformationen zur Verfügung. Gibt es eine Übereinstimmung, gibt das LIS einen Standort an den Client zurück. Diese Standortdaten werden zurück an den Client übertragen.  

Der Teams-Client enthält Standortdaten als Teil eines Notrufs. Diese Daten werden dann vom Notdienstanbieter verwendet, um den entsprechenden PUBLIC Safety Answering Point (PSAP) zu ermitteln und den Anruf an dieses PSAP weiter zu routen, wodurch der PSAP-Verteiler den Standort des Anrufers abrufen kann.  

Bei dynamischen Notrufen muss Folgendes geschehen:

1. Der Netzwerkadministrator konfiguriert Netzwerkeinstellungen und das LIS, um eine Netzwerk-/Notfallstandortkarte zu erstellen.

   Für Direct-Routing ist zusätzliche Konfiguration für Das Routing von Notrufen und möglicherweise für Partnerkonnektivität erforderlich. Der Administrator muss die Verbindung mit einem ANBIETER für Notfallroutingdienste (EMERGENCY Routing Service, **ERS)** konfigurieren oder den Session Border Controller (SBC) für eine ELIN-Anwendung (Emergency Location Identification Number) konfigurieren.

2. Während des Startvorgangs und in regelmäßigen Abständen oder bei einer Änderung einer Netzwerkverbindung sendet der Teams-Client eine Standortanforderung, die Informationen zur Netzwerkkonnektivität enthält, an die Netzwerkeinstellungen und das LIS.

   - Wenn eine Übereinstimmung mit der Website mit den Netzwerkeinstellungen besteht – Richtlinien für Notrufe werden an den Teams von diesem Standort zurückgegeben. (Weitere Informationen zu Richtlinien finden Sie unter [Konfigurieren von Notfallrichtlinien).](#configure-emergency-policies)

   - Wenn eine LIS-Übereinstimmung vor liegt – ein Notfallstandort aus dem Netzwerkelement, mit dem der Teams-Client verbunden ist, wird an den Teams-Client zurückgegeben. Die Übereinstimmung wird in der folgenden Reihenfolge ausgeführt, und das erste übereinstimmende Ergebnis wird zurückgegeben:
       - WAP
       - Ethernet-Schalter/-port
       - Ethernet-Schalter
       - Subnetz

3. Wenn der Teams einen Notruf abruft, wird der Notfallstandort an das PSTN-Netzwerk übermittelt.

   Für Direct-Routing muss der Administrator den SBC so konfigurieren, dass Notrufe an den ERS-Anbieter gesendet werden, oder er muss die SBC-ELIN-Anwendung konfigurieren.

Dieser Artikel enthält die folgenden Abschnitte.

- [Konfigurieren von Notfalladressen](#assign-emergency-addresses)
- [Konfigurieren von Netzwerkeinstellungen](#configure-network-settings)
- [Konfigurieren des Informationsdiensts für den Standort](#configure-location-information-service)
- [Konfigurieren von Notfallrichtlinien](#configure-emergency-policies)
- [Aktivieren von Benutzern und Websites](#enable-users-and-sites)
- [Testen von Notrufen](#test-emergency-calling)

Die Möglichkeit zur automatischen Weiterleitung an den entsprechenden Public Safety Answering Point (PSAP) variiert je nach Land der Teams Benutzer.

Weitere Informationen zu Notrufen, einschließlich Informationen zu Notfalladressen und Notrufrouting, Länderspezifische Informationen sowie Informationen zu Netzwerkeinstellungen und Netzwerktopologie finden Sie unter den folgenden Themen:

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Verwalten von Netzwerkeinstellungen für Cloud-Sprachfeatures](cloud-voice-network-settings.md)
- [Verwalten Ihrer Netzwerktopologie für Cloud Voice-Features](manage-your-network-topology.md)

Weitere Informationen dazu, welche Features in den Government Clouds verfügbar sind, finden Sie unter [Government Support](#government-support) am Ende dieses Artikels.


## <a name="supported-clients"></a>Unterstützte Clients

Die folgenden Clients werden derzeit unterstützt.  Schauen Sie häufig wieder hin, um Aktualisierungen dieser Liste zu sehen.

- Teams-Desktopclient für Microsoft Windows
- Teams-Desktopclient für Apple macOS
- Teams mobiler Client für den Apple iOS-Client, Version 1.0.92.2019121004 und App Store Version 1.0.92 und höher
- Teams mobiler Client für Den Android-Client und Google Play Store, Version 1416/1.0.0.2019121201 und höher
- Teams 1449/1.0.94.2019110802 und höher
- Teams-Räume Version 4.4.25.0 und höher

> [!NOTE]
> Dynamische Notrufe, einschließlich Benachrichtigungen des Sicherheitsdesks, werden auf dem Webclient Teams nicht unterstützt. Um zu verhindern, dass Benutzer den Teams-Webclient zum Anrufen von PSTN-Nummern verwenden, können Sie eine Richtlinie für Teams-Anrufe festlegen und die Einstellung **Web-PSTN-Anruf** zulassen deaktivieren. Weitere Informationen finden Sie unter [Anrufrichtlinien in Teams](teams-calling-policy.md) [und Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) 

> [!NOTE]
> Subnetz- und WLAN-basierte Standorte werden auf allen Clients Teams unterstützt. <br>
> Ethernet/Switch (LLDP) wird derzeit nur auf Windows und nur Windows Versionen 8.1 und höher unterstützt.

## <a name="assign-emergency-addresses"></a>Zuweisen von Notfalladressen

Sie können sowohl Anrufplanbenutzern als auch Den Netzwerk-IDs, die zum dynamischen Abrufen eines Standorts erforderlich sind, Notfalladressen zuweisen. (Subnetz- und WLAN-AP werden unterstützt. Ethernet-Switch/-Port wird auf Windows 8.1 zu diesem Zeitpunkt und höher unterstützt).

Um das automatisierte Routing von Notrufen innerhalb der USA zu unterstützen, müssen Sie sicherstellen, dass die Notfallstandorte, die Netzwerk-IDs zugewiesen sind, die zugeordneten Geocodes enthalten. (Notfalladressen ohne Geocodes können den Netzwerkbezeichnern, die für dynamische Standorte erforderlich sind, nicht zugewiesen werden.)

Azure Karten wird für standortbasierte Dienste verwendet.  Wenn Sie eine Notfalladresse über das Microsoft Teams Admin Center eingeben, überprüft Teams Azure-Karten auf die Adresse:

- Wenn eine Übereinstimmung gefunden wird, werden die Geocodes automatisch einbezogen.

- Wenn keine Übereinstimmung gefunden wird, haben Sie die Möglichkeit, eine Notfalladresse manuell zu erstellen. Dazu können Sie die Pin-Drop-Funktion verwenden. 

Dies bedeutet Folgendes: Wenn ein vorhandener Notfallstandort, der für die Zuweisung zu Anrufplanbenutzern erstellt wurde, für einen dynamischen Standort vorgesehen ist, muss dieselbe Adresse neu erstellt werden, um die Geocodes zu enthalten. Um zwischen den beiden Speicherorten zu unterscheiden, sollten Sie eine andere Beschreibung eingeben. Der neue Notfallstandort kann den Benutzern zugewiesen werden, die über den alten Standort verfügen. Nach der vollständigen Migration kann der alte Speicherort gelöscht werden.

Sie fügen Notfalladressen im Microsoft Teams Admin Center oder mithilfe von PowerShell hinzu und weisen diese zu. Weitere Informationen finden Sie unter [Hinzufügen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md) und Zuweisen eines [Notfallstandorts für einen Benutzer.](assign-change-emergency-location-user.md)

## <a name="configure-network-settings"></a>Konfigurieren von Netzwerkeinstellungen

Netzwerkeinstellungen werden verwendet, um den Standort eines Teams-Clients zu ermitteln und dynamisch Richtlinien für Notrufe und einen Notfallstandort zu erhalten. Sie können Netzwerkeinstellungen entsprechend der Art konfigurieren, in der Ihre Organisation Notrufe nutzen möchte.

Netzwerkeinstellungen umfassen Standorte, die eine Sammlung von Subnetzen umfassen, und diese werden ausschließlich für die dynamische Richtlinienzuweisung zu Benutzern verwendet. So könnten beispielsweise eine Richtlinie für Notrufe und eine Richtlinie für die Weiterleitung von Notrufen der "Redmond-Website" zugewiesen werden, damit für jeden Benutzer, der von zu Hause oder an einem anderen Microsoft-Standort ans Telefon geht, Notrufnummern, Weiterleitung und Sicherheitsleitstelle für Redmond konfiguriert ist.  

>[!Note]
>Subnetze können auch in LIS definiert und einem Notfallstandort zugeordnet werden.  LIS-Subnetze müssen durch die Netzwerk-ID definiert werden, die mit dem Subnetz-IP-Bereich übereinstimmen, der Clients zugewiesen ist. Beispielsweise ist die Netzwerk-ID für eine Client-IP/Mask von 10.10.10.150/25 **10.10.10.128.** Weitere Informationen finden Sie unter [Grundlegendes zu TCP/IP-Adressierung und Subnetzing.](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting)

Beachten Sie die folgenden Definitionen. Weitere Informationen finden Sie unter [Netzwerkeinstellungen für Cloud-Sprachfeatures.](cloud-voice-network-settings.md)

- Vertrauenswürdige IP-Adressen enthalten eine Sammlung der externen Internet-IP-Adressen des Unternehmensnetzwerks und werden verwendet, um festzustellen, ob sich der Endpunkt des Benutzers innerhalb des Unternehmensnetzwerks befindet. Der Versuch, eine dynamische Richtlinie oder einen dynamischen Speicherort zu erhalten, erfolgt nur, wenn die externe IP-Adresse des Benutzers einer IP-Adresse in der vertrauenswürdigen IP-Adresse entspricht. Eine Übereinstimmung kann mit IPv4- oder IPv6-IP-Adressen vorgenommen werden und hängt vom Format des IP-Pakets ab, das an die Netzwerkeinstellungen gesendet wurde.  (Wenn eine öffentliche IP-Adresse sowohl IPv4 als auch IPv6 enthält, müssen Sie beide als vertrauenswürdige IP-Adressen hinzufügen.)

- Eine Netzwerkregion enthält verschiedene Netzwerkstandorte. 

- Ein Netzwerkstandort stellt einen Ort dar, an dem Ihre Organisation einen physischen Wert hat, z. B. ein Büro, eine Gruppe von Gebäuden oder einen Campus. Diese Standorte sind als eine Sammlung von IP-Subnetzen definiert.

- Ein Netzwerksubnetz muss einem bestimmten Netzwerkstandort zugeordnet sein. Der Standort eines Clients wird basierend auf dem Netzwerksubnetz und dem zugehörigen Netzwerkstandort bestimmt.  

Sie konfigurieren Netzwerkeinstellungen im Microsoft Teams Admin Center oder mithilfe von PowerShell. Weitere Informationen finden Sie unter [Verwalten der Netzwerktopologie für Cloud-Sprachfeatures.](manage-your-network-topology.md)

Beachten Sie, dass es einige Zeit (bis zu ein paar Stunden) dauern kann, bis einige Änderungen an den Netzwerkeinstellungen (z. B. neue Adresse, Netzwerk-ID und so weiter) an die Clients weiterverteilt Teams werden.  

**Für Anrufplanbenutzer:**

- Wenn eine dynamische Konfiguration der Benachrichtigung des Sicherheitsdesks erforderlich ist, müssen Sie sowohl vertrauenswürdige IP-Adressen als auch Netzwerkwebsites konfigurieren.

- Wenn nur dynamische Speicherorte erforderlich sind, dürfen Sie nur vertrauenswürdige IP-Adressen konfigurieren.

- Wenn keines dieser Einstellungen erforderlich ist, ist keine Konfiguration der Netzwerkeinstellungen erforderlich. 

**Für Benutzer des Direct-Routings:**

- Wenn eine dynamische Aktivierung von Notrufen oder eine dynamische Konfiguration der Benachrichtigung des Sicherheitsdesks erforderlich ist, müssen Sie sowohl vertrauenswürdige IP-Adressen als auch Netzwerkwebsites konfigurieren.

- Wenn nur dynamische Speicherorte erforderlich sind, dürfen Sie nur vertrauenswürdige IP-Adressen konfigurieren.

- Wenn keines dieser Einstellungen erforderlich ist, ist keine Konfiguration der Netzwerkeinstellungen erforderlich.


## <a name="configure-location-information-service"></a>Konfigurieren des Informationsdiensts für den Standort

Ein Teams-Client ruft Notfalladressen von den Standorten ab, die unterschiedlichen Netzwerk-IDs zugeordnet sind. Sowohl Subnetze als auch Funkzugriffspunkte (WaPs) werden unterstützt. Ethernet-Switch/-Port wird auf Windows 8.1 zu diesem Zeitpunkt unterstützt.

Damit ein Client einen Standort erhält, müssen Sie das LIS mit Netzwerk-IDs (Subnetzen, WAPs, Schaltern, Ports) und Notfallstandorten füllen. Dies können Sie im Microsoft Teams Admin Center oder mithilfe von PowerShell tun.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Navigieren Sie im linken Navigationsbereich **zu** Locations  >  **Networks & Locations**.
2. Klicken Sie auf die Registerkarte, die die hinzuzufügende Netzwerk-ID darstellt. Klicken Sie z. B. **auf Subnetze,** **WLAN-Zugriffspunkte,** **Schalter** oder **Ports**. Klicken Sie dann auf **Hinzufügen**.
3. Füllen Sie die Felder aus, fügen Sie einen Notfallstandort hinzu, und klicken Sie dann auf **Übernehmen**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie die folgenden Cmdlets, um Ports, Switches, Subnetze und WAPs zum LIS hinzuzufügen.

- [Get](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Get](/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Get](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Get](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>Wenn Subnetze als Teil von Netzwerkstandorten verwendet werden, müssen sie im Location Information Service neu definiert werden, um dynamische Speicherorte zu rendern.

## <a name="configure-emergency-policies"></a>Konfigurieren von Notfallrichtlinien

Verwenden Sie die folgenden Richtlinien zum Konfigurieren von Notrufen. Sie können diese Richtlinien im Microsoft Teams Admin Center oder mithilfe von PowerShell verwalten.

- **Richtlinie zum Routing von Notrufen** – Gilt nur für direktes Routing. Mit dieser Richtlinie werden Notfallnummern, Masken pro Nummer bei Bedarf und die PSTN-Route pro Nummer konfiguriert.  Sie können diese Richtlinie Benutzern, Netzwerkwebsites oder beiden zuweisen. (Anrufpläne Teams-Clients werden automatisch für Notrufe mit den Notrufnummern aus dem Land basierend auf ihren Microsoft 365 oder Office 365-Standort aktiviert.)  Weitere Informationen finden Sie unter [Verwalten von Richtlinien für das Routing von Notrufen für Direct Routing.](manage-emergency-call-routing-policies.md)

- **Richtlinie für Notrufe** – Gilt für Anrufpläne und direktes Routing. Mit dieser Richtlinie wird die Benachrichtigung des Sicherheitsdesks konfiguriert, wenn ein Notruf erfolgt. Sie können festlegen, wer benachrichtigt werden soll und wie er benachrichtigt wird. Beispielsweise, um die Sicherheitsanrufe der Organisation automatisch zu benachrichtigen und sie bei Notrufen anhören zu lassen.  Diese Richtlinie kann entweder Benutzern oder Netzwerkwebsites oder beiden zugewiesen werden. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für Notrufe in Teams.](manage-emergency-calling-policies.md)

## <a name="enable-users-and-sites"></a>Aktivieren von Benutzern und Websites

Sie können Benutzern und Standorten Richtlinien für die Weiterleitung von Notrufen und Notrufen zuweisen. Beachten Sie, dass Richtlinien für das Routing von Notrufen nur für das Direct-Routing gelten. (Obwohl es möglich ist, diese Richtlinie einem Anrufplanbenutzer zuzuordnen, hat die Richtlinie keine Auswirkung.)

Sie weisen Richtlinien im Microsoft Teams Admin Center oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter:

- [Verwalten von Richtlinien für das Routing von Notrufen für Direct Routing](manage-emergency-call-routing-policies.md)
- [Verwalten von Richtlinien für Notrufe in Teams](manage-emergency-calling-policies.md)

Hier sind einige PowerShell-Beispiele.

Verwenden Sie den folgenden Befehl, um einen bestimmten Benutzer für die Benachrichtigung des Sicherheitsdesks zu aktivieren:

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Verwenden Sie den folgenden Befehl, um Standort 1 eine Richtlinie namens "Contoso-Notrufrichtlinie 1" zuzuordnen:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Um einen bestimmten Direct Routing-Benutzer für Notrufe zu aktivieren, verwenden Sie den folgenden Befehl:

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Zum Zuweisen einer Richtlinie namens "Contoso New York Emergency Call Routing" zu Standort 1 verwenden Sie den folgenden Befehl:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Wenn Sie einer Netzwerkwebsite und einem Benutzer eine Richtlinie für Notrufe zugewiesen haben und sich der Benutzer an diesem Netzwerkstandort befindet, setzt die Richtlinie, die dem Netzwerkstandort zugewiesen ist, die Dem Benutzer zugewiesene Richtlinie außer Kraft.

## <a name="test-emergency-calling"></a>Testen von Notrufen

Einige Anbieter von Notfall-Routingdiensten (Emergency Routing Service Provider, ERSPs) in den USA bieten einen Testbot für Notrufe an.

- **Anrufplanbenutzer in den USA** können die vordefinierte Testnotrufnummer 933 verwenden, um die Konfiguration für Notrufe zu überprüfen. Diese Nummer wird an einen Bot geroutet, der dann die Rufnummer des Anrufers (Anrufer-ID), die Notfalladresse oder den Standort ans Licht benennen kann und ob der Anruf automatisch an das PSAP umleitunget oder zuerst angezeigt wird.

- **Kunden mit Direct Routing in den USA sollten** sich mit ihrem ERSP für einen Testdienst koordinieren.

## <a name="government-support"></a>Government support

Die folgende Tabelle zeigt die Unterstützung für dynamische Notrufe in Behördenwolken:

| Cloud | Verfügbarkeit |
| :------------|:-------|
| World Wide Multi Tenant | Verfügbar auf allen Teams Clients |
| GCC | Verfügbar auf allen Teams Clients |
| GGCH | Verfügbar auf Teams Desktops |
| DoD | Ausstehend |

 ## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Verwalten von Notruf-Richtlinien](manage-emergency-calling-policies.md)
- [Verwalten von Richtlinien für das Routing von Notrufen ](manage-emergency-call-routing-policies.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Zuweisen oder Ändern eines Notfallstandorts für den Benutzer](assign-change-emergency-location-user.md)
- [Netzwerkeinstellungen für Cloud Voice-Features](cloud-voice-network-settings.md)
- [Verwalten Ihrer Netzwerktopologie für Cloud Voice-Features](manage-your-network-topology.md)
