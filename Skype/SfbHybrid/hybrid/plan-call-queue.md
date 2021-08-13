---
title: Planen einer Cloudanrufwarteschleife
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
description: Übersicht über die Verwendung einer automatischen Cloudtelefonzentrale mit Skype for Business Server 2019.
ms.openlocfilehash: fa1807c272c8d9bba8ae406a87dc55589560d870da5b59fc093c2d9d1a2933e6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300511"
---
# <a name="plan-cloud-call-queues"></a>Planen von Cloud-Anrufwarteschlangen

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Die Cloudanrufwarteschleife ist ein Dienst, der Kundenanrufe akzeptiert, eine Begrüßungsnachricht wiedergibt und diese Anrufe dann in einer Warteschleife platziert, während eine vorkonfigurierte Liste von Agents gesucht wird, um diese Anrufe zu beantworten. Sie können die Gruppe von Agents in E-Mail-aktivierten Verteilerlisten oder Sicherheitsgruppen definieren. Ihre Organisation kann eine oder viele Anrufwarteschleifen haben. Anrufwarteschleifen werden in der Regel in Kombination mit automatischen Telefonzentralen verwendet.

Darüber hinaus können Cloud-Anrufwarteschleifen Folgendes bereitstellen:

- Musik, während Anrufer auf die Warteschleife warten
- Angepasste Einstellungen für die maximale Größe, das Timeout und die Anrufbehandlungsoptionen für die Anrufwarteschleife

Jeder Anrufwarteschleife wird ein **Ressourcenkonto** (siehe ["Ressourcenkonten konfigurieren")](configure-onprem-ra.md)auf Ihrem Skype for Business Server 2019-System zugewiesen, das direkt mit einer Anrufwarteschleife im Microsoft Teams Admin Center verknüpft wird. Weitere Informationen dazu, was Anrufwarteschleifen sind und welche Optionen und Features für Anrufwarteschleifen vorhanden sind, finden Sie unter [Erstellen einer Cloud-Anrufwarteschleife.](/MicrosoftTeams/create-a-phone-system-call-queue)

> [!NOTE]
> Sie können einer Anrufwarteschleife mehrere Telefonnummern zuweisen, es müssen sich jedoch um Microsoft-Dienstnummern, Direct Routing-Nummern oder Hybridnummern handeln.

## <a name="requirements"></a>Anforderungen

Bei den folgenden Anforderungen wird davon ausgegangen, dass Sie bereits Skype for Business Server 2019 in einer unterstützten Topologie bereitgestellt haben.  Ihre Anforderungen hängen von Ihrem Szenario ab:

- Führen Sie für eine neue Konfiguration von Cloud-Anrufwarteschleifen die unter Konfigurieren von [Ressourcenkonten](configure-onprem-ra.md)beschriebenen Schritte aus. Sie müssen Ressourcenkonten entweder online oder in Skype for Business Server 2019 erstellen, und Sie müssen möglicherweise auch eine Telefonnummer der Anrufwarteschleife zuordnen.

Zusätzlich zu den oben genannten Anforderungen müssen die folgenden Anforderungen so konfiguriert werden, dass eine Verbindung mit dem Microsoft Cloud-Anrufwarteschleifendienst hergestellt wird:

- Hybridkonnektivität. Wenn Sie bereits Skype for Business Server bereitgestellt haben und Cloud-Anrufwarteschleifen für Ihre lokalen Benutzer aktivieren möchten, müssen Sie sicherstellen, dass die Hybridkonnektivität zwischen Ihrer lokalen und Onlineumgebung eingerichtet ist. Dies wird manchmal als Konfiguration für geteilte Domänen bezeichnet.

   Weitere Informationen finden Sie unter Planen der [Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](plan-hybrid-connectivity.md) und Konfigurieren der [Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365.](configure-hybrid-connectivity.md)

- Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die kostenlose Telefonsystem Virtuelle Benutzerlizenz verwenden. Dadurch werden telefonnummern auf Organisationsebene Telefonsystem Funktionen bereitgestellt, und Sie können funktionen für automatische Telefonzentralen und Anrufwarteschleifen erstellen.

- Erstellen Sie ein lokales [Ressourcenkonto](configure-onprem-ra.md) für jede Anrufwarteschleife, und weisen Sie bei Bedarf eine Lizenz und Telefonnummer zu.  

Wenn Sie über eine solide Struktur verfügen, die Ihren Anforderungen entspricht, und ein Skript, das Kunden effizient führt, fahren Sie mit  [dem Konfigurieren von Ressourcenkonten](configure-onprem-ra.md)fort.

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Ressourcenkonten](configure-onprem-ra.md)

[Aktivieren der Aufzeichnung benutzerdefinierter Ansagen über die Benutzerschnittstelle für Telefoneingaben](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Was sind automatische Cloudtelefonzentralen?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Planen der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](plan-hybrid-connectivity.md)

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](configure-hybrid-connectivity.md)

[Verwalten von Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)