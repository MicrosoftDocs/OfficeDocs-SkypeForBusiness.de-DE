---
title: AppLocker-Anwendungssteuerungsrichtlinien in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Desktopclientanwendung für Teams mit AppLocker-Anwendungssteuerungsrichtlinien aktivieren.
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb12012c0775d98c7d1b08b61c6c0deba83a4d5f
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516773"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>AppLocker-Anwendungssteuerungsrichtlinien in Microsoft Teams

In diesem Artikel wird erläutert, wie Sie die Desktop Client-App für Teams mit AppLocker-Anwendungssteuerungsrichtlinien aktivieren. Die Verwendung von AppLocker dient dazu, die Programm-und Skriptausführung durch nicht administrative Benutzer zu beschränken. Weitere Informationen und Anleitungen zu AppLocker finden Sie unter [Was ist AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

Das Verfahren zum Aktivieren von Teams mit AppLocker erfordert das Erstellen von AppLocker-basierten Whitelisting-Richtlinien. Richtlinien werden mit der Gruppenrichtlinien-Verwaltungssoftware und/oder der Verwendung von Windows PowerShell-Cmdlets für AppLocker erstellt (Weitere Informationen finden Sie in der [technischen Referenz zu AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) ). Die AppLocker-Richtlinie wird im XML-Format gespeichert und kann mit einem beliebigen Text-oder XML-Editor bearbeitet werden.

## <a name="teams-whitelisting-with-applocker"></a>Whitelists von Teams mit AppLocker

AppLocker-Regeln sind in Regelsammlungen unterteilt. AppLocker-Regeln gelten für die Ziel-APP und sind die Komponenten, aus denen die AppLocker-Richtlinie besteht.  

Für die Whitelist von Teams empfehlen wir die Verwendung der [Herausgeber Konditions Regeln](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) , da alle Teams-APP-Dateien digital signiert sind.
  
Es wird nicht empfohlen, Pfadregeln zu verwenden, da das Installationsverzeichnis für Teams vom Benutzer beschreibbar ist. Wir empfehlen auch nicht die Verwendung von Hashregeln, da die Regeln jedes Mal aktualisiert werden müssen, wenn die Client-App für Teams aktualisiert wird.

Da die ausführbaren Dateien des Teams-Desktops digital signiert sind, identifiziert die Publisher-Bedingung eine APP-Datei auf der Grundlage ihrer digitalen Signatur und der eingebetteten Versionsattribute. Die digitale Signatur enthält Informationen über das Unternehmen, das die APP-Datei (den Herausgeber) erstellt hat. Die Versionsinformationen, die aus der binären Ressource abgerufen werden, enthalten den Namen des Produkts, zu dem die Datei gehört, und die Versionsnummer der Anwendungsdatei.

### <a name="example-of-publisher-condition-rules"></a>Beispiel für Herausgeber Konditions Regeln

Für die Client-App "Teams" (alle Dateien, alle Versionen):

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a>Verwandte Themen
[Was ist AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Technische Referenz zu AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)