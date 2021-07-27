---
title: Hybrid deaktivieren, um die Migration nur zu Teams durchzuführen
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Dieser Artikel enthält ausführliche Schritte zum Deaktivieren der Hybridbereitstellung im Rahmen der Cloudkonsolidierung für Teams und Skype for Business.
ms.openlocfilehash: 90f3b6d5cd533ca92966a46dd271d2f82f40acc4
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510506"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a>Deaktivieren Sie die Hybridkonfiguration, um die Migration zu Teams abzuschließen. 

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


In diesem Artikel wird beschrieben, wie Sie Ihre Hybridkonfiguration vor der Außerbetriebnahme Ihrer lokalen Skype for Business umgebung deaktivieren. Dies ist Schritt 2 der folgenden Schritte zum Außerbetriebsetzen Ihrer lokalen Umgebung:

- Schritt 1. [Verschieben Sie alle erforderlichen Benutzer aus der lokalen Umgebung in die Onlineumgebung.](decommission-move-on-prem-users.md)

- **Schritt 2. Deaktivieren Sie die Hybridkonfiguration.** (Dieser Artikel)

- Schritt 3: [Migrieren Sie Hybridanwendungsendpunkte von lokalen zu online.](decommission-move-on-prem-endpoints.md)

- Schritt 4. [Entfernen Sie Ihre lokale Skype for Business Bereitstellung.](decommission-remove-on-prem.md)

> [!NOTE]
> Die Schritte 2 und 3 sollten im gleichen Wartungsfenster ausgeführt werden, da vorhandene Hybridanwendungsendpunkte zwischen Schritt 2 und Abschluss von Schritt 3 nicht gefunden werden können.


## <a name="summary"></a>Zusammenfassung

Nachdem Sie alle Benutzer von Skype for Business lokal auf Teams Nur in Microsoft 365 aktualisiert haben, können Sie die lokale Skype for Business Bereitstellung außer Betrieb gesetzt haben.

Bevor Sie die lokale Skype for Business Bereitstellung außer Betrieb genommen und Hardware entfernt haben, müssen Sie die lokale Bereitstellung logisch von Microsoft 365 trennen, indem Sie die Hybridbereitstellung deaktivieren. Das Deaktivieren der Hybridbereitstellung besteht aus den folgenden vier Schritten:

1. [Aktualisieren Sie DNS-Einträge so, dass sie auf Microsoft 365 verweisen.](#update-dns-to-point-to-microsoft-365)

2. [Ändern Sie den Koexistenzmodus für Ihre Organisation in Teams Only](#change-the-coexistence-mode-for-your-organization-to-teams-only).

3. [Deaktivieren Sie den freigegebenen SIP-Adressraum (auch als "geteilte Domäne" bezeichnet) in der Microsoft 365 Organisation.](#disable-shared-sip-address-space-in-microsoft-365-organization)

4. [Kommunikation zwischen lokalen und Microsoft 365 deaktivieren](#disable-communication-between-on-premises-and-microsoft-365)

Diese Schritte trennen ihre lokale Bereitstellung von Skype for Business Server logisch von Microsoft 365 und stellen sicher, dass Ihre Organisation vollständig Teams ist. Nachdem Sie diese Schritte abgeschlossen haben, können Sie Ihre lokale Skype for Business Bereitstellung außer Betrieb nehmen, indem Sie eine von zwei Methoden verwenden, auf die in ["Entscheiden, wie Attribute nach der Außerbetriebnahme verwaltet](cloud-consolidation-managing-attributes.md)werden sollen" verwiesen wird.

> [!Important] 
> Sobald diese logische Trennung abgeschlossen ist, weisen msRTCSIP-Attribute aus Ihrem lokalen Active Directory weiterhin Werte auf und werden weiterhin über Azure AD Verbinden mit Azure AD synchronisiert. Wie Sie die lokale Umgebung außer Betrieb nehmen, hängt davon ab, ob Sie diese Attribute beibehalten oder zuerst aus Ihrem lokalen Active Directory löschen möchten. Beachten Sie, dass das Löschen der lokalen msRTCSIP-Attribute nach der Migration von der lokalen Bereitstellung zu einem Dienstverlust für Benutzer führen kann! Details und Nachteile der beiden Außerbetriebnahmeansätze werden unter ["Entscheiden, wie Attribute nach der Außerbetriebnahme verwaltet](cloud-consolidation-managing-attributes.md)werden" beschrieben.

## <a name="update-dns-to-point-to-microsoft-365"></a>Aktualisieren von DNS, um auf Microsoft 365 zu verweisen

Das externe DNS der Organisation für die lokale Organisation muss aktualisiert werden, damit Skype for Business Einträge auf Microsoft 365 anstatt auf die lokale Bereitstellung verweisen. 

Darüber hinaus können CNAME-Einträge für Meet- oder Dialin-Einträge (sofern vorhanden) gelöscht werden. Schließlich sollten alle DNS-Einträge für Skype for Business in Ihrem internen Netzwerk entfernt werden.

Ausführliche Informationen zum Aktualisieren von DNS-Einträgen finden Sie unter Aktualisieren von [DNS-Einträgen, damit Ihre Organisation nur Teams sein kann.](decommission-manage-dns-entries.md)

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a>Ändern des Koexistenzmodus für Ihre Organisation in Teams Only

Mit diesem Schritt wird sichergestellt, dass jeder neue Benutzer in Ihrer Organisation immer als Teams Einziger Benutzer erstellt wird. 

Wenn Sie versuchen, den Mandantenmodus in Teams Only zu ändern, wird automatisch überprüft, ob lokale DNS-Einträge vorhanden sind, die möglicherweise in Schritt 1 übersehen wurden, und diese Einträge in der Ausgabe identifiziert. Das Ändern des Mandantenmodus in Teams Nur ist erst erfolgreich, wenn alle DNS-Einträge für Ihre Organisation aktualisiert wurden. 

Um den Mandantenmodus in Teams Führen Sie nur den folgenden Befehl aus einem Teams PowerShell-Fenster aus.

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

Alternativ können Sie das Teams Admin Center verwenden, um den Mandanten-Koexistenzmodus in TeamsOnly zu ändern, unter "Organisationsweite Einstellungen" > "Teams Upgrade".    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a>Deaktivieren des freigegebenen SIP-Adressraums in Microsoft 365 Organisation
    
Um den freigegebenen SIP-Adressraum zu deaktivieren, führen Sie den folgenden Befehl in einem Teams PowerShell-Fenster aus.

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a>Kommunikation zwischen lokalen und Microsoft 365 deaktivieren

Um die Kommunikation zwischen der lokalen Umgebung und Microsoft 365 zu deaktivieren, führen Sie den folgenden Befehl in einem lokalen PowerShell-Fenster aus:

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a>Mehr dazu

- [Cloudkonsolidierung für Teams und Skype for Business](cloud-consolidation.md)

- [Außerbetriebnahme Ihrer lokalen Skype for Business-Umgebung](decommission-on-prem-overview.md)

