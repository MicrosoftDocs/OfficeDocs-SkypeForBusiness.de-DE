---
title: Planen einer automatischen Cloud-Telefonzentrale
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Übersicht über die Verwendung einer automatischen Cloud-Telefonzentrale mit Skype for Business Server 2019
ms.openlocfilehash: 635d9c6548ba807153876d63ad228f69646e93c8
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2019
ms.locfileid: "36207030"
---
# <a name="plan-cloud-auto-attendants"></a>Planen automatischer Cloud-Telefonzentralen

Die mit Exchange Unified Messaging (Exchange Server 2013 oder Exchange Server 2016) verwendete automatische Telefonzentrale ist in Exchange Server 2019 oder Exchange Online nicht mehr verfügbar. Wenn Ihre Implementierung von Skype for Business Server 2019 in eine dieser Exchange-Versionen integriert ist, müssen Sie die Online-Cloud-VoIP-Funktionen verwenden, die mit dem Telefon System verbunden sind. Informationen zum Verschieben von Exchange um Diensten, die in Exchange Server 2013 und 2016 verwaltet werden, finden Sie unter [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md) in der Cloud.

Dies bedeutet inhärent, dass Sie eine hybride Implementierung von Skype for Business Server 2019 haben, wenn Sie Unified Messaging-Funktionen wie automatische Telefonzentralen verwenden möchten. Weitere Informationen finden Sie unter [Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Office 365](configure-hybrid-connectivity.md) .

Eine automatische Telefonzentrale ist ein clouddienst, der Kundenanrufe akzeptiert und Begrüßungen wiedergibt, Ihnen Menü Optionen zur Verfügung stellt und mit dem Anrufer unter Verwendung von Speech oder dialpad interagiert, um Ihre Anrufe an das richtige Ziel weiterzuleiten. Jeder automatischen Telefonzentrale wird ein **Ressourcenkonto** (siehe[Configure Resource Accounts](configure-onprem-ra.md)) auf Ihrem Skype for Business Server 2019-System zugewiesen, das direkt mit einer automatischen Telefonzentrale im Microsoft Teams Admin Center verknüpft wird. Weitere Informationen finden Sie unter [Was sind automatische Cloud-Telefonzentralen?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) weitere Details zu den automatischen Telefonzentralen und den verfügbaren Optionen und Funktionen für automatische Telefonzentralen.

> [!NOTE]
> Sie können einer automatischen Telefonzentrale mehrere Microsoft-Dienstnummern oder Hybrid Nummern zuweisen.

Ein eingehender Anruf bei einer automatischen Cloud-Telefonzentrale kann einen von mehreren Pfaden annehmen, wie hier gezeigt:

![Diagramm für automatische Telefonzentralen](../../SfBServer2019/media/AA-plan-concept.png)

1. Via Skype for Business Server 2019
2. Über einen [Session Border Controller](/MicrosoftTeams/direct-routing-border-controllers.md) und [Direktes Routing](/MicrosoftTeams/direct-routing-plan.md)
3. Über eine Nummer, die Online in Office 365 verwaltet wird.

Siehe auch:

- [Einrichten einer automatischen Cloud-Telefonzentrale](/microsoftteams/create-a-phone-system-auto-attendant)
- [Automatisches Beantworten und Weiterleiten eingehender Anrufe](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Voraussetzungen

Bei den folgenden Anforderungen wird vorausgesetzt, dass Sie bereits Skype for Business Server 2019 in einer unterstützten Topologie bereitgestellt haben.  Ihre Anforderungen hängen von Ihrem Szenario ab:

- Wenn Sie bereits Exchange um Online oder lokal verwenden und ein Upgrade auf Skype for Business 2019 durchführen, müssen Sie die Struktur ihrer automatischen Telefonzentralen erfassen und in der Cloud mithilfe von automatischen Cloud-Telefonzentralen neu erstellen. Weitere Informationen finden Sie unter [Verschieben einer Exchange um automatischen Telefonzentrale oder Anrufwarteschlange in das Telefon System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).

- Für eine neue Konfiguration von automatischen Cloud-Telefonzentralen führen Sie die unter [Configure Resource Accounts](configure-onprem-ra.md)beschriebenen Schritte aus.

Zusätzlich zu den oben aufgeführten Anforderungen müssen die folgenden Anforderungen so konfiguriert werden, dass eine Verbindung mit dem automatischen Microsoft Cloud-Telefonzentralen Dienst hergestellt wird:

- Hybrid Konnektivität. Wenn Sie bereits Skype for Business Server bereitgestellt haben und die automatische Cloud-Telefonzentrale für Ihre lokalen Benutzer aktivieren möchten, müssen Sie sicherstellen, dass Sie eine hybride Konnektivität zwischen Ihren lokalen und Online-Umgebungen eingerichtet haben. Dies wird manchmal als geteilte Domänenkonfiguration bezeichnet.

   Weitere Informationen finden Sie unter [Planen der Hybrid Konnektivität zwischen Skype for Business Server und Office 365](plan-hybrid-connectivity.md) und [Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Office 365](configure-hybrid-connectivity.md).

- Wenn Sie Ihrer automatischen Telefonzentrale eine Telefonnummer zuweisen, benötigen Sie eine [Office 365 Enterprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) -Lizenz.
- Erstellen Sie für jede automatische Telefonzentrale ein Online- [Ressourcenkonto](/MicrosoftTeams/manage-resource-accounts.md) oder ein lokales [Ressourcenkonto](configure-onprem-ra.md), und weisen Sie Telefonnummern und Lizenzen zu. 

## <a name="migration-and-interoperability"></a>Migration und Interoperabilität

Wenn Sie Skype for Business Server 2019 und/oder Exchange Server 2019 bereitstellen möchten, müssen Sie die Migration sorgfältig planen, um eine kontinuierliche Unterstützung für automatische Telefonzentralen sicherzustellen. Denken Sie dabei an Folgendes:

- Exchange Server 2019 bietet keine Exchange um Funktionalität mehr
- Exchange Unified Messaging befindet sich im Ruhestands Modus
- Skype for Business Server 2019 nicht mehr in Exchange Online um integriert

Automatische Cloud-Telefonzentralen können mit Skype for Business Server 2019, 2015 und 2013 konfiguriert werden.

Microsoft empfiehlt die folgenden Migrationspfade:

- Wenn Sie ein Upgrade auf Skype for Business Server 2019 durchführen, können Sie Exchange um in Exchange Server 2013 oder 2016 verwenden, aber Sie müssen ein Upgrade auf die automatische Cloud-Telefonzentrale durchführen, wenn Sie Exchange Server 2019 verwenden.

- Wenn Sie ein Upgrade auf Exchange Server 2019 durchführen und frühere Versionen von Exchange Server um für Skype for Business Server Sprachnachrichten verwenden, empfiehlt Microsoft, ein Upgrade auf Skype for Business Server 2019 vor dem Post Fach Upgrade durchführen.  Andernfalls geht die Sprachnachrichten Funktion verloren.

Weitere Informationen zum Planen der Migration finden Sie unter [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Migrieren einer zuvor implementierten Exchange um System für die automatische Telefonzentrale

Derzeit unterstützen wir keine automatisierte Migration in die Cloud eines in Exchange 2013 oder 2016 erstellten automatischen UM-Telefonzentralen Systems. Um manuell ein System für die automatische Telefonzentrale neu zu erstellen, müssen Sie Folgendes tun:

1. Verwenden Sie die Exchange-Verwaltungs-PowerShell-Befehle, um die Struktur des alten automatischen Telefonzentralen Systems zu überprüfen, einschließlich aller geschachtelten automatischen Telefonzentralen und Anrufwarteschlangen.  
2. Erstellen von Kopien von Text-zu-Sprache-Skripts oder aufgezeichneten Nachrichten, die den einzelnen um-Telefonzentralen-Knoten zugeordnet sind.
3. Erstellen Sie vor Ort-Endpunkte für jeden Knoten der automatischen Telefonzentrale, einschließlich Zuweisen eines Testtelefon Nummern und Lizenzen zu den Objekten. Beachten Sie, dass Sie jetzt die Möglichkeit haben, von Onlinediensten wie dem Telefon System verwendete Lizenzen für lokale Telefonnummern zuzuweisen.
4. Implementieren Sie einen neuen automatischen Cloud-Telefonzentralen Dienst mit Skype for Business Online und Telefon System. Informationen zur Implementierung finden Sie unter [Configure Resource Accounts](configure-onprem-ra.md) . Laden Sie dabei die Text-zu-Sprache-Skripts oder aufgezeichneten Nachrichten, die den einzelnen um-Telefonzentralen-Knoten zugeordnet sind, hoch.
5. Testen Sie die Funktionalität der automatischen Cloud-Telefonzentrale.
6. Weisen Sie der neu erstellten automatischen primären Cloud-Telefonzentrale erneut die Telefonnummer zu, die der alten Exchange um automatischen Telefonzentrale zugewiesen wurde.

Ausführliche Informationen zu diesen Schritten finden Sie unter [Verschieben einer Exchange um automatischen Telefonzentrale oder Anrufwarteschlange in das Telefon System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) .

## <a name="additional-planning-resources"></a>Zusätzliche Planungsressourcen

Das Lernprogramm mit dem Titel [Small Business Beispiel: Einrichten einer automatischen Telefonzentrale](/microsoftteams/tutorial-org-aa) durchläuft den Prozess der Erfassung von Informationen zu Benutzeranforderungen, der Planung einer Struktur von automatischen Telefonzentralen und Benutzern (und möglicherweise auch von Anrufwarteschlangen), dem Schreiben der Menüansagen und Implementieren des Plans im Teamadministrator Center. Lesen Sie das Lernprogramm, und verwenden Sie die Übungseinheiten, um Ihren Plan zu erstellen.

Wenn Sie über eine solide Struktur verfügen, die Ihren Anforderungen entspricht, und ein Skript, das Kunden effizient leitet, fahren Sie mit [Konfigurieren von Ressourcenkonten](configure-onprem-ra.md)fort.

> [!CAUTION]
> Wie in [KB4480742](https://support.microsoft.com/en-us/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)erwähnt, wird das Verschieben Exchange um in Server 2015 erstellten automatischen Telefonzentralen auf Server mit Server 2019 nicht empfohlen. Vorläufig müssen Sie Sie in einem Skype for Business Server 2015-Pool aufbewahren, der im Koexistenzmodus ausgeführt wird.

## <a name="see-also"></a>Siehe auch

[Planen der Migration von Skype for Business Server und Exchange Server](plan-um-migration.md)

[Konfigurieren von Ressourcenkonten](configure-onprem-ra.md)

[Aktivieren der Aufzeichnung benutzerdefinierter Ansagen über die Benutzerschnittstelle für Telefoneingaben](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Was sind automatische Cloud-Telefonzentralen?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Einrichten einer automatischen Cloud-Telefonzentrale](/microsoftteams/create-a-phone-system-auto-attendant)

Exchange um: [eingehende Anrufe automatisch beantworten und weiterleiten](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Planen der Hybriden Konnektivität zwischen Skype for Business Server und Office 365](plan-hybrid-connectivity.md)

[Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Office 365](configure-hybrid-connectivity.md)

[KB4480742: Anrufe beim Teilnehmerzugriff oder bei der automatischen Telefonzentrale schlagen fehl, wenn der Fehler "schnell beschäftigt" und "500 Server intern" nach dem Verschieben von Kontaktobjekten auf Skype for Business Server 2019 aufgetreten ist.](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
