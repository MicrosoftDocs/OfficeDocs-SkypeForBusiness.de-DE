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
description: Übersicht über die Verwendung einer automatischen Cloud-Telefon attendant mit Skype for Business Server 2019.
ms.openlocfilehash: 629c28e752b7316a3d2e7fda0acf7f457788d6a8
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918741"
---
# <a name="plan-cloud-call-queues"></a>Planen von Cloud-Anrufwarteschlangen

Bei der Cloudanrufwarteschleife handelt es sich um einen Dienst, der Kundenanrufe akzeptiert, eine Begrüßungsnachricht abspielt und diese Anrufe dann in einer Warteschleife platziert, während eine vorkonfigurierte Liste von Agents zur Beantwortung dieser Anrufe durchsucht wird. Sie können die Gruppe von Agents in E-Mail-aktivierten Verteilerlisten oder Sicherheitsgruppen definieren. Ihre Organisation kann über eine oder mehrere Anrufwarteschleifen verfügen. Anrufwarteschleifen werden in der Regel in Kombination mit automatischen Telefon attendants verwendet.

Darüber hinaus können Cloudanrufwarteschleifen:

- Musik, während Anrufer in der Warteschleife warten
- Angepasste Einstellungen für maximale Größe, Timeout und Anrufbehandlungsoptionen für Anrufwarteschlangen

Jeder Anrufwarteschleife wird ein Ressourcenkonto **(siehe** "Ressourcenkonten [konfigurieren")](configure-onprem-ra.md)auf Ihrem Skype for Business Server 2019-System zugewiesen, das direkt mit einer Anrufwarteschleife im Microsoft Teams Admin Center verknüpft wird. Weitere [Informationen dazu,](/MicrosoftTeams/create-a-phone-system-call-queue) was Anrufwarteschleifen sind und welche Optionen und Funktionen für Anrufwarteschleifen vorhanden sind, finden Sie unter "Erstellen einer Cloud-Anrufwarteschleife".

> [!NOTE]
> Sie können einer Anrufwarteschleife mehrere Telefonnummern zuweisen, dabei muss es sich jedoch um Microsoft-Servicenummern, Direktroutingnummern oder Hybridnummern befinden.

## <a name="requirements"></a>Anforderungen

Bei den folgenden Anforderungen wird davon ausgegangen, dass Sie Skype for Business Server 2019 bereits in einer unterstützten Topologie bereitgestellt haben.  Ihre Anforderungen hängen von Ihrem Szenario ab:

- Führen Sie für eine neue Konfiguration von Cloudanrufwarteschleifen die unter ["Konfigurieren von Ressourcenkonten" beschriebenen Schritte aus.](configure-onprem-ra.md) Sie müssen Ressourcenkonten entweder online oder in Skype for Business Server 2019 erstellen und der Anrufwarteschleife möglicherweise auch eine Telefonnummer zuordnen.

Zusätzlich zu den oben genannten Anforderungen müssen die folgenden Anforderungen so konfiguriert werden, dass eine Verbindung mit dem Microsoft Cloud-Anrufwarteschleifendienst hergestellt wird:

- Hybridkonnektivität. Wenn Sie Skype for Business Server bereits bereitgestellt haben und Cloudanrufwarteschlangen für Ihre lokalen Benutzer aktivieren möchten, müssen Sie sicherstellen, dass die Hybridkonnektivität zwischen Ihrer lokalen und der Onlineumgebung eingerichtet ist. Dies wird manchmal als Konfiguration für geteilte Domänen bezeichnet.

   Weitere Informationen finden Sie unter [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).

- Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die kostenlose virtuelle Benutzerlizenz des Telefonsystems verwenden. Dadurch werden Telefonsystemfunktionen für Telefonnummern auf Organisationsebene zur Verfügung gestellt, und Sie können Funktionen für automatische Telefonanrufe und Anrufwarteschleifen erstellen.

- Erstellen Sie für [jede](configure-onprem-ra.md) Anrufwarteschleife ein lokales Ressourcenkonto, und weisen Sie bei Bedarf eine Lizenz und telefonnummer zu.  

Wenn Sie eine solide Struktur haben, die Ihren Anforderungen entspricht, und ein Skript, das Kunden effizient leitet, fahren Sie mit dem Konfigurieren [von Ressourcenkonten fort.](configure-onprem-ra.md)

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Ressourcenkonten](configure-onprem-ra.md)

[Aktivieren der Aufzeichnung benutzerdefinierter Ansagen über die Benutzerschnittstelle für Telefoneingaben](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Was sind automatische Cloudtelefonzentralen?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Planen der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](plan-hybrid-connectivity.md)

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](configure-hybrid-connectivity.md)

[Verwalten von Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)
