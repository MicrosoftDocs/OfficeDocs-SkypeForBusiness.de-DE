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
description: Erfahren Sie, wie Sie das Feature für dynamische Notfallanrufe für Microsoft Calling Plans und Phone System Direct Routing konfigurieren.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2531add2b43b7061b81a23676c54fbc557929c0f
ms.sourcegitcommit: 2ce82f301f2d59da57f579a23038b2cab5e31360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51858008"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Planen und Konfigurieren dynamischer Notrufe 

Dynamische Notrufe für Microsoft Calling Plans und Telefonsystem Direct Routing bieten die Möglichkeit zum Konfigurieren und Weiterleiten von Notrufen und zum Benachrichtigen von Sicherheitsmitarbeitern basierend auf dem aktuellen Standort des Teams-Clients.  

Basierend auf der vom Mandantenadministrator definierten Netzwerktopologie stellt der Teams-Client Informationen zur Netzwerkkonnektivität in einer Anforderung an den Standortinformationsdienst (Location Information Service, LIS) zur Verfügung. Wenn eine Übereinstimmung vorkommt, gibt die LIS einen Speicherort an den Client zurück. Diese Standortdaten werden an den Client zurück übertragen.  

Der Teams-Client enthält Standortdaten als Teil eines Notrufs. Diese Daten werden dann vom Notfalldienstanbieter verwendet, um den geeigneten öffentlichen Sicherheitsanrufpunkt (Public Safety Answering Point, PSAP) zu ermitteln und den Anruf an dieses PSAP weiter zu verweisen, wodurch der PSAP-Disponent den Standort des Anrufers abrufen kann.  

Bei dynamischen Notrufen muss Folgendes auftreten:

1. Der Netzwerkadministrator konfiguriert die Netzwerkeinstellungen und die LIS, um eine Netzwerk-/Notfallspeicherortzuordnung zu erstellen.

   Für Direct Routing ist eine zusätzliche Konfiguration für das Routing von Notrufen und möglicherweise für partnerkonnektivität erforderlich. Der Administrator muss die Verbindung zu einem Notfallleitplandienstanbieter  (Emergency Routing Service, ERS) (USA) konfigurieren oder den Session Border Controller (SBC) für eine Notfallstandortidentifikationsnummer (Emergency Location Identification Number, ELIN) konfigurieren.

2. Während des Startvorgangs und in regelmäßigen Abständen danach oder bei einer Änderung einer Netzwerkverbindung sendet der Teams-Client eine Standortanforderung, die die Netzwerkverbindungsinformationen enthält, an die Netzwerkeinstellungen und die LIS.

   - Wenn eine Netzwerkeinstellungen-Website übereinstimmen – Richtlinien für Notrufe werden von dieser Website an den Teams-Client zurückgegeben. (Weitere Informationen zu Richtlinien finden Sie unter [Konfigurieren von Notfallrichtlinien](#configure-emergency-policies)).

   - Wenn es eine LIS-Übereinstimmung gibt – ein Notfallspeicherort aus dem Netzwerkelement, mit dem der Teams-Client verbunden ist, wird an den Teams-Client zurückgegeben. Die Übereinstimmung wird in der folgenden Reihenfolge ausgeführt, und das erste übereinstimmende Ergebnis wird zurückgegeben:
       - WAP
       - Ethernet-Switch/-Port
       - Ethernet-Switch
       - Subnetz

3. Wenn der Teams-Client einen Notruf abruft, wird der Notfallstandort an das PSTN-Netzwerk übermittelt.

   Bei Direct Routing muss der Administrator den SBC so konfigurieren, dass Notrufe an den ERS-Anbieter gesendet werden oder die SBC-ELIN-Anwendung konfiguriert wird.

Dieser Artikel enthält die folgenden Abschnitte.

- [Konfigurieren von Notfalladressen](#assign-emergency-addresses)
- [Konfigurieren von Netzwerkeinstellungen](#configure-network-settings)
- [Konfigurieren des Standortinformationsdiensts](#configure-location-information-service)
- [Konfigurieren von Notfallrichtlinien](#configure-emergency-policies)
- [Aktivieren von Benutzern und Websites](#enable-users-and-sites)
- [Testen von Notrufen](#test-emergency-calling)

Die Möglichkeit zum automatischen Routing an den entsprechenden Public Safety Answering Point (PSAP) variiert je nach Nutzungsland des Teams-Benutzers.

Weitere Informationen zu Notrufen, einschließlich Informationen zu Notfalladressen und Notfallanrufrouting, länderspezifische Informationen sowie Informationen zu Netzwerkeinstellungen und Netzwerktopologie finden Sie in den folgenden Themen:

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Verwalten von Netzwerkeinstellungen für Cloud-Sprachfeatures](cloud-voice-network-settings.md)
- [Verwalten Ihrer Netzwerktopologie für Cloud Voice-Features](manage-your-network-topology.md)

Weitere Informationen zu den Features, die in den Clouds der Regierung verfügbar sind, finden Sie unter [Unterstützung](#government-support) durch die Regierung am Ende dieses Artikels.


## <a name="supported-clients"></a>Unterstützte Clients

Die folgenden Clients werden derzeit unterstützt.  Schauen Sie häufig zurück, um Aktualisierungen dieser Liste zu sehen.

- Teams-Desktopclient für Microsoft Windows
- Teams-Desktopclient für Apple macOS
- Mobiler Teams-Client für Apple iOS, Version 1.0.92.2019121004 und App Store, Version 1.0.92 und höher
- Mobiler Teamclient für Android-Client und Google Play Store, Version 1416/1.0.0.2019121201 und höher
- Version 1449/1.0.94.2019110802 und höher
- Teams Rooms, Version 4.4.25.0 und höher

> [!NOTE]
> Dynamische Notrufe einschließlich Benachrichtigungen über den Sicherheitsschalter werden im Teams-Webclient nicht unterstützt. Um zu verhindern, dass Benutzer den Teams-Webclient zum Aufrufen von PSTN-Nummern verwenden, können Sie eine Anrufrichtlinie für Teams festlegen und die Einstellung **Web-PSTN-Anrufe zulassen** deaktivieren. Weitere Informationen finden Sie unter [Aufrufen von Richtlinien in Teams](teams-calling-policy.md) und [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).

## <a name="assign-emergency-addresses"></a>Zuweisen von Notfalladressen

Sie können Sowohl Anrufplanbenutzern als auch den Netzwerkbezeichnern, die zum dynamischen Abrufen eines Standorts erforderlich sind, Notfalladressen zuweisen. (Subnetz- und WLAN-AP werden unterstützt. Ethernet-Switch/-Port wird zu diesem Zeitpunkt Windows 8.1 und höher unterstützt).

Um das automatisierte Routing von Notrufen innerhalb der USA zu unterstützen, müssen Sie sicherstellen, dass die Notfallstandorte, die Netzwerkbezeichnern zugewiesen sind, die zugeordneten Geocodes enthalten. (Notfalladressen ohne Geocodes können den Netzwerkbezeichnern, die für dynamische Speicherorte erforderlich sind, nicht zugewiesen werden.)

Azure Maps wird für standortbasierte Dienste verwendet.  Wenn Sie über das Microsoft Teams Admin Center eine Notfalladresse eingeben, überprüft Teams Azure Maps auf die Adresse:

- Wenn eine Übereinstimmung gefunden wird, werden die Geocodes automatisch einbezogen.

- Wenn keine Übereinstimmung gefunden wird, haben Sie die Möglichkeit, manuell eine Notfalladresse zu erstellen. Dazu können Sie die Pin-Drop-Funktion verwenden. 

Dies bedeutet: Wenn ein vorhandener Notfallstandort, der zum Zuweisen von Anrufplanbenutzern erstellt wird, für einen dynamischen Standort vorgesehen ist, muss dieselbe Adresse neu erstellt werden, um die Geocodes zu enthalten. Um zwischen den beiden Speicherorten zu unterscheiden, sollten Sie eine andere Beschreibung eingeben. Der neue Notfallstandort kann den Benutzern zugewiesen werden, die über den alten Standort verfügen. Nach der vollständigen Migration kann der alte Speicherort gelöscht werden.

Sie fügen Notfalladressen im Microsoft Teams Admin Center oder mithilfe von PowerShell hinzu und weisen sie zu. Weitere Informationen finden Sie unter [Hinzufügen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md) und Zuweisen eines Notfallstandorts für einen [Benutzer.](assign-change-emergency-location-user.md)

## <a name="configure-network-settings"></a>Konfigurieren von Netzwerkeinstellungen

Netzwerkeinstellungen werden verwendet, um den Standort eines Teams-Clients zu bestimmen und richtlinien für Notrufe und einen Notfallstandort dynamisch zu erhalten. Sie können Netzwerkeinstellungen entsprechend der Art und Weise konfigurieren, in der Ihre Organisation Notrufe verwenden möchte.

Zu den Netzwerkeinstellungen gehören Websites, die eine Sammlung von Subnetzen enthalten und die ausschließlich für die dynamische Richtlinienzuweisung für Benutzer verwendet werden. So könnten beispielsweise eine Richtlinie für Notrufe und eine Richtlinie für die Weiterleitung von Notrufen der "Redmond-Website" zugewiesen werden, sodass jeder Benutzer, der von zu Hause oder einem anderen Microsoft-Standort aus durchstreift, mit Notrufnummern, Routing und Einem Security Desk speziell für Redmond konfiguriert ist.  

>[!Note]
>Subnetze können auch in LIS definiert und einem Notfallstandort zugeordnet werden.  

Beachten Sie die folgenden Definitionen. Weitere Informationen finden Sie unter [Netzwerkeinstellungen für Cloud-Sprachfeatures.](cloud-voice-network-settings.md)

- Vertrauenswürdige IP-Adressen enthalten eine Sammlung der externen Internet-IP-Adressen des Unternehmensnetzwerks und werden verwendet, um festzustellen, ob sich der Endpunkt des Benutzers innerhalb des Unternehmensnetzwerks befindet. Ein Versuch, eine dynamische Richtlinie oder einen dynamischen Speicherort zu erhalten, wird nur dann vorgenommen, wenn die externe IP-Adresse des Benutzers einer IP-Adresse in der vertrauenswürdigen IP-Adresse entspricht. Eine Übereinstimmung kann entweder mit IPv4- oder IPv6-IP-Adressen vorgenommen werden und hängt vom Format des an die Netzwerkeinstellungen gesendeten IP-Pakets ab.  (Wenn eine öffentliche IP-Adresse sowohl IPv4 als auch IPv6 enthält, müssen Sie beide als vertrauenswürdige IP-Adressen hinzufügen.)

- Eine Netzwerkregion enthält verschiedene Netzwerkstandorte. 

- Eine Netzwerkwebsite stellt einen Ort dar, an dem Ihre Organisation einen physischen Wert hat, z. B. ein Büro, eine Reihe von Gebäuden oder einen Campus. Diese Websites sind als eine Sammlung von IP-Subnetzen definiert.

- Ein Netzwerksubnetz muss einer bestimmten Netzwerkwebsite zugeordnet sein. Der Standort eines Clients wird basierend auf dem Netzwerksubnetz und der zugeordneten Netzwerkwebsite bestimmt.  

Sie konfigurieren Netzwerkeinstellungen im Microsoft Teams Admin Center oder mithilfe von PowerShell. Weitere Informationen finden Sie unter [Verwalten der Netzwerktopologie für Cloud-Sprachfeatures.](manage-your-network-topology.md)

Beachten Sie, dass es einige Zeit (bis zu ein paar Stunden) dauern kann, bis einige Änderungen an den Netzwerkeinstellungen (z. B. eine neue Adresse, netzwerkbezeichner und so weiter) vorgenommen wurden, um die Daten weiter zu vermehren und den Teams-Clients zur Verfügung zu stehen.  

**Für Anrufplanbenutzer:**

- Wenn eine dynamische Konfiguration der Security Desk-Benachrichtigung erforderlich ist, müssen Sie sowohl vertrauenswürdige IP-Adressen als auch Netzwerkwebsites konfigurieren.

- Wenn nur dynamische Speicherorte erforderlich sind, müssen Sie nur vertrauenswürdige IP-Adressen konfigurieren.

- Wenn keines dieser Einstellungen erforderlich ist, ist das Konfigurieren von Netzwerkeinstellungen nicht erforderlich. 

**Für Direct Routing-Benutzer:**

- Wenn eine dynamische Aktivierung von Notrufen oder eine dynamische Konfiguration der Security Desk-Benachrichtigung erforderlich ist, müssen Sie sowohl vertrauenswürdige IP-Adressen als auch Netzwerkwebsites konfigurieren.

- Wenn nur dynamische Speicherorte erforderlich sind, müssen Sie nur vertrauenswürdige IP-Adressen konfigurieren.

- Wenn keines dieser Einstellungen erforderlich ist, ist das Konfigurieren von Netzwerkeinstellungen nicht erforderlich.


## <a name="configure-location-information-service"></a>Konfigurieren des Standortinformationsdiensts

Ein Teams-Client ruft Notfalladressen von den Speicherorten ab, die verschiedenen Netzwerkbezeichnern zugeordnet sind. Sowohl Subnetze als auch WLAN-Access Points (WAPs) werden unterstützt. Ethernet-Switch/-Port wird zu diesem Zeitpunkt Windows 8.1 und höher unterstützt.

Damit ein Client einen Speicherort abrufen kann, müssen Sie die LIS mit Netzwerkbezeichnern (Subnetze, WAPs, Switches, Ports) und Notfallspeicherorten füllen. Sie können dies im Microsoft Teams Admin Center oder mithilfe von PowerShell tun.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie in der linken Navigationsleiste zu  >  **Speicherorte & Speicherorte.**
2. Klicken Sie auf die Registerkarte, die den Netzwerkbezeichner darstellt, den Sie hinzufügen möchten. Klicken Sie beispielsweise auf **Subnetze,** **WLAN-Zugriffspunkte,** **Schalter** oder **Ports.** Klicken Sie dann auf **Hinzufügen.**
3. Füllen Sie die Felder aus, fügen Sie einen Notfallstandort hinzu, und klicken Sie dann auf **Übernehmen.**

### <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie die folgenden Cmdlets, um der LIS Ports, Switches, Subnetze und WAPs hinzuzufügen.

- [Get](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Get](/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Get](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Get](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>Wenn Subnetze als Teil von Netzwerkwebsites verwendet werden, müssen sie im Standortinformationsdienst neu definiert werden, um dynamische Speicherorte zu rendern.

## <a name="configure-emergency-policies"></a>Konfigurieren von Notfallrichtlinien

Verwenden Sie die folgenden Richtlinien zum Konfigurieren von Notrufen. Sie können diese Richtlinien im Microsoft Teams Admin Center oder mithilfe von PowerShell verwalten.

- **Richtlinie für das Routing von Notrufen** – Gilt nur für direktes Routing. Diese Richtlinie konfiguriert die Notfallnummern, Masken pro Nummer bei Bedarf und die PSTN-Route pro Nummer.  Sie können diese Richtlinie Benutzern, Netzwerkwebsites oder beiden zuweisen. (Anrufpläne Teams-Clients werden automatisch für Notrufe mit den Notrufnummern aus dem Land aktiviert, die auf ihrem Microsoft 365- oder Office 365-Nutzungsstandort basieren.)  Weitere Informationen finden Sie unter [Verwalten von Routingrichtlinien für Notrufe für Direct Routing](manage-emergency-call-routing-policies.md).

- **Richtlinie für Notrufe** – Gilt für Anrufpläne und direktes Routing. Mit dieser Richtlinie wird die Benachrichtigungserfahrung des Security Desk konfiguriert, wenn ein Notruf erfolgt. Sie können festlegen, wer benachrichtigt werden soll und wie sie benachrichtigt werden. Beispielsweise, um den Sicherheitsschalter Ihrer Organisation automatisch zu benachrichtigen und sie bei Notrufen anhören zu lassen.  Diese Richtlinie kann entweder Benutzern oder Netzwerkwebsites oder beiden zugewiesen werden. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für Notrufe in Teams.](manage-emergency-calling-policies.md)

## <a name="enable-users-and-sites"></a>Aktivieren von Benutzern und Websites

Sie können Benutzern und Websites Richtlinien für das Routing von Notrufen und Notfallanrufen zuweisen. Beachten Sie, dass Richtlinien für das Routing von Notrufen nur für direktes Routing gelten. (Obwohl es möglich ist, diese Richtlinie einem Anrufplanbenutzer zuzuordnen, hat die Richtlinie keine Auswirkung.)

Sie weisen Richtlinien im Microsoft Teams Admin Center oder mithilfe von PowerShell zu. Weitere Informationen finden Sie unter:

- [Verwalten von Routingrichtlinien für Notrufe für Direct Routing](manage-emergency-call-routing-policies.md)
- [Verwalten von Richtlinien für Notrufe in Teams](manage-emergency-calling-policies.md)

Hier sind einige PowerShell-Beispiele.

Verwenden Sie den folgenden Befehl, um einen bestimmten Benutzer für die Benachrichtigung am Security Desk zu aktivieren:

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Verwenden Sie den folgenden Befehl, um Website 1 eine Richtlinie namens "Richtlinie für Contoso-Notrufe 1" zuzuordnen:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Um einen bestimmten Direct Routing-Benutzer für Notrufe zu aktivieren, verwenden Sie den folgenden Befehl:

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Verwenden Sie den folgenden Befehl, um Website 1 eine Richtlinie namens "Contoso New York Emergency Call Routing" zuzuordnen:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Wenn Sie einer Netzwerkwebsite und einem Benutzer eine Richtlinie für Notrufe zugewiesen haben und sich dieser Benutzer auf dieser Netzwerkwebsite befindet, setzt die Der Netzwerkwebsite zugewiesene Richtlinie die dem Benutzer zugewiesene Richtlinie außer Kraft.

## <a name="test-emergency-calling"></a>Testen von Notrufen

Einige Notfallroutedienstanbieter (Emergency Routing Service Providers, ERSPs) in den USA bieten einen Testbot für Notrufe an.

- **Anrufplanbenutzer in den USA** können die vordefinierte Testnotrufnummer 933 verwenden, um ihre Konfiguration für Notrufe zu überprüfen. Diese Nummer wird an einen Bot gesendet, der dann die Rufnummer des Anrufers (Anrufer-Rufnummer), die Notfalladresse oder den Ort zurücksenkert und ob der Anruf automatisch an das PSAP gesendet oder zuerst angezeigt wird.

- **Direct Routing-Kunden in den USA** sollten sich mit ihrem ERSP für einen Testdienst koordinieren.

## <a name="government-support"></a>Unterstützung durch die Regierung

Die folgende Tabelle zeigt die Unterstützung für dynamische Notrufe in den Regierungswolken:

| Cloud | Verfügbarkeit |
| :------------|:-------|
| World Wide Multi Tenant | Verfügbar für alle Teams-Clients |
| GCC | Verfügbar für alle Teams-Clients |
| GCCH | Auf dem Desktop von Teams verfügbar |
| DoD | Ausstehend |

 ## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Verwalten von Notruf-Richtlinien](manage-emergency-calling-policies.md)
- [Verwalten von Routingrichtlinien für Notrufe ](manage-emergency-call-routing-policies.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Zuweisen oder Ändern eines Notfallstandorts für Ihren Benutzer](assign-change-emergency-location-user.md)
- [Netzwerkeinstellungen für Cloud Voice-Features](cloud-voice-network-settings.md)
- [Verwalten Ihrer Netzwerktopologie für Cloud Voice-Features](manage-your-network-topology.md)