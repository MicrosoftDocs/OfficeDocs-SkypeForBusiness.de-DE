---
title: Planen einer Cloud-Anrufwarteschleife
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
description: Übersicht über die Verwendung einer automatischen Cloudtelefonzentrale mit Skype for Business Server 2019.
ms.openlocfilehash: df8013a4abc2029d585032b3d0bce810175e04f4
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615421"
---
# <a name="plan-cloud-call-queues"></a>Planen von Cloud-Anrufwarteschlangen

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Die Cloudanrufwarteschleife ist ein Dienst, der Kundenanrufe annimmt, eine Begrüßungsnachricht abgibt und diese Anrufe dann in einer Wartewarteschleife platziert, während eine vorkonfigurierte Liste von Agents gesucht wird, um diese Anrufe anzunehmen. Sie können die Gruppe von Agents in E-Mail-aktivierten Verteilerlisten oder Sicherheitsgruppen definieren. Ihre Organisation kann eine oder mehrere Anrufwarteschleifen haben. Anrufwarteschleifen werden in der Regel in Kombination mit automatischen Telefonzentralen verwendet.

Darüber hinaus können Cloudanrufwarteschleifen Folgendes bereitstellen:

- Musik, während Anrufer im Wartebereich warten
- Angepasste Einstellungen für maximale Größe der Anrufwarteschleife, Timeout- und Anrufbehandlungsoptionen

Jeder Anrufwarteschleife wird ein **Ressourcenkonto** (siehe [Ressourcenkonten konfigurieren](configure-onprem-ra.md)) auf Ihrem Skype for Business Server 2019-System zugewiesen, das direkt mit einer Anrufwarteschleife im Microsoft Teams Admin Center verknüpft wird. Weitere Informationen dazu, was Anrufwarteschleifen sind und welche Optionen und Features für Anrufwarteschleifen vorhanden sind, finden Sie unter ["Erstellen einer Cloudanrufwarteschleife](/MicrosoftTeams/create-a-phone-system-call-queue) ".

> [!NOTE]
> Sie können einer Anrufwarteschleife mehrere Telefonnummern zuweisen, aber diese müssen Microsoft-Dienstnummern, Direct Routing-Nummern oder Hybridnummern sein.

## <a name="requirements"></a>Anforderungen

Bei den folgenden Anforderungen wird davon ausgegangen, dass Sie bereits Skype for Business Server 2019 in einer unterstützten Topologie bereitgestellt haben.  Ihre Anforderungen hängen von Ihrem Szenario ab:

- Führen Sie für eine neue Konfiguration von Cloudanrufwarteschleifen die unter ["Konfigurieren von Ressourcenkonten"](configure-onprem-ra.md) beschriebenen Schritte aus. Sie müssen Ressourcenkonten entweder online oder in Skype for Business Server 2019 erstellen und möglicherweise auch eine Telefonnummer der Anrufwarteschleife zuordnen.

Zusätzlich zu den oben genannten Anforderungen müssen die folgenden Anforderungen so konfiguriert werden, dass eine Verbindung mit dem Microsoft Cloud-Anrufwarteschleifendienst hergestellt wird:

- Hybridkonnektivität. Wenn Sie bereits Skype for Business Server bereitgestellt haben und Cloudanrufwarteschleifen für Ihre lokalen Benutzer aktivieren möchten, müssen Sie sicherstellen, dass Eine Hybridverbindung zwischen Ihrer lokalen und Ihrer Onlineumgebung eingerichtet ist. Dies wird manchmal als Konfiguration einer geteilten Domäne bezeichnet.

   Weitere Informationen finden Sie unter [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).

- Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die lizenzfreie **Microsoft Teams Telefon Ressourcenkonto** verwenden. Dadurch werden Telefonsystemfunktionen für Telefonnummern auf Organisationsebene bereitgestellt, und Sie können funktionen für automatische Telefonzentralen und Anrufwarteschleifen erstellen.

- Erstellen Sie ein lokales [Ressourcenkonto](configure-onprem-ra.md) für jede Anrufwarteschleife, und weisen Sie bei Bedarf eine Lizenz und Telefonnummer zu.  

Wenn Sie über eine solide Struktur verfügen, die Ihren Anforderungen entspricht, und ein Skript, das Kunden effizient führt, fahren  [Sie mit der Konfiguration von Ressourcenkonten fort](configure-onprem-ra.md).

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Ressourcenkonten](configure-onprem-ra.md)

[Aktivieren der Aufzeichnung benutzerdefinierter Ansagen über die Benutzerschnittstelle für Telefoneingaben](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Was sind automatische Cloudtelefonzentralen?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Einrichten einer automatischen Cloudtelefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Planen der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](plan-hybrid-connectivity.md)

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](configure-hybrid-connectivity.md)

[Verwalten von Ressourcenkonten in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)