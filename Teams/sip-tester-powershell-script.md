---
title: PowerShell-Skript zum Testen von Direct Routing Session Border Controller-Verbindungen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Verwenden Sie dieses PowerShell-Skriptbeispiel, um Direct Routing Session Border Controller-Verbindungen in Microsoft Teams zu testen.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 215edfed535352004c960182bd649721131aedb0
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564133"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>PowerShell-Skript zum Testen von Direct Routing Session Border Controller-Verbindungen

Der SIP-Tester-Client ist ein PowerShell-Beispielskript, mit dem Sie SBC-Verbindungen (Direct Routing Session Border Controller) in Microsoft Teams testen können. Dieses Skript testet die grundlegende Funktionalität eines vom Kunden gekoppelten SIP-Trunks (Session Initiation Protocol) mit Direct Routing.

Das Skript sendet einen SIP-Test an den Testläufer, wartet auf das Ergebnis und stellt ihn dann in einem lesbaren Format dar. Sie können dieses Skript verwenden, um die folgenden Szenarien zu testen:

- Ausgehende und eingehende Anrufe
- Gleichzeitiges Klingeln
- Medieneskalation
- Beratende Übertragung

## <a name="download-the-script-and-documentation"></a>Herunterladen des Skripts und der Dokumentation

Laden Sie das [SIP Tester-Clientskript und die Dokumentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true) herunter.

  > [!NOTE]
  > Sip Tester-Clientskript unterstützt nur adal.ps Version 3.19.8.1. Wenn eine höhere Version des adal.ps verwendet wird, wird ein Fehler zurückgegeben.
  
  
