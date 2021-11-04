---
title: PowerShell-Skript zum Testen von Direct Routing Session Border Controller-Verbindungen
author: cichur
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
ms.openlocfilehash: acba1d06debc9a0e06ee6636e14ee5cbf15bd90f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774405"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>PowerShell-Skript zum Testen von Direct Routing Session Border Controller-Verbindungen

Sip Tester-Client ist ein PowerShell-Beispielskript, mit dem Sie SBC-Verbindungen (Direct Routing Session Border Controller) in Microsoft Teams. Mit diesem Skript werden die Grundlegenden Funktionen eines SIP-Trunks (Session Initiation Protocol) mit Direct-Routing vom Kunden gekoppelt.

Das Skript übermittelt einen SIP-Test an den Testläufer, wartet auf das Ergebnis und stellt es dann in einem lesbaren Format vor. Mit diesem Skript können Sie die folgenden Szenarien testen:

- Ausgehende und eingehende Anrufe
- Gleichzeitiges Klingeln
- Medieneskalation
- Transfer mit Weisungsüberweisung

## <a name="download-the-script-and-documentation"></a>Herunterladen des Skripts und der Dokumentation

Laden Sie das [Clientskript und die Dokumentation für SIP-Tester herunter.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)

  > [!NOTE]
  > Sip Tester-Clientskript unterstützt nur adal.ps Version 3.19.8.1. Ein Fehler wird zurückgegeben, wenn eine neuere Version des adal.ps wird.
  
  
