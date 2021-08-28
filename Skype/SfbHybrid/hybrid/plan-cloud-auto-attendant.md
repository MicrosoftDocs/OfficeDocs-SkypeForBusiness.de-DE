---
title: Planen einer automatischen Cloudtelefonzentrale
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: Übersicht über die Verwendung einer automatischen Cloudtelefonzentrale mit Skype for Business Server 2019
ms.openlocfilehash: 5d28618efc2b02240cdfe3e4c05945f9a6e4b575
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610172"
---
# <a name="plan-cloud-auto-attendants"></a>Planen automatischer Cloud-Telefonzentralen

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Die automatische Telefonzentrale, die mit Exchange Unified Messaging (Exchange Server 2013 oder Exchange Server 2016) verwendet wird, ist in Exchange Server 2019 oder Exchange Online nicht mehr verfügbar. Wenn Ihre Implementierung von Skype for Business Server 2019 in eine dieser Exchange Versionen integriert ist, müssen Sie die Online-Cloud voice-Features verwenden, die Telefonsystem zugeordnet sind. Informationen zum Verschieben Exchange UM-Dienste, die auf Exchange Server 2013 und 2016 verwaltet werden, finden Sie unter ["Planen](plan-um-migration.md) der Skype for Business Server und Exchange Server Migration".

Dies bedeutet inhärent, dass Sie über eine hybride Implementierung von Skype for Business Server 2019 verfügen, wenn Sie Unified Messaging-Features wie automatische Telefonzentralen verwenden möchten. Weitere Informationen finden Sie unter Konfigurieren der [Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365.](configure-hybrid-connectivity.md)

Eine automatische Telefonzentrale ist ein Clouddienst, der Kundenanrufe akzeptiert und Begrüßungen abgibt, ihnen Menüoptionen bereitstellt und mit Anrufern per Sprache oder der Wähltastatur interagiert, um ihre Anrufe an das richtige Ziel weiterzuleiten. Jeder automatischen Telefonzentrale wird ein *Ressourcenkonto* (siehe ["Ressourcenkonten konfigurieren")](configure-onprem-ra.md)auf Ihrem Skype for Business Server 2019-System zugewiesen, das direkt mit einer automatischen Telefonzentrale im Microsoft Teams Admin Center verknüpft wird. Weitere Informationen dazu, was automatische [Telefonzentralen](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) sind und welche Optionen und Features für automatische Telefonzentralen vorhanden sind, finden Sie unter "Was sind automatische Cloudtelefonzentralen".

> [!NOTE]
> Sie können einer automatischen Telefonzentrale mehrere Microsoft-Dienstnummern, Direct Routing-Nummern oder Hybridnummern zuweisen.

Ein eingehender Anruf bei einer automatischen Cloudtelefonzentrale kann einen von mehreren Pfaden annehmen, wie hier gezeigt:

![Diagramm für automatische Telefonzentralen](../../SfBServer2019/media/AA-plan-concept.png)

1. Über Skype for Business Server 2019
2. Über einen [Session Border Controller](/MicrosoftTeams/direct-routing-border-controllers.md) und Direct [Routing](/MicrosoftTeams/direct-routing-plan.md)
3. Über eine Onlinenummer in Microsoft 365 oder Office 365.

Siehe auch:

- [Einrichten einer automatischen Cloudtelefonzentrale](/microsoftteams/create-a-phone-system-auto-attendant)
- [Automatisches Beantworten und Weiterleiten eingehender Anrufe](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Anforderungen

Bei den folgenden Anforderungen wird davon ausgegangen, dass Sie bereits Skype for Business Server 2019 in einer unterstützten Topologie bereitgestellt haben.  Ihre Anforderungen hängen von Ihrem Szenario ab:

- Wenn Sie bereits Exchange ONLINE oder lokal verwenden und auf Skype for Business 2019 aktualisieren, müssen Sie die Struktur Ihrer automatischen Telefonzentralen erfassen und sie mithilfe automatischer Cloudtelefonzentralen in der Cloud neu erstellen. Weitere Informationen finden Sie unter [Verschieben einer Exchange automatischen UM-Telefonzentrale oder Anrufwarteschleife in Telefonsystem.](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)

- Führen Sie für eine neue Konfiguration der automatischen Cloudtelefonzentralen die unter  [Konfigurieren von Ressourcenkonten](configure-onprem-ra.md)beschriebenen Schritte aus.

Zusätzlich zu den oben genannten Anforderungen müssen die folgenden Anforderungen so konfiguriert werden, dass eine Verbindung mit dem automatischen Telefonzentralendienst von Microsoft Cloud hergestellt wird:

- Hybridkonnektivität. Wenn Sie bereits Skype for Business Server bereitgestellt haben und die automatische Cloudtelefonzentrale für Ihre lokalen Benutzer aktivieren möchten, müssen Sie sicherstellen, dass die Hybridkonnektivität zwischen Ihrer lokalen und Onlineumgebung eingerichtet ist. Dies wird manchmal als Konfiguration für geteilte Domänen bezeichnet.

   Weitere Informationen finden Sie unter Planen der [Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](plan-hybrid-connectivity.md) und Konfigurieren der [Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365.](configure-hybrid-connectivity.md)

- Wenn Sie Ihrer automatischen Telefonzentrale eine Telefonnummer zuweisen, benötigen Sie eine [Office 365 Enterprise E5-Lizenz.](../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing.md)
- Erstellen Sie ein [Onlineressourcenkonto](/MicrosoftTeams/manage-resource-accounts.md) oder ein lokales [Ressourcenkonto](configure-onprem-ra.md) für jede automatische Telefonzentrale, und weisen Sie Telefonnummern und Lizenzen zu. 

## <a name="migration-and-interoperability"></a>Migration und Interoperabilität

Wenn Sie planen, Skype for Business Server 2019 und/oder Exchange Server 2019 bereitzustellen, müssen Sie die Migration sorgfältig planen, um die fortlaufende Unterstützung für automatische Telefonzentralen sicherzustellen. Denken Sie dabei an Folgendes:

- Exchange Server 2019 bietet keine Exchange UM-Funktionalität mehr
- Exchange Unified Messaging befindet sich im Einstellungsmodus
- Skype for Business Server 2019 wird nicht mehr in Exchange Online UM integriert

Automatische Cloudtelefonzentralen können mit Skype for Business Server 2019, 2015 und 2013 konfiguriert werden.

Microsoft empfiehlt die folgenden Migrationspfade:

- Wenn Sie ein Upgrade auf Skype for Business Server 2019 durchführen, können Sie Exchange UM in Exchange Server 2013 oder 2016 verwenden, aber Sie müssen ein Upgrade auf die automatische Cloudtelefonzentrale durchführen, wenn Sie Exchange Server 2019 verwenden.

- Wenn Sie ein Upgrade auf Exchange Server 2019 durchführen und frühere Versionen von Exchange Server UM für Skype for Business Server Voice messaging verwenden, empfiehlt Microsoft, vor dem Postfachupgrade auf Skype for Business Server 2019 zu aktualisieren.  Andernfalls geht die Sprachnachrichtenfunktion verloren.

Weitere Informationen zum Planen der Migration finden Sie unter [Planen der Skype for Business Server und Exchange Server Migration.](plan-um-migration.md)

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Migrieren eines zuvor implementierten Exchange automatischen UM-Telefonzentralensystems

Derzeit unterstützen wir keine automatisierte Migration in die Cloud eines automatischen UM-Telefonzentralensystems, das in Exchange 2013 oder 2016 erstellt wurde. Um ein automatisches Telefonzentralensystem manuell neu zu erstellen, müssen Sie Folgendes tun:

1. Verwenden Sie Exchange PowerShell-Administratorbefehle, um die Struktur des alten automatischen Telefonzentralensystems zu überprüfen, einschließlich geschachtelter automatischer Telefonzentralen und Anrufwarteschleifen.  
2. Erstellen Sie Kopien von Text-zu-Sprache-Skripts oder aufgezeichneten Nachrichten, die jedem Knoten der automatischen UM-Telefonzentrale zugeordnet sind.
3. Erstellen Sie lokale Endpunkte für jeden Knoten der automatischen Telefonzentrale, einschließlich der Zuweisung von Testtelefonnummern und Lizenzen zu den Objekten. Beachten Sie, dass Sie jetzt die Möglichkeit haben, lokale Telefonnummernlizenzen zuzuweisen, die von Onlinediensten wie Telefonsystem verwendet werden.
4. Implementieren Sie einen neuen automatischen Cloudtelefonzentralendienst mit Microsoft Teams und Telefonsystem. Details zur Implementierung finden Sie unter [Konfigurieren von Ressourcenkonten.](configure-onprem-ra.md) Laden Sie dabei die Text-zu-Sprache-Skripts oder aufgezeichneten Nachrichten hoch, die jedem Knoten der automatischen UM-Telefonzentrale zugeordnet sind.
5. Testen Sie die Funktionalität der automatischen Cloudtelefonzentrale.
6. Weisen Sie die Telefonnummer, die der alten Exchange automatischen UM-Telefonzentrale zugewiesen wurde, der neu erstellten automatischen Haupttelefonzentrale für die Cloud zu.

Weitere Informationen zu diesen Schritten finden Sie unter [Verschieben einer automatischen UM-Telefonzentrale oder Anrufwarteschleife für Exchange um Telefonsystem.](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)

Wenn Sie über eine solide Struktur verfügen, die Ihren Anforderungen entspricht, und ein Skript, das Kunden effizient führt, fahren Sie mit [dem Konfigurieren von Ressourcenkonten](configure-onprem-ra.md)fort.

> [!CAUTION]
> Wie in [KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)erwähnt, wird davon abgeraten, Exchange in Server 2015 erstellten automatischen UM-Telefonzentralen auf Server mit Server 2019 zu verschieben. Sie müssten sich vorerst in einem Skype for Business Server 2015-Pool befinden, der im Koexistenzmodus ausgeführt wird.

## <a name="see-also"></a>Siehe auch

[Planen der Migration von Skype for Business Server und Exchange Server](plan-um-migration.md)

[Konfigurieren von Ressourcenkonten](configure-onprem-ra.md)

[Aktivieren der Aufzeichnung benutzerdefinierter Ansagen über die Benutzerschnittstelle für Telefoneingaben](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Was sind automatische Cloudtelefonzentralen?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Einrichten einer automatischen Cloudtelefonzentrale](/microsoftteams/create-a-phone-system-auto-attendant)

Exchange UM: [Automatisches Beantworten und Weiterleiten eingehender Anrufe](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Planen der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](plan-hybrid-connectivity.md)

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](configure-hybrid-connectivity.md)

[KB4480742: Anrufe beim Abonnentenzugriff oder bei der automatischen Telefonzentrale schlagen mit schnell ausgelasteten und "500 Server Internal"-Fehlern fehl, nachdem Kontaktobjekte in Skype for Business Server 2019 verschoben wurden.](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)