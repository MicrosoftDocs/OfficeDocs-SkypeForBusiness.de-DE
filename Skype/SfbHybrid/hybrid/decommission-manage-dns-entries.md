---
title: Verwalten von DNS-Einträgen bei der Außerbetriebnahme Ihrer lokalen Umgebung
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Anweisungen zum Verwalten von DNS-Einträgen bei der Außerbetriebnahme Ihrer lokalen Skype for Business Umgebung.
ms.openlocfilehash: a69b99f8adf5cf520f08ebef5f08de82426d5723
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636781"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>Aktualisieren von DNS-Einträgen, damit Ihre Organisation nur Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Organisationen, die zuvor lokale Bereitstellungen von Skype for Business Server oder Lync Server ausgeführt haben, verfügen möglicherweise immer noch über DNS-Einträge, die auf eine lokale Skype for Business Bereitstellung verweisen. Diese Datensätze sind erforderlich, wenn Ihre Organisation lokale Skype for Business Benutzer enthält. Sobald Ihre Organisation jedoch keine lokalen Skype for Business- oder Lync Server-Benutzer mehr hat, sind diese ursprünglichen Einträge für die lokale Bereitstellung nicht mehr erforderlich, und **diese DNS-Einträge müssen aktualisiert werden, um auf Microsoft 365 (oder in einigen Fällen entfernt)** im Rahmen der Migration von der lokalen Bereitstellung zu Teams Only zu verweisen. *Microsoft kann diese DNS-Einträge nicht in Ihrem Auftrag aktualisieren.*

Wenn sie versuchen, TeamsOnly dem gesamten Mandanten zu gewähren, überprüft Teams DNS, um festzustellen, ob einer der unten aufgeführten DNS-Einträge in jeder Ihrer Microsoft 365 überprüften Domänen in Ihrer Organisation vorhanden ist. Wenn Datensätze gefunden werden und auf einen anderen Wert als Microsoft 365 verweisen, schlägt der Versuch, den Mandanten-Koexistenzmodus in TeamsOnly zu ändern, entwurfsbedingt fehl. Dadurch wird verhindert, dass Hybridorganisationen mit lokalen Benutzern versehentlich den TeamsOnly-Modus auf den Mandanten anwenden, da dadurch der Partnerverbund für alle lokalen Skype for Business Benutzer in der Organisation (unabhängig davon, ob Teams oder Skype for Business verwendet wird) aufgehoben würde.


## <a name="how-to-identify-stale-dns-records"></a>So identifizieren Sie veraltete DNS-Einträge

Um DNS-Einträge zu identifizieren, die verhindern, dass Ihre Organisation alle Teams ist, können Sie das Teams Admin Center verwenden, um den Koexistenzmodus in TeamsOnly zu ändern. Wechseln Sie zur **organisationsweiten Einstellung**  ->  **Teams Upgrade.** Alle DNS-Einträge, die verhindern, dass die Organisation zu Teams Only wird in die Fehlermeldung eingeschlossen.  Falls keine DNS-Einträge gefunden werden, wird der Koexistenzmodus für Ihre Organisation in TeamsOnly geändert.   

Alternativ können Sie Teams PowerShell verwenden, um dasselbe zu tun, wie unten gezeigt:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
   ```

## <a name="dns-records-to-be-updated"></a>DNS-Einträge, die aktualisiert werden sollen

Wenn in Ihrer Organisation keine Benutzer mehr in lokalen Skype for Business Server oder Lync Server gehostet werden, müssen Sie folgendermaßen vorgehen:

- Aktualisieren Sie die liste der Skype for Business DNS-Einträge unten so, dass sie auf Microsoft 365 zeigt (anstelle der lokalen Bereitstellung). Wenn Sie über mehrere SIP-Domänen verfügen, müssen Sie dies für jede SIP-Domäne tun, bei der es sich um eine Microsoft 365 überprüfte Domäne handelt.

- Entfernen Sie Skype for Business DNS-Einträge, wenn die SIP-Domäne nicht mehr verwendet wird. 

Aktualisieren Sie sie in jeder Domäne, in der Sie einen der folgenden Datensätze finden, wie folgt:

| Eintragstyp | Name | TTL | Priorität | Schriftbreite | Port | Wert |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| SRV | _sipfederationtls.tcp | 3600 |  100 | 1  | 5061  | sipfed.online.lync.com |
| SRV | _sip.tls | 3600  | 100 |    1    | 443   | sipdir.online.lync.com |
| CNAME | lyncdiscover |    3600 |  Nicht zutreffend |   Nicht zutreffend |   Nicht zutreffend |   webdir.online.lync.com |
| CNAME |   sip | 3600 |    Nicht zutreffend |   Nicht zutreffend  | Nicht zutreffend |    sipdir.online.lync.com |
|||||||

Darüber hinaus können CNAME-Einträge für Meet- oder Dialin-Einträge (sofern vorhanden) gelöscht werden. Schließlich sollten alle DNS-Einträge für Skype for Business in Ihrem internen Netzwerk entfernt werden.

> [!Note] 
> In seltenen Fällen kann das Ändern von DNS von der Lokalen auf Microsoft 365 für Ihre Organisation dazu führen, dass der Partnerverbund mit einigen anderen Organisationen nicht mehr funktioniert, bis diese andere Organisation ihre Verbundkonfiguration aktualisiert:
>
> - Alle Verbundorganisationen, die das ältere Direct Federation-Modell (auch als zulässiger Partnerserver bezeichnet) verwenden, müssen ihre zulässigen Domäneneinträge für ihre Organisation aktualisieren, um den Proxy-FQDN zu entfernen. Dieses Legacyverbundmodell basiert nicht auf DNS-SRV-Einträgen, sodass eine solche Konfiguration veraltet ist, sobald Ihre Organisation in die Cloud verschoben wird.
> 
> - Eine Partnerorganisation, die über keinen aktivierten Hostinganbieter für "sipfed.online.lync" verfügt. <span> com muss die Konfiguration aktualisieren, um dies zu aktivieren. Diese Situation ist nur möglich, wenn die Verbundorganisation ausschließlich lokal ist und nie mit einem Hybrid- oder Onlinemandanten verbunden ist. In einem solchen Fall funktioniert der Partnerverbund mit diesen Organisationen erst, wenn sie ihren Hostinganbieter aktivieren.
>
> Wenn Sie vermuten, dass einer Ihrer Verbundpartner möglicherweise einen direkten Partnerverbund verwendet oder nicht mit einer Online- oder Hybridorganisation verbunden ist, empfehlen wir Ihnen, ihnen eine Entsprechende-Kommunikation zu senden, während Sie sich auf die Durchführung Der Migration in die Cloud vorbereiten.
  




