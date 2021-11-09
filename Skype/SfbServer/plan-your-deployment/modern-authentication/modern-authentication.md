---
title: Planen der modernen Authentifizierung in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Planungsthemen für Authentifizierung und Autorisierung für Skype for Business Server, einschließlich der Integration in andere Produkte
ms.openlocfilehash: 3bcd9ab78c9703dd938230740fddba4034aff315
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851869"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Erläuterung von Authentifizierung und Autorisierung in Skype for Business

Authentifizierung und Autorisierung sind verwandte Konzepte, führen aber unterschiedliche Arbeit für Sie aus (obwohl beides erforderlich ist). Vereinfacht ausgedrückt hängt die Authentifizierung (AuthN) von geheimen Schlüsseln ab, die nur ein gültiger Benutzer kennt oder besitzt. Dabei kann es sich um ein Kennwort, Code, Fingerabdruck, Zertifikat, eine Kombination von Ansprüchen über den Benutzer, die wahr sind, oder um eine Kombination dieser Dinge, die zusammen verwendet werden, handelt. AuthN ist ein Prozess, mit dem Sie nachweisen können, wer Sie sind.

Die Autorisierung (AuthZ) befasst sich mit dem, worauf Sie Zugriff haben, nachdem Sie nachgewiesen haben, wer Sie sind. Es bestimmt, was Sie sehen, bearbeiten und anderweitig darauf zugreifen dürfen. Beispielsweise haben Sie möglicherweise leistungsstarken Zugriff auf SharePoint Online durch den Websitesammlungsadministrator. Wenn Sie jedoch zu einer anderen Onlinearbeitsauslastung wechseln, z. B. Skype for Business Online, verfügen Sie möglicherweise über die Rechte zum Beheben von Benutzerproblemen, und ändern Sie nicht die Konfiguration des Servers oder der Server. Bei einer dritten Workload, z. B. Exchange Online, haben Sie möglicherweise nur den durchschnittlichen Benutzerzugriff. AuthZ überprüft, was und wie viel Zugriff Sie auf Dienste/Worloads, Anwendungen, Dateien und andere Daten haben.

Unsere Beispiele umfassen Onlineeigenschaften wie SharePoint und Exchange online, aber die Prozesse von AuthN und AuthZ funktionieren lokal und in einer Hybridumgebung auf die gleiche Weise. Letztendlich werden Tools wie AAD Verbinden und ADFS in die AuthN- und AuthZ-Story einbezogen, indem sie entweder lokale Konten und Kennwörter mit dem AD der Cloud synchronisieren (was Azure AD ist) oder in den Fluss von AuthZ eindringen, sodass ein Benutzer nicht häufig zur Eingabe seiner Anmeldeinformationen aufgefordert wird, z. B. beim Wechseln zwischen Workloads in der Cloud, wodurch ein einzelner Sign-On Szenarien erstellt wird. Aber sie sind an sich nicht verantwortlich für AuthN oder AuthZ, sondern nur Teil der Mechanismen.

Heute betrachten viele Technologien diese Prozesse (AuthN und AuthZ) als einen Mechanismus, und Sie werden viele Verweise auf Authentifizierungsprozesse hören, die auch die Autorisierung enthalten. Es ist wichtig zu beachten, dass der erste Schritt beim Benutzerzugriff AuthN ist, um zu bestätigen, wer Sie sind und dass AuthZ das Wissen verwendet, wer der Benutzer ist, um zu bestimmen, auf was er Zugriff hat (wie Sie mit Open Authorization oder OAuth sehen werden).

  
## <a name="authentication-and-authorization-planning-topics"></a>Themen zur Authentifizierungs- und Autorisierungsplanung

[Verwenden der modernen Authentifizierung (Modern Authentication, ADAL) mit Skype for Business](plan-adal.md)

[Unterstützte Skype for Business-Topologien mit moderner Authentifizierung](topologies-supported.md)

[Planen, legacy-Authentifizierungsmethoden intern und extern für Ihr Netzwerk zu deaktivieren.](turn-on-modern-auth.md)

