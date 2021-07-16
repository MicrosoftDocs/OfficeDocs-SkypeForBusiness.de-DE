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
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Anweisungen zum Verwalten von DNS-Einträgen bei der Außerbetriebnahme Ihrer lokalen Skype for Business Umgebung.
ms.openlocfilehash: bd8f3873ab28ef8e0b7ade86ffc95b4d5bb4e4cb
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458998"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>Aktualisieren von DNS-Einträgen, damit Ihre Organisation nur Teams werden kann

Organisationen, die zuvor lokale Bereitstellungen von Skype for Business Server oder Lync Server ausgeführt haben, verfügen möglicherweise weiterhin über DNS-Einträge, die auf eine lokale Skype for Business Bereitstellung verweisen. Diese Datensätze sind erforderlich, wenn Ihre Organisation lokale Skype for Business Benutzer enthält. Sobald Ihre Organisation jedoch keine lokalen Skype for Business oder Lync Server-Benutzer mehr hat, sind diese Datensätze nicht mehr erforderlich. Im Rahmen der Migration von der lokalen zu Teams müssen diese Datensätze aktualisiert werden, um auf Microsoft 365 oder entfernt zu verweisen. Microsoft kann diesen Schritt nicht für Sie ausführen.

Wenn sie versuchen, TeamsOnly dem gesamten Mandanten zu gewähren, überprüft Teams DNS, um festzustellen, ob einer dieser DNS-Einträge für Ihre Organisation vorhanden ist. Wenn Datensätze gefunden werden und auf einen anderen Wert als Microsoft 365 verweisen, schlägt der Versuch fehl, den Mandanten-Koexistenzmodus in TeamsOnly zu ändern. Mit diesem Entwurf soll verhindert werden, dass Hybridorganisationen mit lokalen Benutzern versehentlich den TeamsOnly-Modus auf den Mandanten anwenden, da dadurch der Partnerverbund für alle lokalen Skype for Business Benutzer aufgehoben würde (unabhängig davon, ob Teams oder Skype for Business verwendet wird).

Darüber hinaus müssen diese Datensätze aktualisiert werden, damit Sie TeamsOnly für den gesamten Mandanten gewähren können.

> [!Note] 
> In seltenen Fällen kann das Ändern von DNS von der Lokalen auf Microsoft 365 für Ihre Organisation dazu führen, dass der Partnerverbund mit einigen anderen Organisationen nicht mehr funktioniert, bis diese andere Organisation ihre Verbundkonfiguration aktualisiert:
>
> - Alle Verbundorganisationen, die das ältere Direct Federation-Modell (auch als zulässiger Partnerserver bezeichnet) verwenden, müssen ihre zulässigen Domäneneinträge für ihre Organisation aktualisieren, um den Proxy-FQDN zu entfernen. Dieses Legacyverbundmodell basiert nicht auf DNS-SRV-Einträgen, sodass eine solche Konfiguration veraltet ist, sobald Ihre Organisation in die Cloud verschoben wird.
> 
> - Eine Partnerorganisation, die über keinen aktivierten Hostinganbieter für "sipfed.online.lync" verfügt. <span> com muss die Konfiguration aktualisieren, um dies zu aktivieren. Diese Situation ist nur möglich, wenn die Verbundorganisation ausschließlich lokal ist und noch nie mit einem Hybrid- oder Onlinemandanten verbunden ist. In einem solchen Fall funktioniert der Partnerverbund mit diesen Organisationen erst, wenn sie ihren Hostinganbieter aktivieren.
>
> Wenn Sie vermuten, dass einer Ihrer Verbundpartner möglicherweise einen direkten Partnerverbund verwendet oder nicht mit einer Online- oder Hybridorganisation verbunden ist, empfehlen wir Ihnen, ihnen eine Entsprechende-Kommunikation zu senden, während Sie sich auf die Durchführung Der Migration in die Cloud vorbereiten.

## <a name="how-to-identify-stale-dns-records"></a>So identifizieren Sie veraltete DNS-Einträge

Um DNS-Einträge zu identifizieren, die verhindern, dass Ihre Organisation nur Teams wird, können Sie das Teams Admin Center verwenden, um den Koexistenzmodus in TeamsOnly zu ändern. Wechseln Sie zur **organisationsweiten Einstellung**  ->  **Teams Upgrade.** Alle DNS-Einträge, die verhindern, dass die Organisation zu Teams Only wird in die Fehlermeldung eingeschlossen.  Falls keine DNS-Einträge gefunden werden, wird der Koexistenzmodus für Ihre Organisation in TeamsOnly geändert. 

## <a name="how-to-remove-stale-dns-records"></a>Entfernen veralteter DNS-Einträge

Wenn Ihre Organisation keine lokalen Skype for Business Server oder Lync Server-Benutzer mehr hat, müssen Sie folgendermaßen vorgehen:

- Aktualisieren Sie Skype for Business DNS-Einträge so, dass sie auf Microsoft 365 verweisen (anstelle der lokalen Bereitstellung).

- Entfernen Sie Skype for Business DNS-Einträge, wenn die SIP-Domäne nicht mehr verwendet wird. 

Aktualisieren Sie sie in jeder Domäne, in der Sie einen der folgenden Datensätze finden, wie folgt:

| Eintragstyp | Name | TTL | Priorität | Schriftbreite | Port | Wert |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| SRV | _sipfederationtls.tcp | 3600 |  100 | 1 | 5061  | sipfed.online.lync.com |
| SRV | _sip.tls | 3600  | 100 |    1   | 443   | sipdir.online.lync.com |
| CNAME | lyncdiscover |    3600 |  Nicht zutreffend |   Nicht zutreffend |   Nicht zutreffend |   webdir.online.lync.com |
| CNAME |   sip | 3600 |    Nicht zutreffend |   Nicht zutreffend  | Nicht zutreffend |    sipdir.online.lync.com |
|||||||




