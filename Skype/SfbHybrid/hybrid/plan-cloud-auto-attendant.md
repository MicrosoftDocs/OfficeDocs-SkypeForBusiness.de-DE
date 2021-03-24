---
title: Planen einer automatischen Cloud-Attendant
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Übersicht über die Verwendung einer automatischen Cloud-Telefonwarte mit Skype for Business Server 2019
ms.openlocfilehash: b144576b3e572137a512881f4bdcd1ab0e06d0ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110351"
---
# <a name="plan-cloud-auto-attendants"></a>Planen automatischer Cloud-Telefonzentralen

Die automatische Attendant, die mit Exchange Unified Messaging (Exchange Server 2013 oder Exchange Server 2016) verwendet wird, ist in Exchange Server 2019 oder Exchange Online nicht mehr verfügbar. Wenn Ihre Implementierung von Skype for Business Server 2019 in eine dieser Exchange-Versionen integriert ist, müssen Sie die Online-Cloud-Voice-Features verwenden, die dem Telefonsystem zugeordnet sind. Informationen zum Verschieben von Exchange UM-Diensten, die auf Exchange Server 2013 und 2016 in die Cloud gespeichert sind, finden Sie unter [Plan for Skype for Business Server and Exchange Server](plan-um-migration.md) migration.

Dies bedeutet inhärent, dass Sie über eine Hybridimplementierung von Skype for Business Server 2019 verfügen, wenn Sie Unified Messaging-Features wie automatische Telefonanten verwenden möchten. Weitere Informationen finden Sie [unter Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365.](configure-hybrid-connectivity.md)

Eine automatische Telefon attendant ist ein Clouddienst, der Kundenanrufe akzeptiert und Begrüßungen abnimmt, ihnen Menüoptionen zur Verfügung stellt und mit Anrufern interagiert, die Sprache oder die Wählpad verwenden, um ihre Anrufe an das richtige Ziel weiterzurouten. Jeder automatischen Telefonzentrale wird ein Ressourcenkonto *(siehe* [Konfigurieren](configure-onprem-ra.md)von Ressourcenkonten ) auf Ihrem Skype for Business Server 2019-System zugewiesen, das direkt mit einer automatischen Telefonzentrale im Microsoft Teams Admin Center verknüpft wird. Weitere [Informationen dazu,](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) was automatische Attendants sind und welche Optionen und Features für automatische Attendants vorhanden sind, finden Sie unter Was sind automatische Cloud-Attendanten?

> [!NOTE]
> Sie können einer automatischen Attendant mehrere Microsoft-Dienstnummern, Direkte Routingnummern oder Hybridnummern zuweisen.

Ein eingehender Anruf bei einer automatischen Cloud-Telefonkonferenz kann einen von mehreren Pfaden verwenden, wie hier gezeigt:

![Diagramm für automatische Attendanten](../../SfBServer2019/media/AA-plan-concept.png)

1. Über Skype for Business Server 2019
2. Über einen [Session Border Controller und](/MicrosoftTeams/direct-routing-border-controllers.md) [direktes Routing](/MicrosoftTeams/direct-routing-plan.md)
3. Über eine Onlinenummer in Microsoft 365 oder Office 365.

Siehe auch:

- [Einrichten einer automatischen Cloudtelefonzentrale](/microsoftteams/create-a-phone-system-auto-attendant)
- [Automatisches Beantworten und Weiterleiten eingehender Anrufe](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Anforderungen

Bei den folgenden Anforderungen wird davon ausgegangen, dass Skype for Business Server 2019 bereits in einer unterstützten Topologie bereitgestellt ist.  Ihre Anforderungen hängen von Ihrem Szenario ab:

- Wenn Sie Exchange UM bereits online oder lokal verwenden und ein Upgrade auf Skype for Business 2019 durchführen, müssen Sie die Struktur Ihrer automatischen Telefonanten erfassen und mithilfe automatischer Cloud-Telefonanten in der Cloud neu erstellen. Weitere Informationen finden Sie unter Verschieben einer automatischen Exchange UM-Telefonanlage oder Anrufwarteschlange [in das Telefonsystem](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).

- Führen Sie für eine neue Konfiguration der automatischen Cloud-Attendanten die unter [Configure resource accounts beschriebenen Schritte aus.](configure-onprem-ra.md)

Zusätzlich zu den oben genannten Anforderungen müssen die folgenden Anforderungen für die Verbindung mit dem automatischen Microsoft Cloud-Attendant-Dienst konfiguriert werden:

- Hybridkonnektivität. Wenn Sie Skype for Business Server bereits bereitgestellt haben und die automatische Cloud-Telefonwarte für Ihre lokalen Benutzer aktivieren möchten, müssen Sie sicherstellen, dass zwischen Ihren lokalen und Onlineumgebungen hybride Konnektivität eingerichtet ist. Dies wird manchmal als geteilte Domänenkonfiguration bezeichnet.

   Weitere Informationen finden Sie unter [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) und [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).

- Wenn Sie Ihrer automatischen Telefonwarte eine Telefonnummer zuweisen, benötigen Sie eine [Office 365 Enterprise E5-Lizenz.](../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing.md)
- Erstellen Sie ein [Onlineressourcenkonto](/MicrosoftTeams/manage-resource-accounts.md) oder ein lokales [Ressourcenkonto](configure-onprem-ra.md) für jede automatische Telefon attendant, und weisen Sie Telefonnummern und Lizenzen zu. 

## <a name="migration-and-interoperability"></a>Migration und Interoperabilität

Wenn Sie Planen der Bereitstellung von Skype for Business Server 2019 und/oder Exchange Server 2019, müssen Sie Ihre Migration sorgfältig planen, um sicherzustellen, dass automatische Telefonanten weiterhin unterstützt werden. Denken Sie dabei an Folgendes:

- Exchange Server 2019 bietet keine Exchange UM-Funktionen mehr
- Exchange Unified Messaging befindet sich im Ruhezustand
- Skype for Business Server 2019 ist nicht mehr in Exchange Online UM integriert

Automatische Cloud-Telefone können mit Skype for Business Server 2019, 2015 und 2013 konfiguriert werden.

Microsoft empfiehlt die folgenden Migrationspfade:

- Wenn Sie ein Upgrade auf Skype for Business Server 2019 durchführen, können Sie Exchange UM in Exchange Server 2013 oder 2016 verwenden, Aber Sie müssen ein Upgrade auf die automatische Cloud-Telefonwarte durchführen, wenn Sie Exchange Server 2019 verwenden.

- Wenn Sie ein Upgrade auf Exchange Server 2019 durchführen und frühere Versionen von Exchange Server UM für Skype for Business Server Voice Messaging verwenden, empfiehlt Microsoft, vor dem Postfachupgrade auf Skype for Business Server 2019 zu aktualisieren.  Andernfalls gehen die Sprachnachrichtenfunktionen verloren.

Weitere Informationen zum Planen Ihrer Migration finden Sie unter [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Migrieren eines zuvor implementierten automatischen Exchange UM-Attendantsystems

Derzeit unterstützen wir keine automatisierte Migration in die Cloud eines automatischen UM-Attendant-Systems, das in Exchange 2013 oder 2016 erstellt wurde. Um ein automatisches Attendantsystem manuell neu zu erstellen, müssen Sie:

1. Verwenden Sie Die PowerShell-Befehle des Exchange-Admins, um die Struktur des alten automatischen Telefonanlagesystems zu überprüfen, einschließlich geschachtelter automatischer Telefonanten und Anrufwarteschlangen.  
2. Erstellen Sie Kopien von Text-zu-Sprache-Skripts oder aufgezeichneten Nachrichten, die jedem Knoten der automatischen UM-Attendant zugeordnet sind.
3. Erstellen Sie lokale Endpunkte für jeden Knoten der automatischen Telefon attendant, einschließlich der Zuweisung einer Testtelefonnummer und Lizenzen zu den Objekten. Beachten Sie, dass Sie jetzt die Möglichkeit haben, lizenzen für lokale Telefonnummern zuzuordnen, die von Onlinediensten wie Telefonsystem verwendet werden.
4. Implementieren Sie einen neuen automatischen Cloud-Telefoniedienst mit Microsoft Teams und Telefonsystem. Details [zur Implementierung finden Sie unter Configure resource accounts.](configure-onprem-ra.md) Laden Sie dabei die Text-zu-Sprache-Skripts oder aufgezeichneten Nachrichten hoch, die jedem Knoten der automatischen UM-Attendant zugeordnet sind.
5. Testen Sie die Funktionalität der automatischen Cloud-Attendant.
6. Zuweisen der Telefonnummer, die der alten automatischen Exchange UM-Telefon attendant zugewiesen ist, der neu erstellten automatischen Haupt-Cloud-Telefonwarte.

Weitere [Informationen zu diesen Schritten](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) finden Sie unter Verschieben einer automatischen Exchange UM-Telefonanlage oder Anrufwarteschlange in das Telefonsystem.

Wenn Sie über eine solide Struktur verfügen, die Ihren Anforderungen entspricht, und ein Skript, das Kunden effizient leitet, fahren Sie mit Konfigurieren von [Ressourcenkonten fort.](configure-onprem-ra.md)

> [!CAUTION]
> Wie in [KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)erwähnt, wird davon abgeraten, automatische Exchange UM-Attendanten, die in Server 2015 erstellt wurden, auf Server mit Server 2019 zu verschieben. Sie müssen sie vorerst in einem Skype for Business Server 2015-Pool im Koexistenzmodus ausführen lassen.

## <a name="see-also"></a>Siehe auch

[Planen der Migration von Skype for Business Server und Exchange Server](plan-um-migration.md)

[Konfigurieren von Ressourcenkonten](configure-onprem-ra.md)

[Aktivieren der Aufzeichnung benutzerdefinierter Ansagen über die Benutzerschnittstelle für Telefoneingaben](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Was sind automatische Cloudtelefonzentralen?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Einrichten einer automatischen Cloudtelefonzentrale](/microsoftteams/create-a-phone-system-auto-attendant)

Exchange UM: [Eingehende Anrufe automatisch beantworten und routen](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Planen der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](plan-hybrid-connectivity.md)

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](configure-hybrid-connectivity.md)

[KB4480742: Anrufe an den Teilnehmerzugriff oder die automatische Telefon attendant führen zu Einem Fehler bei schnell ausgelastet und "Interner 500 Server"-Fehler nach dem Verschieben von Kontaktobjekten zu Skype for Business Server 2019](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)