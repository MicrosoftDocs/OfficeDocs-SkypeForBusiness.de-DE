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
description: Hier erfahren Sie, wie Sie Teams Desktopclientanwendung mit AppLocker-Anwendungssteuerungsrichtlinien aktivieren.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b68d698ffcb703e70e12f3801ff70fb0719bb17cb09e23facf47121529a86b0b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288443"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>AppLocker-Anwendungssteuerelementrichtlinien in Microsoft Teams

In diesem Artikel wird erläutert, wie Sie Teams Desktopclient-App mit AppLocker-Anwendungssteuerungsrichtlinien aktivieren. Die Verwendung von AppLocker dient dazu, die Ausführung von Programm und Skripts durch Benutzer ohne Administratorrechte einzuschränken. Weitere Informationen und Anleitungen zu AppLocker finden Sie unter [Was ist AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

Der Prozess zum Aktivieren Teams mit AppLocker erfordert die Erstellung von auf AppLocker basierenden Richtlinien für die Aufnahme von Einträgen. Richtlinien werden mit Gruppenrichtlinien-Verwaltungssoftware und/oder der Verwendung von Windows PowerShell-Cmdlets für AppLocker erstellt (weitere Informationen finden Sie in der technischen Referenz zu [AppLocker).](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) Die AppLocker-Richtlinie wird im XML-Format gespeichert und kann mit beliebigem Text- oder XML-Editor bearbeitet werden.

## <a name="teams-allow-list-with-applocker"></a>Teams mit AppLocker

AppLocker-Regeln sind in Sammlungen von Regeln organisiert. AppLocker-Regeln gelten für die Ziel-App und sind die Komponenten, aus der die AppLocker-Richtlinie besteht.  

Um die Teams zu ermöglichen, empfiehlt [](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) es sich, die Bedingungsregeln des Herausgebers zu verwenden, da alle Teams-App-Dateien digital signiert sind.
  
Wir raten von der Verwendung von Pfadregeln ab, da Teams-Installationsverzeichnis vom Benutzer geschrieben werden kann. Wir raten auch von der Verwendung von Hashregeln ab, da die Regeln jedes Mal aktualisiert werden müssten, wenn Teams-Client-App aktualisiert wird.

Da Teams Desktopdateien digital signiert sind, identifiziert die Herausgeberbedingung eine App-Datei basierend auf ihrer digitalen Signatur und den eingebetteten Versionsattributen. Die digitale Signatur enthält Informationen über das Unternehmen, das die App-Datei erstellt hat (den Herausgeber). Die Versionsinformationen, die aus der Binärressource erhalten werden, enthalten den Namen des Produkts, zu dem die Datei gehört, und die Versionsnummer der Anwendungsdatei.

### <a name="example-of-publisher-condition-rules"></a>Beispiel für Herausgeberbedingungsregeln

Fügen Sie Teams-Client-App (alle Dateien, alle Versionen) Folgendes zu den Ausführbaren Regeln & DLL-Regeln hinzu:

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>Verwandte Themen
[Was ist AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Technische Referenz zu AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)