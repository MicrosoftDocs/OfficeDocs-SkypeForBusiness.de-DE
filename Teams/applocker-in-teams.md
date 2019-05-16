---
title: Richtlinien für die Kontrolle von AppLocker Anwendung in Microsoft-Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: Erfahren Sie, wie die Teams Desktopclientanwendung mit AppLocker Steuerelement Richtlinien aktivieren.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04379cad0ab224915a02475b010f908d486284cc
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34063210"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Richtlinien für die Kontrolle von AppLocker Anwendung in Microsoft-Teams

In diesem Artikel wird erläutert, wie die Teams Desktopclient app mit Richtlinien AppLocker-Steuerelement zu aktivieren. Verwendung von AppLocker dient zur Ausführung von Programm- und Skript Einschränken von Benutzern ohne Administratorrechte. Weitere Informationen und Anleitungen zu AppLocker finden Sie unter [Neuigkeiten AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

Das Verfahren zum Aktivieren von Teams mit AppLocker erfordert die Erstellung von AppLocker-basierte mithilfe von Richtlinien. Richtlinien mit Group Policy Managementsoftware und/oder die Verwendung von Windows PowerShell-Cmdlets für AppLocker erstellt werden (siehe die [AppLocker technische Referenz](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) für Weitere Informationen). Die Richtlinie AppLocker wird im XML-Format gespeichert und kann mit einem Text- oder XML-Editor bearbeitet werden.

## <a name="teams-whitelisting-with-applocker"></a>Mithilfe von Teams mit AppLocker

AppLocker-Regeln sind in Sammlungen von Regeln organisiert. AppLocker-Regeln gelten für die gezielte app, und sie sind die Komponenten, die die Richtlinie AppLocker bilden.  

Weiße Teams wird empfohlen, dass Sie die [Publisher Bedingungsregeln](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) verwenden, da alle Teams app Dateien digital signiert werden.
  
Es wird nicht die Verwendung von Pfadregeln empfohlen, da das Installationsverzeichnis Teams Benutzer nicht schreibgeschützt ist. Nicht auch empfohlen die Verwendung von Hashregeln, da die Regeln müssten aktualisiert werden, wenn die Client-Teams app aktualisiert wird.

Da Teams desktop ausführbare Dateien digital signiert werden, identifiziert die Publisher Bedingung basierte auf der digitalen Signatur und eingebettete Versionsattribute eine app-Datei. Die digitale Signatur enthält Informationen über das Unternehmen, das die app-Datei (Herausgeber) erstellt. Die Informationen zur Version, die von der Binärressource abgerufen wird, enthält den Namen des Produkts, die Datei Teil ist, und die Versionsnummer der Datei der Anwendung.

### <a name="example-of-publisher-condition-rules"></a>Beispiel für Publisher Bedingungsregeln

Für Teams-Client-Anwendung (alle Dateien, alle Versionen):

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a>Verwandte Themen
[Was ist AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [AppLocker technische Referenz](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)