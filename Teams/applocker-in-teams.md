---
title: AppLocker-Steuerelementrichtlinien
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie die Desktopclientanwendung von Teams mit AppLocker-Anwendungssteuerungsrichtlinien aktivieren.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d6e6040956ba5e5469076b4fbbab337f58268c68
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120847"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>AppLocker-Anwendungssteuerungsrichtlinien in Microsoft Teams

In diesem Artikel wird erläutert, wie Sie die Teams-Desktopclient-App mit AppLocker-Anwendungssteuerungsrichtlinien aktivieren. Die Verwendung von AppLocker dient dazu, die Programm- und Skriptausführung durch Benutzer ohne Administratorrechte einzuschränken. Weitere Informationen und Anleitungen zu AppLocker finden Sie unter [Was ist AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

Der Prozess zum Aktivieren von Teams mit AppLocker erfordert die Erstellung von AppLocker-basierten Richtlinien für die Aufnahme von Zulassen. Richtlinien werden mit Gruppenrichtlinienverwaltungssoftware und/oder der Verwendung von Windows PowerShell-Cmdlets für AppLocker erstellt (weitere Informationen finden Sie in der technischen Referenz zu [AppLocker).](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) Die AppLocker-Richtlinie wird im XML-Format gespeichert und kann mit jedem beliebigen Text- oder XML-Editor bearbeitet werden.

## <a name="teams-allow-list-with-applocker"></a>Liste der Zulassen von Teams mit AppLocker

AppLocker-Regeln sind in Regelsammlungen organisiert. AppLocker-Regeln gelten für die gezielte App, und sie sind die Komponenten, aus der die AppLocker-Richtlinie besteht.  

Um Teams zu erlauben, empfehlen [](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) wir, die Herausgeberbedingungsregeln zu verwenden, da alle Teams-App-Dateien digital signiert sind.
  
Die Verwendung von Pfadregeln wird nicht empfohlen, da das Installationsverzeichnis von Teams vom Benutzer beschreibbar ist. Außerdem wird die Verwendung von Hashregeln nicht empfohlen, da die Regeln bei jeder Aktualisierung der #A0 aktualisiert werden müssten.

Da ausführbare Teams-Desktopdateien digital signiert sind, identifiziert die Herausgeberbedingung eine App-Datei basierend auf ihrer digitalen Signatur und eingebetteten Versionsattributen. Die digitale Signatur enthält Informationen über das Unternehmen, das die App-Datei (den Herausgeber) erstellt hat. Die Versionsinformationen, die aus der Binärressource erhalten werden, enthalten den Namen des Produkts, zu dem die Datei gehört, und die Versionsnummer der Anwendungsdatei.

### <a name="example-of-publisher-condition-rules"></a>Beispiel für Herausgeberbedingungsregeln

Fügen Sie für die Teams-Client-App (alle Dateien, alle Versionen) den ausführbaren Regeln & DLL-Regeln Folgendes hinzu:

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>Verwandte Themen
[Was ist AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Technische Referenz für AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)