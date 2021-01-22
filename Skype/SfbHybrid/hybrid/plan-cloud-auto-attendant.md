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
description: Übersicht über die Verwendung einer automatischen Cloud-Telefon attendant mit Skype for Business Server 2019
ms.openlocfilehash: 50cd9bb8b20e44d750dab68ec6fecb30bd02e203
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918691"
---
# <a name="plan-cloud-auto-attendants"></a>Planen automatischer Cloud-Telefonzentralen

Die mit Exchange Unified Messaging (Exchange Server 2013 oder Exchange Server 2016) verwendete automatische Attendant ist in Exchange Server 2019 oder Exchange Online nicht mehr verfügbar. Wenn Ihre Implementierung von Skype for Business Server 2019 in eine dieser Versionen von Exchange integriert ist, müssen Sie die Cloud-Voice-Onlinefeatures verwenden, die dem Telefonsystem zugeordnet sind. Informationen zum Verschieben von Exchange UM-Diensten, die auf Exchange Server 2013 und 2016 in die Cloud gespeichert sind, finden Sie unter "Planen der Migration von [Skype for Business Server](plan-um-migration.md) und Exchange Server".

Dies bedeutet grundsätzlich, dass Sie über eine Hybridimplementierung von Skype for Business Server 2019 verfügen, wenn Sie Unified Messaging-Funktionen wie automatische Telefon attendants verwenden möchten. Weitere Informationen finden Sie unter "Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und [Microsoft 365 oder Office 365".](configure-hybrid-connectivity.md)

Bei einer automatischen Telefon attendant handelt es sich um einen Clouddienst, der Kundenanrufe annimmt und Begrüßungen wiedererwählt, ihnen Menüoptionen bietet und mit Anrufern per Spracherkennung oder Wähltaße interagiert, um ihre Anrufe an das richtige Ziel weiterzurouten. Jeder automatischen Telefonzentrale wird ein Ressourcenkonto *(siehe* "Ressourcenkonten [konfigurieren")](configure-onprem-ra.md)auf Ihrem Skype for Business Server 2019-System zugewiesen, das direkt mit einer automatischen Telefonzentrale im Microsoft Teams Admin Center verknüpft wird. Weitere [Informationen dazu,](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) was automatische Cloud-Attendants sind und welche Optionen und Funktionen für automatische Attendants vorhanden sind, finden Sie unter "Was sind automatische Cloud-Attendants?".

> [!NOTE]
> Sie können einer automatischen Attendant mehrere Microsoft-Servicenummern, Direct Routing-Nummern oder Hybridnummern zuweisen.

Ein eingehender Anruf bei einer automatischen Cloud-Telefon attendant kann einen von mehreren Pfaden verwenden, wie hier gezeigt:

![Diagramm für automatische Attendants](../../SfBServer2019/media/AA-plan-concept.png)

1. Über Skype for Business Server 2019
2. Über einen [Session Border Controller und](/MicrosoftTeams/direct-routing-border-controllers.md) [direktes Routing](/MicrosoftTeams/direct-routing-plan.md)
3. Über eine Onlinenummer in Microsoft 365 oder Office 365.

Siehe auch:

- [Einrichten einer automatischen Cloudtelefonzentrale](/microsoftteams/create-a-phone-system-auto-attendant)
- [Automatisches Beantworten und Weiterleiten eingehender Anrufe](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Anforderungen

Bei den folgenden Anforderungen wird davon ausgegangen, dass Skype for Business Server 2019 bereits in einer unterstützten Topologie bereitgestellt wurde.  Ihre Anforderungen hängen von Ihrem Szenario ab:

- Wenn Sie Exchange UM bereits online oder lokal verwenden und ein Upgrade auf Skype for Business 2019 durchführen, müssen Sie die Struktur Ihrer automatischen Telefon attendants erfassen und mithilfe automatischer Cloud-Telefon attendants in der Cloud neu erstellen. Weitere Informationen finden Sie unter [Verschieben einer automatischen Exchange UM-Telefonanlage](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)oder -Anrufwarteschleife in das Telefonsystem.

- Führen Sie für eine neue Konfiguration von automatischen Cloud-Attendants die unter ["Konfigurieren von Ressourcenkonten" beschriebenen Schritte aus.](configure-onprem-ra.md)

Zusätzlich zu den oben genannten Anforderungen müssen die folgenden Anforderungen so konfiguriert werden, dass eine Verbindung mit dem automatischen Microsoft Cloud-Attendant-Dienst hergestellt wird:

- Hybridkonnektivität. Wenn Sie Skype for Business Server bereits bereitgestellt haben und die automatische Cloud attendant für Ihre lokalen Benutzer aktivieren möchten, müssen Sie sicherstellen, dass Sie eine Hybridverbindung zwischen Ihrer lokalen und der Onlineumgebung eingerichtet haben. Dies wird manchmal als Konfiguration für geteilte Domänen bezeichnet.

   Weitere Informationen finden Sie unter Plan [hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).

- Wenn Sie Ihrer automatischen Telefon attendant eine Telefonnummer zuweisen, benötigen Sie eine [Office 365 Enterprise E5-Lizenz.](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing)
- Erstellen Sie ein [Onlineressourcenkonto](/MicrosoftTeams/manage-resource-accounts.md) oder ein lokales [Ressourcenkonto](configure-onprem-ra.md) für jede automatische Telefon attendant, und weisen Sie Telefonnummern und Lizenzen zu. 

## <a name="migration-and-interoperability"></a>Migration und Interoperabilität

Wenn Sie die Bereitstellung von Skype for Business Server 2019 und/oder Exchange Server 2019 planen, müssen Sie Die Migration sorgfältig planen, um eine kontinuierliche Unterstützung für automatische Telefon attendants sicherzustellen. Denken Sie dabei an Folgendes:

- Exchange Server 2019 bietet keine Exchange -UM-Funktionen mehr
- Exchange Unified Messaging befindet sich im Auspensionsmodus
- Skype for Business Server 2019 ist nicht mehr in Exchange Online UM integriert

Automatische Cloud attendants can be configured with Skype for Business Server 2019, 2015, and 2013.

Microsoft empfiehlt die folgenden Migrationspfade:

- Wenn Sie ein Upgrade auf Skype for Business Server 2019 durchführen, können Sie Exchange UM in Exchange Server 2013 oder 2016 verwenden, aber Sie müssen ein Upgrade auf die automatische Cloud attendant durchführen, wenn Sie Exchange Server 2019 verwenden.

- Wenn Sie ein Upgrade auf Exchange Server 2019 durchführen und frühere Versionen von Exchange Server UM für Skype for Business Server Voice Messaging verwenden, empfiehlt Microsoft, vor dem Postfachupgrade auf Skype for Business Server 2019 zu aktualisieren.  Andernfalls gehen die Voicemailfunktionen verloren.

Weitere Informationen zum Planen Ihrer Migration finden Sie unter ["Plan for Skype for Business Server and Exchange Server migration ".](plan-um-migration.md)

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Migrieren eines zuvor implementierten automatischen Exchange UM-Attendant-Systems

Derzeit unterstützen wir keine automatisierte Migration in die Cloud eines automatischen UM-Attendant-Systems, das in Exchange 2013 oder 2016 erstellt wurde. Um ein automatisches Attendantsystem manuell neu zu erstellen, müssen Sie:

1. Verwenden Sie Exchange-Administrator-PowerShell-Befehle, um die Struktur des alten Systems der automatischen Telefonanlage zu überprüfen, einschließlich geschachtelter automatischer Telefonisten und Anrufwarteschleifen.  
2. Erstellen Sie Kopien von Text-zu-Sprache-Skripts oder aufgezeichneten Nachrichten, die jedem Knoten der automatischen UM-Attendant zugeordnet sind.
3. Erstellen Sie lokale Endpunkte für jeden Knoten der automatischen Telefon attendant, einschließlich der Zuweisung von Testtelefonnummern und Lizenzen zu den Objekten. Beachten Sie, dass Sie jetzt die Möglichkeit haben, lizenzen für lokale Telefonnummern zuzuordnen, die von Onlinediensten wie dem Telefonsystem verwendet werden.
4. Implementieren Sie einen neuen automatischen Cloudtelefoniedienst mit Microsoft Teams und dem Telefonsystem. [Implementierungsdetails finden Sie unter](configure-onprem-ra.md) "Konfigurieren von Ressourcenkonten". Laden Sie dabei die Text-zu-Sprache-Skripts oder aufgezeichneten Nachrichten hoch, die jedem Knoten der automatischen UM-Attendant zugeordnet sind.
5. Testen Sie die Funktionalität der automatischen Cloud-Attendant.
6. Zuweisen Sie die der alten automatischen Exchange -Telefon attendant zugewiesene Telefonnummer erneut der neu erstellten automatischen Haupttelefon attendant der Cloud.

Weitere Informationen zu diesen Schritten finden Sie unter "Verschieben einer [automatischen Exchange UM-Telefonanlage](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) oder -Anrufwarteschleife in das Telefonsystem".

Wenn Sie eine solide Struktur haben, die Ihren Anforderungen entspricht, und ein Skript, das Kunden effizient leitet, fahren Sie mit dem Konfigurieren [von Ressourcenkonten fort.](configure-onprem-ra.md)

> [!CAUTION]
> Wie in [KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)erwähnt, wird davon abgeraten, in Server 2015 erstellte automatische Exchange -UM-Attendants auf Server mit Server 2019 zu verschieben. Sie müssen sie vorerst in einem Skype for Business Server 2015-Pool im Koexistenzmodus ausführen lassen.

## <a name="see-also"></a>Siehe auch

[Planen der Migration von Skype for Business Server und Exchange Server](plan-um-migration.md)

[Konfigurieren von Ressourcenkonten](configure-onprem-ra.md)

[Aktivieren der Aufzeichnung benutzerdefinierter Ansagen über die Benutzerschnittstelle für Telefoneingaben](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Was sind automatische Cloudtelefonzentralen?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Einrichten einer automatischen Cloudtelefonzentrale](/microsoftteams/create-a-phone-system-auto-attendant)

Exchange UM: [Automatisches Beantworten und Routen eingehender Anrufe](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Planen der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](plan-hybrid-connectivity.md)

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](configure-hybrid-connectivity.md)

[KB4480742: Anrufe beim Teilnehmerzugriff oder bei der automatischen Telefon attendant führen nach dem Verschieben von Kontaktobjekten zu Skype for Business Server 2019 zu einem Fehler bei "Schnell ausgelastet" und "500 Server Internal"](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
