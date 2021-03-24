---
title: Planen einer Cloudanrufwarteschlange
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
description: Übersicht über die Verwendung einer automatischen Cloud-Telefonwarte mit Skype for Business Server 2019.
ms.openlocfilehash: 62731691f4e56c923d2dd8fa6057f244776ec65b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110491"
---
# <a name="plan-cloud-call-queues"></a>Planen von Cloud-Anrufwarteschlangen

Die Cloudanrufwarteschlange ist ein Dienst, der Kundenanrufe akzeptiert, eine Begrüßungsnachricht abnimmt und diese Anrufe dann in einer Warteschleife platziert, während eine vorkonfigurierte Liste von Agents zum Beantworten dieser Anrufe durchsucht wird. Sie können die Gruppe von Agents in E-Mail-aktivierten Verteilerlisten oder Sicherheitsgruppen definieren. Ihre Organisation kann über eine oder mehrere Anrufwarteschlangen verfügen. Anrufwarteschlangen werden in der Regel in Kombination mit automatischen Telefonanten verwendet.

Darüber hinaus können Cloudanrufwarteschlangen:

- Musik, während Anrufer auf die Warteschleife warten
- Angepasste Einstellungen für maximale Größe, Timeout und Anrufbehandlungsoptionen für Die Anrufwarteschlange

Jeder Anrufwarteschlange wird ein Ressourcenkonto **(siehe** [Konfigurieren](configure-onprem-ra.md)von Ressourcenkonten ) auf Ihrem Skype for Business Server 2019-System zugewiesen, das direkt mit einer Anrufwarteschlange im Microsoft Teams Admin Center verknüpft wird. Weitere [Informationen dazu,](/MicrosoftTeams/create-a-phone-system-call-queue) was Anrufwarteschlangen sind und welche Optionen und Features für Anrufwarteschlangen vorhanden sind, finden Sie unter Erstellen einer Cloudanrufwarteschlange.

> [!NOTE]
> Sie können einer Anrufwarteschlange mehrere Telefonnummern zuweisen, es müssen jedoch Microsoft-Dienstnummern, Direkte Routingnummern oder Hybridnummern sein.

## <a name="requirements"></a>Anforderungen

Bei den folgenden Anforderungen wird davon ausgegangen, dass Skype for Business Server 2019 bereits in einer unterstützten Topologie bereitgestellt ist.  Ihre Anforderungen hängen von Ihrem Szenario ab:

- Führen Sie für eine neue Konfiguration von Cloudanrufwarteschlangen die unter [Configure resource accounts beschriebenen Schritte aus.](configure-onprem-ra.md) Sie müssen Ressourcenkonten entweder online oder in Skype for Business Server 2019 erstellen und der Anrufwarteschlange möglicherweise auch eine Telefonnummer zuordnen.

Zusätzlich zu den oben genannten Anforderungen müssen die folgenden Anforderungen für die Verbindung mit dem Microsoft Cloud-Anrufwarteschlangendienst konfiguriert werden:

- Hybridkonnektivität. Wenn Sie Skype for Business Server bereits bereitgestellt haben und Cloudanrufwarteschlangen für Ihre lokalen Benutzer aktivieren möchten, müssen Sie sicherstellen, dass sie über hybride Verbindungen zwischen Ihren lokalen und Onlineumgebungen verfügen. Dies wird manchmal als geteilte Domänenkonfiguration bezeichnet.

   Weitere Informationen finden Sie unter [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) und [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).

- Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die lizenzfreie Virtuelle Benutzerlizenz des Telefonsystems verwenden. Dies bietet Telefonsystemfunktionen für Telefonnummern auf Organisatorischer Ebene und ermöglicht ihnen das Erstellen automatischer Telefonwarteschlangen- und Anrufwarteschlangenfunktionen.

- Erstellen Sie ein lokales [Ressourcenkonto](configure-onprem-ra.md) für jede Anrufwarteschlange, und weisen Sie bei Bedarf eine Lizenz und Telefonnummer zu.  

Wenn Sie über eine solide Struktur verfügen, die Ihren Anforderungen entspricht, und ein Skript, das Kunden effizient leitet, fahren Sie mit Konfigurieren von [Ressourcenkonten fort.](configure-onprem-ra.md)

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Ressourcenkonten](configure-onprem-ra.md)

[Aktivieren der Aufzeichnung benutzerdefinierter Ansagen über die Benutzerschnittstelle für Telefoneingaben](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Was sind automatische Cloudtelefonzentralen?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Planen der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](plan-hybrid-connectivity.md)

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](configure-hybrid-connectivity.md)

[Verwalten von Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)