---
title: PowerShell-Skript zum Testen von Direct Routing Session Border Controller-Verbindungen
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Verwenden Sie dieses PowerShell-Skriptbeispiel zum Testen von Direct Routing Session Border Controller-Verbindungen in Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd2d0aa4a22e306d08ce215341e6e0a32efb100c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837467"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>PowerShell-Skript zum Testen von Direct Routing Session Border Controller-Verbindungen

Sip Tester-Client ist ein PowerShell-Beispielskript, das Sie zum Testen von SBC-Verbindungen (Direct Routing Session Border Controller) in Microsoft Teams. Mit diesem Skript werden die Grundlegenden Funktionen eines SIP-Trunks (Session Initiation Protocol) mit Direct-Routing vom Kunden gekoppelt.

Das Skript übermittelt einen SIP-Test an den Testläufer, wartet auf das Ergebnis und stellt es dann in einem lesbaren Format vor. Mit diesem Skript können Sie die folgenden Szenarien testen:

- Ausgehende und eingehende Anrufe
- Gleichzeitiges Klingeln
- Medieneskalation
- Transfer mit Weisungsüberweisung

## <a name="download-the-script-and-documentation"></a>Herunterladen des Skripts und der Dokumentation

Laden Sie das [Clientskript und die Dokumentation für SIP-Tester herunter.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)

  > [!NOTE]
  > Sip Tester-Clientskript unterstützt nur adal.ps Version 3.19.8.1. Wenn eine neuere Version des adal.ps wird ein Fehler zurückgegeben.
  
  
