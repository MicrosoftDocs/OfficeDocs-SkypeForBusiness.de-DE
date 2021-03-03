---
title: Planen der modernen Authentifizierung in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Planungsthemen für die Authentifizierung und Autorisierung für Skype for Business Server, einschließlich der Integration in andere Produkte
ms.openlocfilehash: c657a2b3609c5fb93f7f915c460cd3334f7fac03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816245"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Authentifizierung und Autorisierung in Skype for Business

Authentifizierung und Autorisierung sind verwandte Konzepte, sie können jedoch andere Aufgaben für Sie (obwohl beides erforderlich ist) unternehmen. Einfach ausgedrückt: Authentifizierung (AuthN) hängt von geheimen Schlüsseln ab, die nur einem gültigen Benutzer bekannt oder bekannt sind, und dies kann ein Kennwort, Code, Fingerabdruck, Zertifikat, eine Kombination von Ansprüchen über den Benutzer, die wahr sind, oder eine Kombination dieser Gemeinsam verwendeten Dinge sein. AuthN ist ein Prozess, mit dem Sie nachweisen können, wer Sie sind.

Bei der Autorisierung (AuthZ) geht es darum, worauf Sie Zugriff haben, nachdem Sie ihre Herkunft nachgewiesen haben. Es bestimmt, was Sie sehen, bearbeiten und anderweitig darauf zugreifen dürfen. Beispielsweise haben Sie möglicherweise leistungsstarken Websitesammlungsadministratorzugriff auf SharePoint Online, aber wenn Sie zu einer anderen Onlinearbeitsauslastung wie Skype for Business Online wechseln, verfügen Sie möglicherweise über die Berechtigungen zum Behandeln von Benutzerproblemen und nicht zum Ändern der Konfiguration der Server oder Server. Bei einer dritten Arbeitsauslastung, z. B. Exchange Online, haben Sie möglicherweise nur den Zugriff des durchschnittlichen Benutzers. AuthZ überprüft, was und wie viel Zugriff Sie auf Dienste/Worloads, Anwendungen, Dateien und andere Daten haben.

Unsere Beispiele beziehen sich auf Onlineeigenschaften wie SharePoint und Exchange Online, aber die Prozesse von AuthN und AuthZ funktionieren lokal und in einer Hybridbereitstellung auf die gleiche Weise. Letztendlich sind Tools wie AAD Connect und ADFS an der Authentifizierung und AuthZ beteiligt, indem sie entweder lokale Konten und Kennwörter mit dem Ad der Cloud (azure AD) synchronisieren oder den Fluss von AuthZ eindringen, sodass ein Benutzer nicht häufig zur Eingabe seiner Anmeldeinformationen aufgefordert wird, z. B. beim Wechseln zwischen Arbeitsauslastungen in der Cloud und beim Erstellen von Single Sign-On-Szenarien. Aber sie sind an sich nicht für AuthN oder AuthZ verantwortlich, sondern nur Teil der Mechanismen.

Heutzutage betrachten viele Technologien diese Prozesse (AuthN und AuthZ) als einen Mechanismus, und Sie hören viele Verweise auf den Authentifizierungsprozess, die auch die Autorisierung enthalten. Es ist wichtig, sich daran zu erinnern, dass der erste Schritt beim Benutzerzugriff AuthN ist, um zu beweisen, wer Sie sind, und dass AuthZ das Wissen darüber verwendet, wer der Benutzer ist, um zu bestimmen, auf was er Zugriff hat (wie Sie mit Open Authorization oder OAuth sehen werden).

  
## <a name="authentication-and-authorization-planning-topics"></a>Themen zur Authentifizierungs- und Autorisierungsplanung

[Verwenden der modernen Authentifizierung (ADAL) mit Skype for Business](plan-adal.md)

[Unterstützte Skype for Business-Topologien mit moderner Authentifizierung](topologies-supported.md)

[Planen der internen und externen Deschaltierung von Legacyauthentifizierungsmethoden für Ihr Netzwerk.](turn-on-modern-auth.md)

