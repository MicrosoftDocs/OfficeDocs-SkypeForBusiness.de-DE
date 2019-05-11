---
title: Plan für moderne Authentifizierung in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Themen zur Planung für die Authentifizierung und Autorisierung für Skype für Business Server, einschließlich der Integration in andere Produkte
ms.openlocfilehash: 1a7f20fe10a757001fb3eb819371b81f24d6901e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907157"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Besprechen, Authentifizierung und Autorisierung in Skype für Unternehmen

Authentifizierung und Autorisierung Konzepte sind verwandt, jedoch unterschiedliche Arbeit für Sie tun, (obwohl beide erforderlich sind). Tragen Sie einfach ausgedrückt, hängt von Authenciation (AuthN) Secrets nur ein gültiger Benutzer weiß oder hat und, ein Kennwort, Code, Fingerabdruck, Zertifikat, eine Kombination von Ansprüchen zum Benutzer, die "true" sind oder eine Kombination dieser Elemente gemeinsam verwendet werden kann. AuthN ist ein Prozess, zu belegen, dass Sie sind, die Sie sagen, dass Sie sich befinden.

Autorisierung (AuthZ) ist mit, was Sie Zugriff haben, nachdem Sie geprüft haben, die Sie sind betroffen. Es wird bestimmt, was Sie zugelassen wurden haben, finden Sie unter, bearbeiten und anderweitig zugreifen. Beispielsweise kann Ihnen leistungsstarke Websitesammlungsadministrator Zugriff auf SharePoint Online, aber wenn Sie zu einer anderen online-Arbeitslast wie Skype für Online Business wechseln Sie sind berechtigt, die Benutzer Probleme zu beheben, ändern Sie die Konfiguration der nicht der Server oder Server. In einer dritten Arbeitslast, wie Exchange Online möglicherweise Sie nur die durchschnittliche Benutzer Zugriff haben. AuthZ überprüft, welche und wie viele Access Services/Worloads, Anwendungen, Dateien und anderen Daten, die Ihnen.

Unsere Beispiele umfassen online Eigenschaften wie SharePoint und Exchange online, aber die Prozesse AuthN und AuthZ: lokal funktionieren und in einem Hybriden lokalen die gleiche Weise. Schließlich tools wie AAD verbinden und AD FS im AuthN und AuthZ Textabschnitt durch Synchronisieren von lokalen Benutzerkonten und Kennwörter in der Cloud beteiligt sein des AD (die Azure AD bei Office 365 und Azure ist) oder intruding in den Fluss des AuthZ also, die der Benutzer ist nicht häufig für ihre Anmeldeinformationen angenommen aufgefordert beim Wechseln zwischen Arbeitslasten in der Cloud, Single Sign-On Szenarien erstellt. Aber keine, sich selbst verantwortlich AuthN oder AuthZ, nur einen Teil der Abläufe bei.

Heute viele Technologien berücksichtigen diese Prozesse (AuthN und AuthZ) ist ein Mechanismus, und hören Sie viele Verweise auf Authentifizierungsprozess, die auch Authorization enthalten. Es ist wichtig, denken Sie daran, dass der erste Schritt beim Benutzerzugriff AuthN, werden sollen, Ihre Identität nachgewiesen und das AuthZ wissen verwendet, das der Benutzer ist um zu ermitteln, was er Zugriff auf hat (wie Sie mit Open Authorization oder OAuth sehen werden).

  
## <a name="authentication-and-authorization-planning-topics"></a>Authentifizierung und Autorisierung Planning-Themen

[How to use Modern Authentication (ADAL) with Skype for Business](plan-adal.md)

[Skype for Business topologies supported with Modern Authentication](topologies-supported.md)

[Planen der Legacy-Authentifizierungsmethoden intern und extern in Ihr Netzwerk zu deaktivieren.](turn-on-modern-auth.md)

