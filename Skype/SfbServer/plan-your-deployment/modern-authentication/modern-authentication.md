---
title: Planen der modernen Authentifizierung in Skype for Business
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
ms.openlocfilehash: 3b673a9f88895ac57277ef51b51fe0a4a27c64a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221579"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Diskutieren von Authentifizierung und Autorisierung in Skype for Business

Authentifizierung und Autorisierung sind verwandte Konzepte, die Sie jedoch für Sie unterschiedlich bearbeiten (obwohl beides erforderlich ist). Einfach ausgedrückt: authenciation (authn) hängt von den Geheimnissen ab, die nur ein gültiger Benutzer kennt oder hat, und dies kann ein Kennwort, Code, Fingerabdruck, ein Zertifikat, eine Kombination von Ansprüchen über den Benutzer, die wahr sind, oder eine Kombination dieser Dinge, die zusammen verwendet werden. Authn ist ein Prozess, um zu beweisen, dass Sie der sind, den Sie sagen.

Authorization (Authz) beschäftigt sich damit, worauf Sie zugreifen können, nachdem Sie bewiesen haben, wer Sie sind. Er bestimmt, was Sie sehen, bearbeiten und anderweitig zugreifen durften. Beispielsweise können Sie leistungsstarke Websitesammlungsadministratoren Zugriff auf SharePoint Online haben, aber wenn Sie zu einer anderen Online-Arbeitsauslastung wie Skype for Business Online wechseln, verfügen Sie möglicherweise über die Berechtigungen zur Behandlung von Benutzerproblemen, nicht zur Änderung der Konfiguration des Servers oder der Server. In einer dritten Arbeitsauslastung wie Exchange Online haben Sie möglicherweise nur den durchschnittlichen Benutzer Zugriff. Authz überprüft, was und wie viel Zugriff Sie auf Dienste/worloads, Anwendungen, Dateien und andere Daten haben.

Unsere Beispiele umfassen Online-Eigenschaften wie SharePoint und Exchange Online, aber die Prozesse von authn und Authz arbeiten lokal und in einem hybriden Standort auf die gleiche Weise. Letztendlich werden Tools wie Aad Connect und ADFS am authn-und Authz-Artikel beteiligt, indem lokale Konten und Kennwörter in der Cloud AD (Azure AD) synchronisiert werden oder in den Authz-Fluss eindringen, sodass ein Benutzer nicht häufig zur Eingabe seiner Anmeldeinformationen aufgefordert wird, beispielsweise beim Wechsel zwischen Arbeitsauslastungen in der Cloud und beim Erstellen von Szenarien mit einmaligem Anmelden. Sie sind jedoch nicht in sich selbst verantwortlich für authn oder Authz, sondern nur ein Teil der Mechanik.

Heute berücksichtigen viele Technologien diese Prozesse (authn und Authz) als einen Mechanismus, und Sie hören viele Verweise auf den Authentifizierungsprozess, der auch die Autorisierung enthält. Beachten Sie, dass der erste Schritt beim Benutzer Zugriff authn ist, dass Sie sich als die von Ihnen bezeichneten Personen erweisen und dass Authz das Wissen darüber verwendet, wer der Benutzer ist, um zu bestimmen, worauf er Zugriff hat (wie Sie mit offener Autorisierung oder OAuth sehen).

  
## <a name="authentication-and-authorization-planning-topics"></a>Themen zur Authentifizierung und Autorisierungs Planung

[Vorgehensweise verwenden der modernen Authentifizierung (Adal) mit Skype for Business](plan-adal.md)

[Skype for Business Topologien, die mit moderner Authentifizierung unterstützt werden](topologies-supported.md)

[Planen, die vorversions Authentifizierungsmethoden intern und extern für Ihr Netzwerk zu deaktivieren.](turn-on-modern-auth.md)

