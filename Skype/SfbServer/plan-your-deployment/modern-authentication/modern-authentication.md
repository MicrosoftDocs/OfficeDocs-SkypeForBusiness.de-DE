---
title: Plan für moderne Authentifizierung in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Planungsthemen für die Authentifizierung und Autorisierung für Skype for Business Server, einschließlich der Integration in andere Produkte
ms.openlocfilehash: f732e4afa6b82554c4248a244276e5e5b60c71cc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815843"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Diskutieren von Authentifizierung und Autorisierung in Skype for Business

Authentifizierung und Autorisierung sind verwandte Konzepte, aber unterschiedliche Aufgaben für Sie (wenn beides notwendig ist). Einfache Ausdrücke: authenciation (authn) hängt von den Geheimnissen ab, die nur ein gültiger Benutzer kennt oder hat, und dies kann ein Kennwort, Code, Fingerabdruck, Zertifikat, eine Kombination von Ansprüchen bezüglich des Benutzers sein, die wahr sind, oder eine Kombination dieser Dinge, die zusammen verwendet werden. Authn ist ein Verfahren, um zu beweisen, dass Sie die Person sind, die Sie sagen.

Autorisierung (Authz) befasst sich mit dem, worauf Sie Zugriff haben, nachdem Sie bewiesen haben, wer Sie sind. Sie bestimmt, was Sie sehen, bearbeiten und anderweitig zugreifen dürfen. So können Sie beispielsweise über einen leistungsfähigen Website Sammlungs Administrator auf SharePoint Online zugreifen, doch wenn Sie zu einer anderen Online-Arbeitsauslastung wechseln, wie Skype for Business Online, verfügen Sie möglicherweise über die Privilegien zur Behandlung von Benutzerproblemen, nicht zur Änderung der Konfiguration des Server oder Server. Bei einer dritten Arbeitsauslastung, wie etwa Exchange Online, haben Sie möglicherweise nur Zugriff auf den durchschnittlichen Benutzer. Authz überprüft, was und wie viel Zugriff Sie auf Dienste/worloads, Anwendungen, Dateien und andere Daten haben.

Unsere Beispiele beinhalten Online-Eigenschaften wie SharePoint und Exchange Online, aber die Prozesse von authn und Authz funktionieren lokal und in einem hybriden lokal auf die gleiche Weise. Letztendlich werden Tools wie Aad Connect und ADFS in die Geschichte von authn und Authz einbezogen, indem lokale Konten und Kennwörter in der Cloud-Anzeige (die Azure AD im Fall von Office 365 oder Azure ist) synchronisiert werden, oder Sie dringen in den Fluss von Authz ein, sodass ein Benutzer wird nicht häufig zur Eingabe Ihrer Anmeldeinformationen aufgefordert, beispielsweise beim Wechseln zwischen Arbeitslasten in der Cloud und beim Erstellen von Szenarien für einmaliges Anmelden. Aber Sie sind nicht in sich selbstverantwortliche authn-oder Authz, nur ein Teil der Mechanik.

Heute berücksichtigen viele Technologien diese Prozesse (authn und Authz) als einen Mechanismus, und Sie hören viele Verweise auf den Authentifizierungsprozess, die auch die Autorisierung enthalten. Beachten Sie bitte, dass der erste Schritt beim Benutzer Zugriff authn ist, der Sie beweist, wer Sie sind, und dass Authz das Wissen verwendet, wer der Benutzer ist, um zu ermitteln, auf was er oder Sie zugreifen kann (wie Sie mit der Berechtigung "Öffnen" oder "OAuth" sehen).

  
## <a name="authentication-and-authorization-planning-topics"></a>Themen zur Authentifizierungs-und Autorisierungs Planung

[How to use Modern Authentication (ADAL) with Skype for Business](plan-adal.md)

[Skype for Business topologies supported with Modern Authentication](topologies-supported.md)

[Planen Sie das Deaktivieren von Legacy Authentifizierungsmethoden intern und extern für Ihr Netzwerk.](turn-on-modern-auth.md)

