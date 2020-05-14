---
title: Planen einer Cloud-Anrufwarteschlange
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
description: Übersicht über die Verwendung einer automatischen Cloud-Telefonzentrale mit Skype for Business Server 2019.
ms.openlocfilehash: 2186909b3ec905d6ec6d387bcea172d8fb80287c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221305"
---
# <a name="plan-cloud-call-queues"></a>Planen von Cloud-Anrufwarteschlangen

Cloud-Anrufwarteschlange ist ein Dienst, der Kundenanrufe akzeptiert, eine grußmeldung abgibt und diese Anrufe dann in einer Warteschlange platziert, während eine vorkonfigurierte Liste mit Agents durchsucht wird, um diese Anrufe zu beantworten. Sie können die Gruppe von Agents in e-Mail-aktivierten Verteilerlisten oder Sicherheitsgruppen definieren. Ihre Organisation kann eine oder mehrere Anrufwarteschlangen haben. Anrufwarteschlangen werden in der Regel in Kombination mit automatischen Telefonzentralen verwendet.

Darüber hinaus können Cloud-Anrufwarteschlangen Folgendes bieten:

- Musik, während Anrufer auf die Warteschleife warten
- Angepasste Einstellungen für maximale Größe, Timeout und Anruf Behandlungsoptionen für die Anrufwarteschlange

Jeder Anrufwarteschlange wird ein **Ressourcenkonto** (siehe [Configure Resource Accounts](configure-onprem-ra.md)) auf Ihrem Skype for Business Server 2019-System zugewiesen, das direkt mit einer Anrufwarteschlange im Microsoft Teams Admin Center verknüpft wird. Weitere Informationen dazu, welche Anrufwarteschlangen und welche Optionen und Funktionen für Anrufwarteschlangen vorhanden sind, finden Sie unter [Erstellen einer Warteschlange für Cloud-Anrufe](/MicrosoftTeams/create-a-phone-system-call-queue) .

> [!NOTE]
> Sie können einer Anrufwarteschlange mehrere Telefonnummern zuweisen, Sie müssen jedoch Microsoft-Dienstnummern, direkte Routing Nummern oder Hybrid Nummern sein.

## <a name="requirements"></a>Anforderungen

Bei den folgenden Anforderungen wird vorausgesetzt, dass Sie bereits Skype for Business Server 2019 in einer unterstützten Topologie bereitgestellt haben.  Ihre Anforderungen hängen von Ihrem Szenario ab:

- Für eine neue Konfiguration von Cloud-Anrufwarteschlangen führen Sie die unter [Configure Resource Accounts](configure-onprem-ra.md)beschriebenen Schritte aus. Sie müssen Ressourcenkonten entweder online oder in Skype for Business Server 2019 erstellen, und Sie müssen möglicherweise auch eine Telefonnummer der Anrufwarteschlange zuordnen.

Zusätzlich zu den oben aufgeführten Anforderungen müssen die folgenden Anforderungen so konfiguriert werden, dass eine Verbindung mit dem Microsoft Cloud-Anrufwarteschlangen-Dienst hergestellt wird:

- Hybrid Konnektivität. Wenn Sie bereits Skype for Business Server bereitgestellt haben und Cloud-Anrufwarteschlangen für Ihre lokalen Benutzer aktivieren möchten, müssen Sie sicherstellen, dass Sie eine hybride Konnektivität zwischen Ihren lokalen und Online-Umgebungen eingerichtet haben. Dies wird manchmal als geteilte Domänenkonfiguration bezeichnet.

   Weitere Informationen finden Sie unter [Planen der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](plan-hybrid-connectivity.md) und [Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](configure-hybrid-connectivity.md).

- Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die virtuelle Benutzerlizenz für das ﻿kostenlose Telefon System verwenden. Dadurch werden Telefon System Funktionen für Telefonnummern auf Organisationsebene bereitgestellt, und Sie können eine automatische Telefonzentrale und Funktionen für die Anrufwarteschlange erstellen.

- Erstellen Sie für jede Anrufwarteschlange ein lokales [Ressourcenkonto](configure-onprem-ra.md) , und weisen Sie bei Bedarf eine Lizenz und eine Telefonnummer zu.  

## <a name="additional-planning-resources"></a>Zusätzliche Planungsressourcen

Das Lernprogramm mit dem Titel [Small Business Beispiel: Einrichten einer automatischen Telefonzentrale](/microsoftteams/tutorial-org-aa) durchläuft den Prozess der Erfassung von Informationen zu Benutzeranforderungen, der Planung einer Struktur von automatischen Telefonzentralen und Benutzern (und möglicherweise auch von Anrufwarteschlangen), dem Schreiben der Menüansagen und dem Implementieren des Plans im Online Admin Center. Lesen Sie das Lernprogramm, und verwenden Sie die Übungen dort t erstellen Sie Ihren Plan.

Wenn Sie über eine solide Struktur verfügen, die Ihren Anforderungen entspricht, und ein Skript, das Kunden effizient leitet, fahren Sie mit [Konfigurieren von Ressourcenkonten](configure-onprem-ra.md)fort.

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Ressourcenkonten](configure-onprem-ra.md)

[Aktivieren der Aufzeichnung benutzerdefinierter Ansagen über die Benutzerschnittstelle für Telefoneingaben](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Was sind automatische Cloudtelefonzentralen?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Planen der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](plan-hybrid-connectivity.md)

[Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](configure-hybrid-connectivity.md)

[Verwalten von Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)
