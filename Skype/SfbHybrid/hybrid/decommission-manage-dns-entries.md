---
title: Verwalten von DNS-Einträgen beim Außerbetriebnahme Ihrer lokalen Umgebung
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
description: Anweisungen zum Verwalten von DNS-Einträgen beim Außerbetriebnahme Ihrer lokalen Skype for Business Umgebung.
ms.openlocfilehash: c21a736c19ecec41ddc0458931675ca8ede34ed2
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671881"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>Aktualisieren von DNS-Einträgen, damit Ihre Organisation nur Teams ist

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Organisationen, die zuvor lokale Bereitstellungen von Skype for Business Server oder Lync Server hatten, verfügen möglicherweise weiterhin über DNS-Einträge, die auf eine lokale Skype for Business-Bereitstellung verweisen. Diese Datensätze sind erforderlich, wenn Ihre Organisation lokale Skype for Business Benutzer enthält. Sobald Ihre Organisation jedoch keine lokalen Skype for Business- oder Lync Server-Benutzer mehr hat, sind diese ursprünglichen Einträge für die lokale Bereitstellung nicht mehr erforderlich, und diese DNS-Einträge müssen aktualisiert werden, um im Rahmen ihrer Migration von der lokalen zu Teams Only auf **Microsoft 365 (oder in einigen Fällen entfernt) zu verweisen**. *Microsoft kann diese DNS-Einträge nicht in Ihrem Auftrag aktualisieren.*

Wenn Sie versuchen, TeamsOnly dem gesamten Mandanten zu gewähren, überprüft Teams DNS, um festzustellen, ob einer dieser unten aufgeführten DNS-Einträge in jeder Ihrer Microsoft 365 überprüften Domänen in Ihrer Organisation vorhanden ist. Wenn Datensätze gefunden werden und auf einen anderen Wert als Microsoft 365 verweisen, schlägt der Versuch, den Mandantenkoexistenzmodus in TeamsOnly zu ändern, standardmäßig fehl. Dadurch wird verhindert, dass Hybridorganisationen mit lokalen Benutzern fälschlicherweise den TeamsOnly-Modus auf den Mandanten anwenden, da dadurch der Partnerverbund für alle lokalen Skype for Business Benutzer in der Organisation (ob Teams oder Skype for Business) getrennt würde.

## <a name="how-to-identify-stale-dns-records"></a>Identifizieren veralteter DNS-Einträge

Um DNS-Einträge zu identifizieren, die verhindern, dass Ihre Organisation alle Teams werden, können Sie das Teams Admin Center verwenden, um den Koexistenzmodus in TeamsOnly zu ändern. Wechseln Sie zu **Teams** >  **Teams Upgradeeinstellungen**. Alle DNS-Einträge, die verhindern, dass die Organisation Teams Nur wird in die Fehlermeldung eingeschlossen.  Für den Fall, dass keine DNS-Einträge gefunden werden, wird der Koexistenzmodus für Ihre Organisation in TeamsOnly geändert.

Alternativ können Sie Teams PowerShell verwenden, um dasselbe zu tun, wie unten gezeigt:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
   ```

## <a name="dns-records-to-be-updated"></a>Zu aktualisierende DNS-Einträge

Wenn in Ihrer Organisation keine Benutzer mehr in lokalen Skype for Business Server oder Lync Server gehostet werden, müssen Sie die folgenden Schritte ausführen:

- Aktualisieren Sie die liste der Skype for Business DNS-Einträge unten so, dass sie auf Microsoft 365 (anstelle der lokalen Bereitstellung) verweist. Wenn Sie über mehr als eine SIP-Domäne verfügen, müssen Sie dies für jede SIP-Domäne tun, bei der es sich um eine Microsoft 365 überprüfte Domäne handelt.

- Entfernen Sie Skype for Business DNS-Einträge, wenn die SIP-Domäne nicht mehr verwendet wird.

Aktualisieren Sie diese in jeder Domäne, in der Sie einen der folgenden Einträge finden, wie folgt:

|Eintragstyp|Name|TTL|Priorität|Schriftbreite|Port|Wert|
|---|---|---|---|---|---|---|
|SRV|_sipfederationtls._tcp|3600|100|1|5061|sipfed.online.lync.com|
|SRV|_sip._tls|3600|100|1|443|sipdir.online.lync.com|
|CNAME|lyncdiscover|3600|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|webdir.online.lync.com|
|CNAME|sip|3600|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|sipdir.online.lync.com|

Darüber hinaus können CNAME-Einträge für Besprechung oder Einwahl (sofern vorhanden) gelöscht werden. Schließlich sollten alle DNS-Einträge für Skype for Business in Ihrem internen Netzwerk entfernt werden.

> [!NOTE]
> In seltenen Fällen kann das Ändern von DNS von der lokalen zu Microsoft 365 für Ihre Organisation dazu führen, dass der Verbund mit einigen anderen Organisationen nicht mehr funktioniert, bis diese andere Organisation ihre Verbundkonfiguration aktualisiert:
>
> - Alle Verbundorganisationen, die das ältere Direct Federation-Modell (auch als zugelassener Partnerserver bezeichnet) verwenden, müssen ihre zulässigen Domäneneinträge für ihre Organisation aktualisieren, um den Proxy-FQDN zu entfernen. Dieses Legacy-Verbundmodell basiert nicht auf DNS SRV-Einträgen, daher wird eine solche Konfiguration veraltet, sobald Ihre Organisation in die Cloud verschoben wird.
>
> - Jede Verbundorganisation, die keinen aktivierten Hostinganbieter für "sipfed.online.lync" hat.<span> com muss ihre Konfiguration aktualisieren, um dies zu aktivieren. Diese Situation ist nur möglich, wenn die Verbundorganisation rein lokal ist und nie mit einem Hybrid- oder Onlinemandanten verbunden wurde. In einem solchen Fall funktioniert der Verbund mit diesen Organisationen erst, wenn sie ihren Hostinganbieter aktivieren.
>
> Wenn Sie vermuten, dass einer Ihrer Verbundpartner den direkten Partnerverbund verwendet oder sich nicht mit einer Online- oder Hybridorganisation verbunden hat, empfehlen wir Ihnen, ihnen eine Mitteilung darüber zu senden, während Sie sich auf die Migration in die Cloud vorbereiten.
